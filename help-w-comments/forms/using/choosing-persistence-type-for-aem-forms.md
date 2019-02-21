---
title: Choosing a persistence type for an AEM Forms installation
seo-title: Choosing a persistence type for an AEM Forms installation
description: Choose a persistence type wisely. It helps you build an efficient and scalable AEM Forms environment. 
seo-description: Choose a persistence type wisely. It helps you build an efficient and scale able AEM Forms environment. 
uuid: 029d63da-e3b6-4001-a4ad-2a67b3d934f2
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: 7fb81059-914d-44f4-a3ac-c10e0e0dc817
index: y
internal: n
snippet: y
---

# Choosing a persistence type for an AEM Forms installation{#choosing-a-persistence-type-for-an-aem-forms-installation}

Choose a persistence type wisely. It helps you build an efficient and scalable AEM Forms environment. 

Persistence is the method to store content on the physical storages. It defines the actual data structure and storage mechanism for the data. MicroKernels act as persistence managers in AEM Forms. AEM Forms supports persistence (MicroKernals) of type TarMK, MongoMK, and RDBMK. You can choose a persistence type for AEM Forms depending upon the purpose and deployment type (Single-Server, Farm, or Cluster) of an AEM Forms instance.

>[!NOTE]
>
>LiveCycle ES4 SP1 uses TarPM persistence to store content.

The following table lists all the supported persistence types along with various parameters to help you choose a persistence type for your environment: 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <th><strong>Installation Type / Cost</strong></th> 
   <th><strong>TarMK</strong></th> 
   <th><strong>MongoMk</strong></th> 
   <th><strong>RDBMK</strong></th> 
  </tr>
  <tr>
   <th><strong>Standalone Setup</strong></th> 
   <td>Supported<br /> </td> 
   <td>Supported</td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <th><strong>Cluster Setup</strong></th> 
   <td>Not Supported</td> 
   <td>Supported</td> 
   <td>Supported</td> 
  </tr>
  <tr>
   <th><strong>License Cost</strong></th> 
   <td>Included with AEM </td> 
   <td>Separate license required</td> 
   <td>Separate license required</td> 
  </tr>
 </tbody>
</table>

TarMK is designed for performance, while MongoMK and RDBMK are designed for scalability. Adobe highly recommends TarMK as the default persistence technology for all AEM Forms deployment scenarios, for both Author and Publish instances, except in the use cases outlined in section [Choosing Mongo or a Relational Database Microkernel over TarMK](#main-pars-header).

For the list of supported Microkernels, see [AEM Forms on OSGi Technical Requirements](../../sites/deploying/using/technical-requirements.md) or [AEM Forms on JEE supported platform combinations](../../forms/using/AEM-forms-JEE-supported-platforms.md) articles.

## Choosing Mongo or a Relational Database Microkernel over TarMK {#choosing-mongo-or-a-relational-database-microkernel-over-tarmk}

A scalable (clustered) AEM Forms environment is a set of two or more horizontally configured active author instances. You can choose to run more than one author instance if a single server, supporting all concurrent authoring activities, is no longer sustainable.

Only MongoMK and RDBMK persistence type are supported for a scalable (clustered) AEM Forms on JEE environment. The number of servers or the size of scalable environment varies for every installation. For a list of considerations and examples, see the [Recommended Deployments](../../sites/deploying/using/recommended-deploys.md) and or [Architecture and deployment topologies for AEM Forms](../../forms/using/aem-forms-architecture-deployment.md) article. You can also contact AEM Forms support for detailed information on capacity planning for AEM Forms with RDBMK and TarMK.

<!--
<related-links>
<a href="https://helpx.adobe.com/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html" target="_blank">Installing and configuring AEM Forms</a>
<a href="../../forms/using/html5-forms-architecture.md" target="_blank">Architecture and deployment topologies for AEM Forms</a>
</related-links>
-->
