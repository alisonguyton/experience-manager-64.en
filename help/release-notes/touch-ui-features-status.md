---
title: Touch UI Feature Status
seo-title: Touch UI Feature Status
description: Release notes specific to Adobe Experience Manager 6.3 Touch UI.
seo-description: Release notes specific to Adobe Experience Manager 6.3 Touch UI.
uuid: d264acc1-1606-4842-bad0-a0ce9a05d1fb
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 504a4ce6-7fdc-4c05-ba34-1244a873866f
index: y
internal: n
snippet: y
---

# Touch UI Feature Status{#touch-ui-feature-status}

>[!CAUTION]
>
>With version 6.4 of AEM, the [Classic UI is deprecated](../release-notes/deprecated-removed-features.md). Adobe does not plan to make further enhancements to the Classic UI and users are encouraged to leverage the powerful new features available under the touch-enabled UI.

Starting with version 6.0, AEM introduced a new user interface referred to as the "touch-enabled UI" (also known simply as "touch UI") that is aligned to the Adobe Marketing Cloud and to the overall Adobe user interface guidelines. With near feature partity reached, this has become the standard UI in AEM with the legacy, desktop-oriented interface referred to as "classic UI."

While most capabilities are present in the touch-enabled UI, there are features that are not yet complete and will be added in future releases.

The following list shows the current status of the capabilities as implemented in AEM 6.4.

For recommendations for customers that upgrade to AEM 6.4, please see [User Interface Recommendations for Customers](../sites/deploying/using/ui-recommendations.md) for details.

>[!NOTE]
>
>Please note that this page only covers feature parity with classic UI.
>
>Capabilities added and unique to the touch-enabled UI that are not present in the classic UI are not listed.

>[!NOTE]
>
>This list strives to be complete, but should not be considered exhaustive.

## Legend {#legend}

* **Complete**: The feature is fully available in the touch-enabled UI
* **Mostly**: The feature is mostly available in the touch-enabled UI.
* **Missing**: The feature is not present in the touch-enabled UI, the classic UI has to be used to do this action.
* **Replaced**: The feature was replaced with a new implementation that works differently.
* **Removed**: The feature no longer exists in the touch-enabled UI and will not be replaced.

## Feature Status: Sites Admin {#feature-status-sites-admin}

This is a list of capabilities the classic UI Site Admin ( `/siteadmin`) has and the status in the touch-enabled UI ( `/sites.html`).

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Feature<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Comment</strong></td> 
  </tr>
  <tr>
   <td>Navigate Site Hierarchy</td> 
   <td>Complete<br /> </td> 
   <td>AEM 6.4 introduced a <a href="../sites/authoring/using/basic-handling.md#main-pars-header">content tree view</a>.</td> 
  </tr>
  <tr>
   <td>Start Workflow</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Create new page</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Create new site</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Create new launch</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Create new livecopy <br /> </td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Create folder</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Show References</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Show Publication Status</td> 
   <td>Mostly</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Search</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Copy / Paste page (Duplicate)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Move page(s)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publish page(s)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publish page(s) without replication rights</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publish later</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publish tree</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Unpublish pages(s)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Unpublish page(s) without replication rights</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Unpublish later</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Delete</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Lock/Unlock</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>View/Edit Properties</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Set Permissions on Page(s)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Version history</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Restore version</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Restore tree and restore deleted pages</td> 
   <td>Missing</td> 
   <td>Use Classic UI.</td> 
  </tr>
  <tr>
   <td>Show difference between old and current version<br /> </td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Livecopy Actions (Roll-out)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>See language copies</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Find &amp; Replace</td> 
   <td>Missing<br /> </td> 
   <td>Use Classic UI.</td> 
  </tr>
  <tr>
   <td>Notification Inbox (JCR events)</td> 
   <td>Missing</td> 
   <td>Use Classic UI. Will be replaced with different implementation.</td> 
  </tr>
 </tbody>
</table>

## Feature Status: Page Editor {#feature-status-page-editor}

This is a list of capabilities the classic UI Page Editor ( `/cf#`) has and the status in the touch-enabled ( `/editor.html`).

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Feature</strong></td> 
   <td><strong>Status</strong></td> 
   <td><strong>Comment</strong></td> 
  </tr>
  <tr>
   <td>Edit Web Pages</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit Mobile Web Pages<br /> </td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit content imported via Design Importer<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit E-Mails</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit Mobile Apps</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit Forms</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit Offers</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit Workflows Models<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>ode: Edit &amp; Preview</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Responsive Preview<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Mode: Edit Design</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Mode: Scaffolding</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Mode: Live Copy Status<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Add annotations</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Edit properties<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Roll-out Page</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Start &amp; Show Workflow</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflow package Handing</td> 
   <td>Mostly</td> 
   <td>Completely accessible in touch-enabled UI. Multiple workflow payload still presented in classic UI.<br /> </td> 
  </tr>
  <tr>
   <td>Lock/Unlock Page</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publish Page <br /> </td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Unpublish Page</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Copy Page</td> 
   <td>Removed<br /> </td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/managing-pages.md#main-pars-title-7">copy pages</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Move Page</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/managing-pages.md#main-pars-title-8">move pages</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Delete Page</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/managing-pages.md#main-pars-title-9">delete pages</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Show References</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/author-environment-tools.md#main-pars-title-11">see the detailed reference list</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Audit Log</td> 
   <td>Removed</td> 
   <td>Use Site Admin and <a href="../sites/authoring/using/author-environment-tools.md#main-pars-title-19">open activity rail</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Create Version</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/working-with-page-versions.md#main-pars-title-0">create new versions</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Restore Version</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/working-with-page-versions.md#main-pars-title-1">restore versions</a>.</td> 
  </tr>
  <tr>
   <td>Switch Launches</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/authoring/using/launches-promoting.md">switch between launches</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Translate Page</td> 
   <td>Removed</td> 
   <td>Use Site Admin to <a href="../sites/administering/using/tc-manage.md">add page to translation projects</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Timewarp (choose date/time and browse site as it then looked)<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Set Permissions</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Client Context UI<br /> </td> 
   <td>Replaced</td> 
   <td>Use the <a href="../sites/authoring/using/ch-previewing.md">ContextHub</a> UI going forward.</td> 
  </tr>
  <tr>
   <td>Content Finder for the various media types<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Component List</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Copy &amp; paste components<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>List of components in clipboard</td> 
   <td>Missing</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Undo / Redo</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Drag &amp; drop content into component placeholder</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Drag &amp; drop content directly into parsys placeholder with component auto-creation<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

<!--
Comment Type: annotation
Last Modified By: aheimoz
Last Modified Date: 2018-04-05T03:33:53.852-0400
The workflow model editor is now available in touch. See: https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/workflows-models.html
-->

<!--
Comment Type: annotation
Last Modified By: aheimoz
Last Modified Date: 2018-04-05T03:43:40.530-0400
Workflow Package Handling Still looks like classic, but it's available through touch (which is documented). See: https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/workflows-participating.html#ViewingtheWorkflowPayloadMultipleResources
-->

## Feature Status: Text, Table, and Image Editors {#feature-status-text-table-and-image-editors}

This is a list of capabilities the classic UI Text, Table, and Image Editor have and the status in the touch-enabled UI.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Feature</strong></td> 
   <td><strong>Status </strong></td> 
   <td><strong>Comment<br /> </strong></td> 
  </tr>
  <tr>
   <td>Rich Text Editor</td> 
   <td>Complete</td> 
   <td>Usable in-place, in dialog, and in full screen.</td> 
  </tr>
  <tr>
   <td>Enable/disable RTE Plug-ins</td> 
   <td>Complete<br /> </td> 
   <td>Can be done using the <a href="../sites/authoring/using/templates.md">Template Editor</a>.</td> 
  </tr>
  <tr>
   <td>Use RTE for Plain-text</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Links &amp; Anchor</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Character Map</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Copy/Paste</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Paste from Microsoft Word<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Find &amp; Replace</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Text Formats (bold, ...)</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Sub &amp; Superscript</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Justify</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Lists (bullet / numbers)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Paragraph Format</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Text Styles</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Source Editor (Edit HTML)<br /> </td> 
   <td>Complete<br /> </td> 
   <td>Only available in dialog and full screen.<br /> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Spellchecker</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Table (embedded Table Editor)</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-in: Undo/Redo<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE Plug-In: Allow in-line images</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Table Editor</td> 
   <td>Complete</td> 
   <td>Usable in-place, in dialog, and in full screen.<br /> </td> 
  </tr>
  <tr>
   <td>Drag &amp; drop Image into table cell<br /> </td> 
   <td>Complete</td> 
   <td>Usable in-line</td> 
  </tr>
  <tr>
   <td>Image Editor<br /> </td> 
   <td>Complete</td> 
   <td>Usable in-place, in dialog, and in full screen.<br /> </td> 
  </tr>
  <tr>
   <td>Enable/disable IPE Plug-ins</td> 
   <td>Complete</td> 
   <td>There is now a UI in the <a href="../sites/authoring/using/templates.md">Template Editor</a>.</td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Crop</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Flip</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Undo/Redo</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Image Map</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Rotate</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE Plug-in: Zoom</td> 
   <td>Complete<br /> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Feature Status: Tools {#feature-status-tools}

This is a list of various tools the classic UI have and the status in the touch-enabled UI.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody>
  <tr>
   <td><strong>Feature<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Comment</strong></td> 
  </tr>
  <tr>
   <td>Task Management</td> 
   <td>Replaced</td> 
   <td>6.0 introduced <a href="../sites/authoring/using/projects.md">Projects &amp; Tasks</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Workflow Inbox<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Workflow to Page Template Configuration (<span class="code">/etc/workflow/wcm/templates.html</span>)</td> 
   <td>Missing<br /> </td> 
   <td>Use Classic UI.</td> 
  </tr>
  <tr>
   <td>Tagging Admin UI<br /> </td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>MSM/Blueprint Control Center</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Blueprint Manager UI</td> 
   <td>Complete</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Roll-out Configuration UI</td> 
   <td>Missing</td> 
   <td>Use Classic UI.</td> 
  </tr>
  <tr>
   <td>User, Groups &amp; Permissions UI<br /> </td> 
   <td>Mostly Complete<br /> </td> 
   <td>For advanced permission editing use Classic UI.<br /> </td> 
  </tr>
  <tr>
   <td>Purge Versions (<span class="code">/etc/versioning/purge.html</span>)</td> 
   <td>Missing</td> 
   <td>Use Classic UI.</td> 
  </tr>
  <tr>
   <td>External Link Checker (<span class="code">/etc/linkchecker.html</span>)</td> 
   <td>Missing</td> 
   <td>Use Classic UI.<br /> </td> 
  </tr>
  <tr>
   <td>Bulk Editor (<span class="code">/etc/importers/bulkeditor.html</span>)</td> 
   <td>Missing<br /> </td> 
   <td>Use Classic UI.</td> 
  </tr>
 </tbody>
</table>
