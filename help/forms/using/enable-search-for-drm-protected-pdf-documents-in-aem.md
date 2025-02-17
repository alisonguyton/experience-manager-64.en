---
title: Enable AEM to search document security protected PDF documents
seo-title: Enable AEM to search document security protected PDF documents
description: Learn how to enable native AEM search to perform full-text search on DRM protected PDF documents.  
seo-description: Learn how to enable native AEM search to perform full-text search on DRM protected PDF documents.  
uuid: c743cda3-252f-4c1f-8d94-e6d26d91dcd8
contentOwner: khsingh
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
geptopics: SG_AEMFORMS/categories/working_with_document_security
discoiquuid: 759068fa-dc1b-4cf5-bc7b-62b8c5464831
---

# Enable AEM to search document security protected PDF documents {#enable-aem-to-search-document-security-protected-pdf-documents}

AEM search is capable of searching and locating AEM assets and performing text search on various commonly used document formats such as plain-text files, Microsoft Office documents, and PDF documents. You can also extend the native search to perform full-text search on [PDF Documents protected with AEM Document security](/help/forms/using/admin-help/document-security.md). To enable AEM to perform full-text search on such documents, perform the following steps:

1. Establish a secure connection
1. Index a sample policy-protected PDF document

## Prerequisites {#prerequisites}

* If you are using AEM Forms on OSGi:

    * Install [AEM Forms Document Security Indexer package](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) on the AEM Forms server. 
    * Ensure an AEM Forms on JEE server is up and running and document security is installed on corresponding AEM Forms on JEE server. The AEM Form on JEE server is required to index the protected document.

* If you are using only AEM Forms on JEE server, the indexer package is already installed.  
* Ensure that all the bundles are up and running. If all the bundles are not active, wait until all the bundles are up and running.

    * For AEM Forms on OSGi, the bundles are listed at `https://[server]:[port]/system/console/bundles`.
    * For AEM Forms on JEE, the bundles are listed at `https://[server]:[port]/[context-path]/system/console/bundles`. For example `http://localhost:8080/lc/system/console/bundles`.

* Whitelist the *sun.util.calendar* package. To whitelist the package, perform the following steps:

    1. Open AEM Web Console. The URL is `https://[server]:[port]/system/console/configMgr`.
    1. Locate and open **Deserialization Firewall Configuration**.
    1. Add the sun.util.calendar package to the Whitelisted classes or package prefixes field and click **Save**.

## Establish a secure connection between AEM Forms JEE and OSGi stacks {#establish-a-secure-connection-between-aem-forms-jee-and-osgi-stacks}

You can use one of the following methods to establish the secure connection:

* Configure Adobe LiveCycle Client SDK Bundle with AEM Forms on JEE admin credentials
* Configure Adobe LiveCycle Client SDK Bundle using mutual authentication

### Configure Adobe LiveCycle Client SDK Bundle with AEM Forms on JEE admin credentials {#configure-adobe-livecycle-client-sdk-bundle-with-aem-forms-on-jee-admin-credentials}

1. Open AEM Web Console. The URL is `https://[server]:[port]/system/console/configMgr`.
1. Locate and open the **Adobe LiveCycle Client SDK Bundle**. Specify value for the following fields:

    * **Server URL:** Specify HTTP URL of AEM Forms on JEE server. To enable communication over https, restart the server with the -Djavax.net.ssl.trustStore=&lt;path of AEM Forms on JEE keystore file&gt; parameter.
    * **Service Name**: Add the RightsManagementService to the list of specified services.
    * **Username:** Specify user name of the AEM Forms on JEE account to use to initiate calls from AEM server. The account specified must have permissions to start document services on the AEM Forms on JEE server.
    * **Password**: Specify password of the AEM Forms on JEE account mentioned in the Username field.

   Click **Save**. AEM is enabled to search document security protected PDF documents.

### Configure Adobe LiveCycle Client SDK Bundle using mutual authentication {#configure-adobe-livecycle-client-sdk-bundle-using-mutual-authentication}

1. Enable mutual authentication for AEM Forms on JEE. For detailed information, see [CAC and Mutual Authentication](https://helpx.adobe.com/livecycle/kb/cac-mutual-authentication.html).
1. Open AEM Web Console. The URL is `https://[server]:[port]/system/console/configMgr`.
1. Locate and open the **Adobe LiveCycle Client SDK** Bundle. Specify value for the following properties:

    * **Server URL**: Specify HTTPS URL of AEM Forms on JEE server. To enable communication over https, restart the AEM server with the -Djavax.net.ssl.trustStore=&lt;path of AEM Forms on JEE keystore file&gt; parameter.
    * **Enable 2-way SSL**: Enable the Enable 2-way SSL option.
    * **KeyStore File URL**: Specify the URL of the keystore file.
    * **TrustStore FIle URL**: Specify the URL of the truststore file.
    * **KeyStore Password**: Specify the password for the keystore file.
    * **TrustStorePassword**: Specify the password for the truststore file.
    * **Service Name**: Add the RightsManagementService to the list of specified services.

   Click **Save**. AEM is enabled to search document security protected PDF documents

## Index a sample policy-protected PDF document {#index-a-sample-policy-protected-pdf-document}

1. Log in to AEM Assets as an administrator.
1. Create a folder in AEM Digital Asset Manager and upload the policy-protected PDF documents to the newly created folder.

   Now, you can search the policy-protected documents using AEM search.

