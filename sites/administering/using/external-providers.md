---
title: Analytics with External Providers
seo-title: Analytics with External Providers
description: null
seo-description: Learn about Analytics with External Providers.
uuid: cf7ee88c-d7ae-4faa-b80a-0a3cb3559464
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: c63d04be-084d-4a85-9278-65bbc73dc2a0
isreadyforlocalization: false
jcr-lastmodifiedby: remove-legacypath-6-1
index: y
internal: n
snippet: y
---

# Analytics with External Providers{#analytics-with-external-providers}

Analytics can provide you with important and interesting information about how your website is being used.

Various out-of-the box configurations are available for integrating with the appropriate service, for example:

* [Adobe Analytics](../../administering/using/adobeanalytics.md)
* [Adobe Target](../../administering/using/target.md)

You can also configure your own instance of the **Generic Analytics Snippets** to define a new service configurations.

The information is then collected by means of small snippets of code that are added to the web pages. For example:

>[!CAUTION]
>
>Scripts must not be enclosed in `script` tags.

```
var _gaq = _gaq || [];
_gaq.push(['_setAccount', 'UA-XXXXX-X']);
_gaq.push(['_trackPageview']);

(function() {
    var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
    ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
    var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
})();
```

Such snippets enable data to be collected and reports generated. The actual data collected depends on the provider and the actual code snippet used. Example statistics include:

* how many visitors over time
* how many pages visited
* search terms used
* landing pages

>[!CAUTION]
>
>The Geometrixx-Outdoors demo site is configured so that the attributes provided in the Page Properties are appended to the html source code (just above the `</html>` endtag) in the corresponding `js` script.  

>
>If your own `/apps` do not inherit from the default page component ( `/libs/foundation/components/page`) you (or your developers) have to make sure that the corresponding `js` scripts are included, for example by either including `cq/cloudserviceconfigs/components/servicescomponents`, or using a similar mechanism.  

>
>Without this, none of the services (Generic, Analytics, Target, etc) will work.

## Creating a new Service with a Generic Snippet {#creating-a-new-service-with-a-generic-snippet}

For the basic configuration:

1. Open the **Tools** console.  

1. From the left pane expand **Cloud Services Configurations**.  

1. Double-click on **Generic Analytics Snippet** to open the page:

   ![](assets/Analytics_GenericOverview.png)

1. Click on the + to add a new configuration using the dialog; at a minimum assign a name, for example google analytics:

   ![](assets/Analytics_AddConfig.png)

1. Click **Create**, the snippet dialog will open immediately - paste the appropriate javascript snippet into the field:

   ![](assets/Analytics_Snippet.png)

1. Click **OK** to save.

## Using your new Service on Pages {#using-your-new-service-on-pages}

Having created the service configuration you now need configure the required pages to use it:

1. Navigate to the page.  

1. Open the **Page Properties** from sidekick, then the **Cloud Services** tab.  

1. Click **Add Service**, then select the required service; for example the **Generic Analytics Snippet**:

   ![](assets/Analytics_SelectService.png)

1. Click **OK** to save.  

1. You will be returned to the **Cloud Services** tab. The **Generic Analytics Snippet** is now listed with the message `Configuration reference missing`. Use the drop down list to select your specific service instance; for example google-analytics:

   ![](assets/Analytics_SelectSpecificService.png)

1. Click **OK** to save.

   The snippet can now be seen if you view the Page Source for the page.

   After a suitable period of time has elapsed, you will be able to view the statistics that have been collected.

   >[!NOTE]
   >
   >If the configuration is attached to a page that has child pages, the service is inherited by those as well.
