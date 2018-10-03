---
title: Demandware
seo-title: Demandware
description: null
seo-description: Learn how to deploy eCommerce with Demandware.
uuid: 6241f3fd-1af1-48f1-9b28-d534e1339ba5
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/demandware
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 46.669-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 40 31.649-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 9605bc90-eb0a-405a-b17b-d91e53bc9150
disttype: dist5
firstPublishExternalDate: 2017-10-31T16:17:59.754-0400
gnavtheme: light
groupsectionnavitems: no
hidemerchandisingbar: inherit
hidepromocomponent: inherit
isreadyforlocalization: false
jcr-created: 2017-12-01T19 03 11.635-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:40:30.419-0400
lochandoffdate: 2018-04-30T03 26 46.668-0400
lr-lastreplicatedby: carlino@adobe.com
modalsize: 426x240
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/e-commerce
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Demandware
pagetitle: Deploying eCommerce with Demandware
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 40 30.419-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/demandware.html
qaDate: 2017-10-12T21:46:58.665-0400
qaNotes: /content/docs/en/aem/6-3/deploy/ecommerce/demandware
sha1: c8f2d52988c69be01a708aa91fbcd6e1b8c9b9dd
topicBrowsingSortDate: 2018-04-03T08:40:30.419-0400
index: y
internal: n
snippet: y
translate: y
---

# Demandware

Deploying the necessary eCommerce packages will provide the full functionality of the eCommerce framework, together with a reference implementation of eCommerce functionality as provided with a Demandware Commerce implementation (including a demonstration catalog).

### Packages Needed for eCommerce with Demandware

To install eCommerce functionality you need:

* AEM eCommerce framework:

    * this is part of a standard AEM installation

* AEM Demandware Commerce content package: ``

    * cq-6.3.0-featurepack-10262

### Installation of eCommerce with Demandware

To install AEM with a Demandware Commerce integration configuration (using the demonstration catalog, Geometrixx Outdoors), the basic steps are:

1. [Install AEM](deploy.md).

1. Install the content package using the [package manager](/content/help/en/experience-manager/6-4/sites/administering/using/package-manager):

    * cq-6.3.0-featurepack-10262

1. [Author](/content/help/en/experience-manager/6-4/sites/authoring/using/page-authoring) any supplementary pages that you need in AEM.

>[!NOTE]
>
><p>To download the packages, navigate to&nbsp;<a href="/content/help/en/experience-manager/6-4/sites/administering/using/package-manager.html#PackageShare">Package Share</a>.</p>

The server connection between AEM and the Demandware Sandbox needs to be configured. Most of the configuration is already preconfigured to work with the provided SiteGenisis demo content package using default paths, libraries, and so on. If the connector is used with other sites and libraries, you will need to update this configuration.

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Demandware Client**.

1. Enter the **Instance endpoint ip or hostname** as required.
   ![](assets/chlimage_1.png)
1. Click **Save**.

1. Click **Demandware TransportHandler Plugin for WebDAV**.

1. Set the **WebDAV user** and the **WebDAV user password**.
   ![](assets/chlimage_1.png)
1. Click **Save**.

#### Replication

The replication should be enabled after the package installation, you can verify that here: [http://localhost:4502/etc/replication/agents.author/demandware.html](http://localhost:4502/etc/replication/agents.author/demandware.html)

>[!NOTE]
>
><p>The replication agent is configured to info log level by default. If you want to have more information, you can switch the log level to debug.</p>

#### OAuth

The OAuth client is configured to work with a Demandware sandbox instance. For testing purposes, no change is needed.

For staging and productions systems, the OAuth clients need to be configured with appropriate client ID and password.

1. Navigate to [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).

1. Click **Demandware Access Token provider**.
   ![](assets/chlimage_1.png)
1. Modify the values as required and click **Save**.

### Demandware Sandbox

The Demandware Sandbox must be configured to run the new Velocity template engine.

>[!NOTE]
>
><p>The following wizard is not part of the AEM Demandware connector. It is provided as is as part of the demo content package to help with quickly setting up the SiteGenesis demo pages.</p>

1. Navigate to [http://localhost:4502/etc/demandware/init.html](http://localhost:4502/etc/demandware/init.html).

1. Click **Edit.**

1. Verify the values and click **OK**.

1. Click **Initialize**.

1. Go to the WebDAV folder and check for published template files, for example under `adobe01-tech-prtnr-na01-dw.demandware.net/on/demandware.servlet/webdav/Sites/Dynamic/SiteGenesis`.

   >[!NOTE]
   >
   ><p>The extension will be <span class="code">.vs</span>.</p> 

1. Check also for exported JS and CSS files, for example under `adobe01-tech-prtnr-na01-dw.demandware.net/on/demandware.servlet/webdav/Sites/Libraries/SiteGenesisSharedLibrary`.
