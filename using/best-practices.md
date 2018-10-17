---
title: Deploying Best Practices
seo-title: Deploying Best Practices
description: null
seo-description: Deploying and maintaining best practices.
uuid: 398594ee-ea05-4968-b708-eab902b8d1bc
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/best-practices
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 26 47.735-0400
cq-lastmodifiedby: carlino
cq-lastreplicated: 2018-04-03T08 39 38.497-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
cq-template: /apps/help/templates/article-3
discoiquuid: 3b0a963f-3660-40f0-9676-7b7b76a27191
firstPublishExternalDate: 2017-10-31T16:18:15.009-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 01 48.869-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
lastPublishExternalDate: 2018-04-03T08:39:37.757-0400
lochandoffdate: 2018-04-30T03 26 47.735-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/best-practices;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/best-practices
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Best Practices
publishexternaldate: 2018-04-03T08 39 37.757-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/best-practices.html
qaDate: 2017-10-12T21:46:00.000-0400
qaNotes: /content/docs/en/aem/6-3/deploy/best-practices
sha1: 06ba67b5d2d88639f683f1635a4f255b7dea3ecd
topicBrowsingSortDate: 2018-04-03T08:39:37.757-0400
index: y
internal: n
snippet: y
---

# Deploying Best Practices

Deploying best practices describe how to deploy or maintain AEM in the most efficient and most effective way possible. This growing list of topics includes a variety of areas in AEM.

The following areas have documentation available concerning deploying and maintaining best practices and recommendations:

* [OAK](#OAK)
* [Communities](#Communities)
* [UI](#UI)
* [Performance](#Performance)

For best practices on administering, developing, or authoring, see one of the following:

* [Administering best practices](/content/help/en/experience-manager/6-4/sites/administering/using/administer-best-practices)
* [Developing best practices](/content/help/en/experience-manager/6-4/sites/developing/using/best-practices)
* [Authoring best practices](/content/help/en/experience-manager/6-4/sites/authoring/using/best-practices)

Specific documents are described and linked to in the tables that follow.

## OAK
[Oak](platform.md) is a scalable and performant hierarchical content repository that is the foundation of AEM. 

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><p>Scalability, Performance and Disaster Recovery</p> </td> 
   <td><a href="performance.md">Performance &amp; Scalability</a></td> 
   <td>Provides a white paper discussing the technical agility, high performance, and sound disaster recovery features</td> 
  </tr>
  <tr>
   <td>Recommended OAK deployments</td> 
   <td><a href="recommended-deploys.md">Recommended deployments</a></td> 
   <td>Describes deployment scenarios</td> 
  </tr>
  <tr>
   <td>Mongo topology</td> 
   <td><a href="recommended-deploys.md">Mongo topology best practices</a></td> 
   <td>Describes mongo topology - when to use which topology.</td> 
  </tr>
  <tr>
   <td>Datastore options</td> 
   <td><a href="data-store-config.md">Configuring node and data stores</a></td> 
   <td>This document explains best practices around storing binary data and content nodes. Includes informationon using Amazon S3 data store.</td> 
  </tr>
  <tr>
   <td>Search in OAK</td> 
   <td><a href="best-practices-for-queries-and-indexing.md">Best Practices for Queries and Indexing</a><br /> </td> 
   <td>Describes best practices on how to index content.</td> 
  </tr>
 </tbody>
</table>

## Communities
AEM Communities simplifies the creation and management of on-premise Communities. Best practices for AEM Communities are described here:

| Community Content Persistence | [Community Content Store](/content/help/en/experience-manager/6-4/communities/using/working-with-srp) |Discusses the new shared storage feature for user generated content (UGC) and the considerations for choosing the underlying [topology](/content/help/en/experience-manager/6-4/communities/using/topologies). |
|---|---|---|
| Deployments for Communities | [Recommended deployments](recommended-deploys.md#ConsiderationsforAEMCommunities) |Describes the recommended deployments for Communities. |

## UI
Best practices around the user interface are described here:

| Recommendations for UI selection | [User Interface Recommendations for Customers](ui-recommendations.md) |AEM currently has two UIs: classic and touch-optimized UI in the same release. Therefore customers have to make a decision about which to use during the project implementation. This document is intended to help with finding the right choice.. |
|---|---|---|

## Performance
Best practices around performance are listed here:

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td>Best Practices for Quality Assurance</td> 
   <td><a href="configuring-performance.md#BestPracticesforQualityAssurance">Best Practices for Quality Assurance</a></td> 
   <td>A standardized overview of the issues involved with defining a Test Concept specifically for performance tests on your <em>publish</em> environment. This is primarily of interest to QA engineers, project managers and system administrators.</td> 
  </tr>
  <tr>
   <td>Using Dispatcher with a CDN</td> 
   <td><a href="/content/help/en/experience-manager/dispatcher/using/dispatcher#UsingDispatcherwithaCDN">Using Dispatcher with a CDN</a></td> 
   <td>A content delivery network (CDN), such as Akamai Edge Delivery or Amazon Cloud Front, deliver content from a location close to the end user.</td> 
  </tr>
  <tr>
   <td>Performance Optimization</td> 
   <td><a href="configuring-performance.md">Performance Optimization</a></td> 
   <td>A key issue is the time your website takes to respond to visitor requests.</td> 
  </tr>
  <tr>
   <td>Performance Testing</td> 
   <td><a href="best-practices-for-performance-testing.md">Best Practices for Performance Testing</a></td> 
   <td>Describes best practices for running performance tests on an AEM deployment.<br /> </td> 
  </tr>
 </tbody>
</table>
