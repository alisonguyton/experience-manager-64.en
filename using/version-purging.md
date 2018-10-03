---
title: Version Purging
seo-title: Version Purging
description: null
seo-description: This article describes the available options for version purging.
uuid: b07b1ed7-09a8-4efc-acb8-4147a3e51733
content-encoding: ISO-8859-1
aemsrcnodepath: /content/help/en/experience-manager/6-4/sites/deploying/using/version-purging
contentOwner: Guillaume Carlino
cq-designpath: /etc/designs/help
cq-lastmodified: 2018-04-30T03 29 29.390-0400
cq-lastmodifiedby: bohnert
cq-lastreplicated: 2018-04-03T08 47 02.529-0400
cq-lastreplicatedby: carlino
cq-lastreplicationaction: Activate
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
cq-template: /apps/help/templates/article-3
discoiquuid: 2548a564-d65c-423b-a567-b5da29ac7733
firstPublishExternalDate: 2017-10-31T16:17:29.758-0400
isreadyforlocalization: false
jcr-created: 2017-12-01T19 05 31.628-0500
jcr-createdby: admin
jcr-ischeckedout: true
jcr-language: en_us
jcr-lastmodifiedby: remove-legacypath-6-1
lastPublishExternalDate: 2018-04-03T08:47:02.061-0400
lochandoffdate: 2018-04-30T03 29 29.389-0400
lr-lastreplicatedby: carlino@adobe.com
moreHelpPaths: /content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring;/content/help/en/experience-manager/6-4/sites/deploying/morehelp/configuring
mwpw-migration-script-version: 2017-10-12T21 46 58.665-0400
navTitle: Version Purging
primaryAudienceTag: audience:deploying
primaryProductTag: products:SG_EXPERIENCEMANAGER/6.4/SITES
publishexternaldate: 2018-04-03T08 47 02.061-0400
publishExternalURL: https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/version-purging.html
qaDate: 2017-10-12T21:46:58.665-0400
qaNotes: /content/docs/en/aem/6-3/deploy/configuring/version-purging
sha1: eeef380b8587e5f6252447f6dfe6fbdb3d958720
topicBrowsingSortDate: 2018-04-03T08:47:02.061-0400
index: y
internal: n
snippet: y
translate: y
---

# Version Purging

In a standard installation AEM creates a new version of a page or node when you activate a page after updating the content.

>[!NOTE]
>
><p>If no content changes are made then you will see the message stating that the page has been activated, but no new version will be created</p> 
You can create additional versions on request using the **Versioning** tab of the sidekick. These versions are stored in the repository and can be restored if required.

These versions are never purged, so the repository size will grow over time and therefore need to be managed.

AEM is shipped with various mechanisms to help you manage your repository:

* the [Version Manager](#VersionManager) This can be configured to purge old versions when new versions are created.
* the ** [Purge Versions](#PurgeVersionsTool) **tool This is used as part of [monitoring and maintaining](monitoring-and-maintaining.md) your repository. It allows you to intervene to remove old versions of a node, or a hierarchy of nodes, according to these parameters:

    * The maximum number of versions to be kept in the repository. When this number is exceeded, the oldest version is removed.    
    * The maximum age of any version kept in the repository. When the age of a version exceeds this value, it is purged from the repository.

---

## Version Manager
In addition to explicit purging by means of the purge tool, the Version Manager can be configured to purge old versions when new versions are created.

To configure the Version Manager, create a configuration for:

`PID com.day.cq.wcm.core.impl.VersionManagerImpl`

The following options are available:

* `versionmanager.createVersionOnActivation` (Boolean, default: true) whether to create a version when pages are activated. A version is created unless the replication agent is configured to suppress creation of versions, which is honoured by the Version Manager A version is only created if the activation happens on a paths that is contained in versionmanager.ivPaths (see below).
* `versionmanager.ivPaths` (String[], default: {"/"}) paths on which versions are implicitly created on activation if versionmanager.createVersionOnActivation is true.
* `versionmanager.purgingEnabled` (Boolean, default: false) whether to enable purging when new versions are created
* `versionmanager.purgePaths` (String[], default: {"/content"}) on which paths to purge versions when new versions are created
* `versionmanager.maxAgeDays` (int, default: 30) on purge, any version older than this value will be removed. If this value is less than 1, purging is not performed based on the age of the version
* `versionmanager.maxNumberVersions` (int, default 5) on purge, any version older than the n-th newest version will be removed. If this value is less than 1, purging is not performed based on the number of versions
* `versionmanager.minNumberVersions` (int, default 0) The minimum number of versions to keep regardless of the age. If this value is set to a value less than 1 no minimum number of versions is retained.

### Combining Retention Options
The options defining how which versions should be retained ( `maxAgeDays`, `maxNumberVersions`, `minNumberVersions`), can be combined depending on your requirements.

For example, when defining the maximum number of versions to retain AND the oldest version to retain:

* Setting:

    * `maxNumberVersions` = 7    
    * `maxAgeDays` = 30

* With:

    * 10 versions made within the past 60 days    
    * 3 of those versions created within the past 30 days

* Will mean that:

    * The last 3 versions will be retained

For example, when defining the maximum AND minimum number of versions to retain AND the oldest version to retain:

* Setting:

    * `maxNumberVersions` = 3    
    * `maxAgeDays` = 30    
    * `minNumberVersions` = 3

* With:

    * 5 versions made 60 days ago

* Will mean that:

    * 3 versions will be retained

---

## Purge Versions Tool
The **Purge Versions** tool is intended for purging the versions of a node or a hierarchy of nodes in your repository. Its primary purpose is to help you reduce the size of your repository by removing old versions of your nodes.