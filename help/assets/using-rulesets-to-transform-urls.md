---
title: Using Rulesets to Transform URLs
seo-title: Using Rulesets to Transform URLs
description: You can deploy rule sets in Dynamic Media to transform URLs. Rule sets are sets of instructions written in a scripting language (such as JavaScript) that evaluate XML data and take certain actions if that data meets certain conditions. 
seo-description: You can deploy rule sets in Dynamic Media to transform URLs. Rule sets are sets of instructions written in a scripting language (such as JavaScript) that evaluate XML data and take certain actions if that data meets certain conditions. 
uuid: 9fed0c83-67b7-4483-a9b4-322e6a483449
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: abcff903-204b-4ab6-87d8-6f0ce63d7b41
---

# Using rule sets to transform URLs {#using-rulesets-to-transform-urls}

You can deploy rule sets in Dynamic Media to transform URLs. Rule sets are sets of instructions written in a scripting language (such as JavaScript) that evaluate XML data and take certain actions if that data meets certain conditions. Each rule consists of at least one condition and at least one action. A rule evaluates the XML data against the conditions, and if a condition is met, then it takes the appropriate action. Examples of rule sets include the following:

* Adding a MIME type suffix. Many services and websites require image suffixes, such as adding `.jpg` to a URL.
* Creating a folder path to the URL for SEO (Search Engine Optimization) purposes. 

  See [How Adobe Scene7 Publishing System Supports SEO](https://marketing.adobe.com/resources/help/en_US/s7/s7_seo.pdf).  

* Adding metadata to the URL for SEO (Search Engine Optimization) purposes. 

  See [How Adobe Scene7 Publishing System Supports SEO](https://marketing.adobe.com/resources/help/en_US/s7/s7_seo.pdf).  

* Setting the content disposition to trigger a download.
* Simplify Image Serving templating URLs for personalization. For example, turn `rgb{XX,YY,ZZ}` into the RTF-ready `\redXX\greenYY\blueZZ`

* Request certain characters to be encoded such as `$`, `{`, and `}`, and certain characters to be decoded toward ImageServer. For example, Facebook does not work well with URLs containing special characters.  

  See [Removing special characters from URLs](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/remove-special-characters-urls.html).

In the context of Dynamic Media, websites that use an XML-based system to manage asset information can upload XML files to Dynamic Media. You can designate one of these files as the pre-processing rule set file for serving Dynamic Media asset. This file restructures the standard URL protocol format to meet the business logic of systems being integrated with Dynamic Media. You specify an XML file to serve as the rule set definitions file path.

>[!CAUTION]
>
>Use caution when using rulesets; they can prevent Dynamic Media content from being displayed on your website.

There are sample rulesets available that can help you create your own ruleset.  
See [Rule set reference](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/image_catalog/c_rule_set_reference.html).

As with all rule set creation, ensure that your XML file is valid before you upload it by using an XML validator program such as xmlvalid.  
See also [Troubleshooting rule sets](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/scene7-ruleset-troubleshooting.html).

Also, make sure you first test your rule set in a staging environment that does not impact your live production environment.  
Production environments and staging environments typically require different logins.

* **NA staging environment** login page: [https://s7sps1-staging.scene7.com/IpsWeb/](https://s7sps1-staging.scene7.com/IpsWeb/)
* **EMEA staging environment** login page: [https://s7sps3-staging.scene7.com/IpsWeb/](https://s7sps3-staging.scene7.com/IpsWeb/)
* **JAPAC staging environment** login page: [https://s7sps5-staging.scene7.com/IpsWeb/](https://s7sps5-staging.scene7.com/IpsWeb/)

See also [Using 'asset' instead of 'is' image in a rule set](https://helpx.adobe.com/experience-manager/scene7/kb/base/scene7-rulesets/ruleset-asset-instead-image.html).

**To deploy XML rule sets:**

1. Log on to your Dynamic Media Classic account:

   [https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html](https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html)

   Your credentials and logon were provided by Adobe at the time of provisioning. If you do not have this information, contact Technical Support.

1. Upload your rule set file by doing the following:

    * On the Global Navigation bar, click **[!UICONTROL Upload]**.
    * On the **[!UICONTROL Upload]** page, near the upper-left corner, click **[!UICONTROL Browse]**.
    * In the **[!UICONTROL Open]** dialog box, browse to your rule set file (XML).
    * Select the file, then click **[!UICONTROL Open]**.
    * On the right side of the **[!UICONTROL Upload]** page, select a destination folder for the rule set file.
    * Near the bottom of the page, ensure **[!UICONTROL Publish After Uploading]** is checked.
    * In the bottom right corner of the page, click **[!UICONTROL Submit Upload]**.
    * On the Global Navigation bar, click **[!UICONTROL Jobs]** to check the status of the upload job. When the **[!UICONTROL Status]** column on the **[!UICONTROL Job]** page says Upload Done, continue to the next steps.

1. On the navigation bar near the top of the page, click **[!UICONTROL Setup &gt; Application Setup &gt; Publish Setup &gt; Image Server]**.
1. On the **[!UICONTROL Image Server Publish]** page, under the **[!UICONTROL Catalog Management]** group, locate **[!UICONTROL Rule Set Definition File Path]**, then click **[!UICONTROL Select]**.
1. On the **[!UICONTROL Select Rule Set Definition File (XML)]** page, browse to your rule set file, then in the lower-right corner of the page, click **[!UICONTROL Select]**.
1. In the lower-right corner of the Setup page, click **[!UICONTROL Close]**.
1. Run an Image Server Publish job.

   The rule set conditions are applied on the requests to the live Dynamic Media Image Servers.

   If you make changes to the rule set file, the changes are immediately applied when you re-upload and re-publish the updated rule set file.

