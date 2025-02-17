---
title: SPA and Server-Side Rendering
seo-title: SPA and Server-Side Rendering
description: null
seo-description: null
uuid: fbf7d0d1-865d-45d2-aeec-a7e3caf3fcb2
contentOwner: David Hasselhof
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: spa
content-type: reference
discoiquuid: 30d25772-0df7-468e-bcbd-c6fb2e962662
---

# SPA and Server-Side Rendering{#spa-and-server-side-rendering}

>[!NOTE]
>
>AEM 6.4.5.0 or later is required to use the SPA server side rendering features as described in this document.

## Overview {#overview}

Single page applications (SPAs) can offer the user a rich, dynamic experience that reacts and behaves in familiar ways, often just like a native application. [This is achieved by relying on the client to load the content up front and then do the heavy lifting of handling user interaction](/help/sites-developing/spa-walkthrough.md#how-does-a-spa-work) and thus minimizing the amount of communication needed between the client and the server, making the app more reactive.

However this can lead to longer initial load times, especially if the SPA is large and rich in its content. In order to optimize load times, some of the content can be rendered server-side. Using server side rendering (SSR) can accelerate the initial load of the page and then pass further rendering on to the client.

## When to Use SSR {#when-to-use-ssr}

SSR is not required on all projects. Althgouh AEM fully support JS SSR for SPA, Adobe does not recommend implementing it systematically for every project.

When deciding to implement SSR you must first estimate what additional complexity, effort, and cost adding SSR realistically represents for the project, including the long term maintenance. An SSR architecture should be chosen only when the added value clearly exceeds the estimated costs.

SSR usually provides some value when there is a clear "yes" to either of the following questions:

* **SEO:** Is SSR still actually required for your site to be properly indexed by the search engines that bring traffic? Keep in mind that the main search engine crawlers now evaluate JS.
* **Page Speed:** Does SSR provide a measurable speed improvement in real-life environments and add to the overall user experience?

Only when one of these two questions are answered with a clear "yes" for your project does Adobe recommend implementing SSR. The following sections describe how to do this using Node.js.

## AEM-Driven Communication Flow {#aem-driven-communication-flow}

When using SSR, the [component interaction workflow](/help/sites-developing/spa-overview.md#workflow) of SPAs in AEM includes a phase in which the initial content of the app is generated on a Node.js server.

1. The browser requests the SSR content from AEM  

1. AEM posts the model to the Node.js server

1. The Node.js server returns the generated content  

1. AEM serves the HTML returned by the Node.js server via the HTL template of the backend page component.

![server-side-rendering-cms-drivenaemnode](assets/server-side-rendering-cms-drivenaemnode.png)

### Node.js-Driven Communication Flow {#node-js-driven-communication-flow}

The previous section describes the standard and recommended implementation of server side rendering with regards to SPAs in AEM, where AEM performs the bootstrapping and serving of content.

Alternatively, SSR can be implemented so that the Node.js server is responsible for the bootstrapping, effectively reversing the communication flow.

Both models are valid and supported by AEM. However, one should consider the advantages and disadvantages of each before implementing a particular model.

|Bootstrapping|Advantages|Disadvantages|
|-|-|-|
|via AEM|AEM manages injecting libraries where needed<br>Resources only need to be maintained on AEM|Possibly unfamiliar to SPA developer|
|via Node.js|More familiar to SPA developers|Clientlib resources required by the application such as CSS and JavaScript will need to be made available by the AEM developer via the [`allowProxy` property](/help/sites-developing/clientlibs.md#locating-a-client-library-folder-and-using-the-proxy-client-libraries-servlet)<br>Resources must be synched between AEM and the Node.js server<br>To enable authoring of the SPA, a proxy server for the Node.js instance may be necessary|

## Planning for SSR {#planning-for-ssr}

Generally only part of an application needs to be rendered server side. The common example is the content that will be displayed above the fold on the initial load of the page is rendered server side. This saves time by delivering to the client, already rendered content. As the user interacts with the SPA, the additional content is rendered by the client.

As you consider implementing server side rendering for your SPA, you need to review for what parts of the app it will be necessary.

## Developing an SPA using SSR {#developing-an-spa-using-ssr}

SPA components could be rendered by the client (in the browser) or server side. When rendered server side, browser properties such as window size and location are not present. Therefore SPA components should be isomorphic, making no assumption about where they will be rendered.

To leverage SSR, you will need to deploy your code in AEM as well as on a Node.js server. Node.js is responsible for the server side rendering. Most of the code will be the same, however server-specific tasks will differ.

## SSR for SPAs in AEM {#ssr-for-spas-in-aem}

SSR for SPAs in AEM require a Node.js server, which is called for the rendering of the app content server side. Within the HTL of the app, a resource on the Node.js server is called to render the content.

Just as AEM supports the Angular and React SPA frameworks out-of-the box, server side rendering is also supported for Angular and React apps. See the NPM documentation for both frameworks for further details.

* React: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)
* Angular: [https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component](https://github.com/adobe/aem-sample-we-retail-journal/blob/master/react-app/DEVELOPMENT.md#enabling-the-server-side-rendering-using-the-aem-page-component)

For a simplistic example, please refer to the [We.Retail Journal app](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail-journal). It renders the entire application server side. Although this is not a real-world example, it does illustrate what is needed to implement SSR.

>[!NOTE]
>
>Adobe recommends a separate Node.js instance for every AEM environment (author, publish, stage, etc.).

>[!CAUTION]
>This document uses the [We.Retail Journal app](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail-journal) for demonstration purposes only. It should not be used for any project work.
>
>All SPA projects on AEM should be based on the [Maven Archetype for SPA Starter Kit](https://github.com/adobe/aem-spa-project-archetype).
