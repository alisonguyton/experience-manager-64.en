---
title: SPA and Launch Integration
seo-title: SPA and Launch Integration
description: Adobe Launch is the recommended way to implement Analytics, Target, and Audience Manager within SPAs.
seo-description: Adobe Launch is the recommended way to implement Analytics, Target, and Audience Manager within SPAs.
uuid: 6652f429-df7d-4e45-8dfa-48ce6377e8be
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: spa
discoiquuid: 8c21b773-b796-418f-b118-2b3784d7d573
index: y
internal: n
snippet: y
---

# SPA and Launch Integration{#spa-and-launch-integration}

Adobe Launch is the recommended way to implement Analytics, Target, and Audience Manager within Single Page Applications (SPAs).

>[!CAUTION]
>
>The Single-Page Application (SPA) Editor feature was introduced with AEM 6.4 and is currently a release candidate. The SPA Editor will be available in [6.4 SP2](/content/help/en/experience-manager/maintenance-releases-roadmap).
>
>The SPA Editor is the recommended solution for projects that require SPA framework based client-side rendering (e.g. React).

## Tutorial {#tutorial}

To understand how to integrate your SPA with Adobe Launch, please see [this knowledge base article and tutorial](/content/help/en/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement), which will guide you through the Launch setup as well as implement the Experience Cloud in built with Angular or React.

>[!NOTE]
>
>The referenced KB was created to enable Launch integration with SPAs that don't leverage the AEM SPA Editor. These methods should also allow the Launch integration to coexist with SPAs that are built to use the SPA Editor.  

>
>Because the SPA Editor is in prerelease, the use of Redux alongside the Javascript SPA libraries has not been fully explored. Support of Redux is planned in a future release of the SPA Editor.
