---
title: Security Checklist
seo-title: Security Checklist
description: Learn about the various security considerations when configuring and deploying AEM.
seo-description: Learn about the various security considerations when configuring and deploying AEM.
uuid: 3f3c5a3b-0aeb-45eb-8338-a7bb51aa4f8a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 5cf4f1ad-c02a-4446-a861-5fcdc1c48c93
index: y
internal: n
snippet: y
---

# Security Checklist{#security-checklist}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:54.825-0500
<p>I think we need to beef this up a bit.</p>
-->

This section deals with various steps that you should take to ensure that your AEM installation is secure when deployed. The checklist is meant to be applied from top to bottom.

>[!NOTE]
>
>Further information [is also available about the most dangerous security threats as published by Open Web Application Security Project (OWASP)](https://www.owasp.org/index.php/OWASP_Top_Ten_Project).

>[!NOTE]
>
>There are some additional [security considerations](../../../sites/developing/using/dev-guidelines-bestpractices.md#securityconsiderations) applicable at the development phase.

## Main Security Measures {#main-security-measures}

### Run AEM in Production Ready Mode {#run-aem-in-production-ready-mode}

For more information, see [Running AEM in Production Ready Mode](../../../sites/administering/using/production-ready.md).

### Enable HTTPS for transport layer security {#enable-https-for-transport-layer-security}

Enabling the HTTPS transport layer on both author and publish instances is mandatory for having a secure instance.

>[!NOTE]
>
>See the [Enabling HTTP Over SSL](../../../sites/deploying/using/config-ssl.md) section for more information.

### Install Security Hotfixes {#install-security-hotfixes}

Ensure that you have installed the latest [Security Hotfixes provided by Adobe](https://helpx.adobe.com/experience-manager/kb/aem63-available-hotfixes.html).

### Change Default Passwords For the AEM and OSGi Console Admin Accounts {#change-default-passwords-for-the-aem-and-osgi-console-admin-accounts}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:55.067-0500
<p>I think this entire sections need to be simplied. I think the procedure must be somewhere and actually I'm pretty sure we describe this procedure many times in the documentation.<br /> </p>
-->

Adobe strongly recommends that after installation you change the password for the privileged [**AEM** `admin` accounts](#changingthecqadminpassword) (on all instances).

These accounts include:

* The AEM `admin` account  
  Once you have changed the password for the AEM admin account, you will need to use the new password when accessing CRX.

* The `admin` password for the OSGi Web console  
  This change will also be applied to the admin account used for accessing the Web console, so you will need to use the same password when accessing that.

These two accounts use separate credentials and having distinct, strong password for each is vital to a secure deployment.

#### Changing the AEM admin password {#changing-the-aem-admin-password}

The password for the AEM admin account can be changed via the [Granite Operations - Users](../../../sites/administering/using/granite-user-group-admin.md) console.

Here you can edit the `admin` account and [change the password](../../../sites/administering/using/granite-user-group-admin.md#changingthepasswordforanexistinguser).

>[!NOTE]
>
>Changing the admin account also changes the OSGi web console account. After changing the admin account, you should then change the OSGi account to something different.

#### Importance of Changing the OSGi Web Console Password {#importance-of-changing-the-osgi-web-console-password}

Aside from the AEM `admin` account, failing to change the default password for the OSGi web console password can lead to:

* Exposure of the server with a default password during startup and shutdown (that can take minutes for large servers);
* Exposure of the server when the repository is down/restarting bundle - and OSGI is running.

For more information on changing the web console password, see [Changing the OSGi web console admin password](../../../sites/administering/using/security-checklist.md#main-pars-title-11-iclxdv-refd) below.

<!--
Comment Type: draft

<note type="note">
<p>To change the password of the admin account you must use the specific procedure - <a href="#changingthecqadminpassword">Changing the AEM admin password</a>.<br /> </p>
<p>To change the password for the other AEM user accounts you can use the <a href="../../../sites/administering/using/security.md#changingauserpassword">User Management</a> console.<br /> </p>
</note>
-->

<!--
Comment Type: draft

<p>Adobe also recommends that you either remove the example user <span class="code">author</span>, or (at minimum) disable it by changing the password; see the <a href="../../../sites/administering/using/security.md#changingauserpassword">User Management documentation</a> for details on changing a user password.</p>
-->

<!--
Comment Type: draft

<note type="note">
<p>Further actions are described in the table <a href="../../../sites/administering/using/security.md#defaultusersandgroups">Default Users and Groups</a>, which gives an overview of the default users and groups included in the standard installation.</p>
</note>
-->

#### Changing the OSGi web console admin password {#changing-the-osgi-web-console-admin-password}

You must also change the password used for accessing the Web console. This is done by configuring the following properties of the [Apache Felix OSGi Management Console](../../../sites/deploying/using/osgi-configuration-settings.md#apachefelixosgimanagementconsole):

**User Name** and **Password**, the credentials for accessing the Apache Felix Web Management Console itself.  
The password must be changed after the initial installation to ensure the security of your instance.

To do this:

1. Navigate to the web console at `<server>:<port>/system/console/configMgr`.
1. Navigate to** Apache Felix OSGi Management Console** and change the **user name** and **password**.

   ![](assets/chlimage_1-201.png)

1. Click **Save**.

### Implement Custom Error Handler {#implement-custom-error-handler}

Adobe recommends to define custom error handler pages, especially for 404 and 500 HTTP Response codes in order to prevent information disclosure.

>[!NOTE]
>
>See [How can I create custom scripts or error handlers](https://helpx.adobe.com/experience-manager/kb/CustomErrorHandling.html) knowledge base article for more details.

### Complete Dispatcher Security Checklist {#complete-dispatcher-security-checklist}

AEM Dispatcher is a critical piece of your infrastructure. Adobe strongly recommend that you complete the [dispatcher security checklist](/content/help/en/experience-manager/dispatcher/using/security-checklist).

>[!CAUTION]
>
>Using the Dispatcher you must disable the ".form" selector.

## Verification Steps {#verification-steps}

### Configure replication and transport users {#configure-replication-and-transport-users}

A standard installation of AEM specifies `admin` as the user for transport credentials within the default [replication agents](../../../sites/deploying/using/replication.md). Also, the admin user is used to source the replication on the author system.

For security considerations, both should be changed to reflect the particular use case at hand, with the following two aspects in mind:

* The **transport user** should not be the admin user. Rather, set up a user on the publish system that has only access rights to the relevant portions of the publish system and use that user's credentials for the transport.  
  
  You can start from the bundled replication-receiver user and configure this user's access rights to match your situation

* The **replication user** or **Agent User Id** should also not be the admin user, but a user who can only see content that is supposed to be replicated. The replication user is used to collect the content to be replicated on the author system before it is sent to the publisher.

### Check the Operations Dashboard Security Health Checks {#check-the-operations-dashboard-security-health-checks}

AEM 6 introduces the new Operations Dashboard, aimed at aiding system operators troubleshoot problems and monitor the health of an instance.

The dashboard also comes with a collection of security health checks. It is recommended you check the status of all the security health checks before going live with your production instance. For more information, consult the [Operations Dashboard documentation](../../../sites/administering/using/operations-dashboard.md).

### Check if Example Content is Present {#check-if-example-content-is-present}

All example content and users (e.g. the Geometrixx project and its components) should be uninstalled and deleted completely on a productive system before making it publicly accessible.

>[!NOTE]
>
>The sample Geometrixx applications are removed if this instance is running in [Production Ready Mode](../../../sites/administering/using/production-ready.md). If, for any reason, this is not the case, you can uninstall the `cq-geometrixx-all-pkg` package as described in [Uninstalling Packages](../../../sites/administering/using/package-manager.md#uninstallingpackages). You can then delete all geometrixx packages using the same user interface.

### Check if the CRX development bundles are present {#check-if-the-crx-development-bundles-are-present}

These development OSGi bundles should be uninstalled on both author and publish productive systems before making them accessible.

* Adobe CRXDE Support (com.adobe.granite.crxde-support)
* Adobe Granite CRX Explorer (com.adobe.granite.crx-explorer)
* Adobe Granite CRXDE Lite (com.adobe.granite.crxde-lite)

### Check if the Sling development bundle is present {#check-if-the-sling-development-bundle-is-present}

The [AEM Developer Tools for Eclipse](../../../sites/developing/using/aem-eclipse.md) deployes the Apache Sling Tooling Support Install (org.apache.sling.tooling.support.install).

This OSGi bundle should be uninstalled on both author and publish productive systems before making them accessible.

### Protect against Cross-Site Request Forgery {#protect-against-cross-site-request-forgery}

#### The CSRF Protection Framework {#the-csrf-protection-framework}

AEM 6.1 ships with a mechanism that helps protect agains Cross-Site Request Forgery attacks, called the **CSRF Protection Framework**. For more information on how to use it, consult the [documentation](../../../sites/developing/using/csrf-protection.md).

#### The Sling Referrer Filter {#the-sling-referrer-filter}

To address known security issues with Cross-Site Request Forgery (CSRF) in CRX WebDAV and Apache Sling you need to add configurations for the Referrer filter in order to use it.

The referrer filter service is an OSGi service that allows you to configure:

* which http methods should be filtered
* whether an empty referrer header is allowed  
* and a white list of servers to be allowed in addition to the server host.

By default, all variations of localhost and the current host names the server is bound to are in the white list.

To configure the referrer filter service:

1. Open the Apache Felix console (**Configurations**) at:  
   `http://<*server*>:<*port_number*>/system/console/configMgr`  

1. Login as `admin`.
1. In the **Configurations** menu, select:

   `Apache Sling Referrer Filter`

1. In the `Allow Hosts` field, enter all hosts that are allowed as a referrer. Each entry needs to be of the form  
   &lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;   
   For example:

    * `http://allowed.server:80` allows all requests from this server with the given port.
    * If you also want to allow https requests, you have to enter a second line.
    * If you allow all ports from that server you can use `0` as the port number.

1. Check the `Allow Empty` field, if you want to allow empty/missing referrer headers.

   >[!CAUTION]
   >
   >It is recommended to provide a referrer while using commandline tools such as `cURL` instead of allowing an empty value as it might expose your system to CSRF attacks.

1. Edit the methods this filter should use for checks with the `Filter Methods` field.

1. Click **Save** to save your changes.

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-AAC0465A528DC04F0A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:56.096-0500
<p>To link to the main CRX Authentication Handler article when it's done.</p>
-->

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:56.113-0500
<p>This was fixed a long time ago if I remember correctly and understood what Angela said this week. Better check twice, though.</p>
-->

<!--
Comment Type: draft

<h2>Default Access to User Profile(s) is everyone</h2>
-->

<!--
Comment Type: draft

<p>By default, <span class="code">everyone</span> (the built-in group) has read access to all user profile(s)<span class="code"></span>. If such access is not appropriate for your installation you can change these default settings. See <a href="../../../sites/administering/using/identity-management.md#main-pars-par5">Profiles and User Accounts</a>.</p>
-->

### OSGI Settings {#osgi-settings}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:56.176-0500
<p>To be reviewed and simplied, see https://jira.corp.adobe.com/browse/DOC-5392<br /> </p>
-->

Some OSGI settings are set by default to allow easier debugging of the application. These need to be changed on your publish and author productive instances to avoid internal information leaking to the public.

>[!NOTE]
>
>All of the below settings with the exception of **The Day CQ WCM Debug Filter** are automatically covered by the [Production Ready Mode](../../../sites/administering/using/production-ready.md). Because of this, we recommend reviewing all the settings before deploying your instance in a productive environment.

For each of the following services the specified settings need to be changed:

* [Adobe Granite HTML Library Manager](../../../sites/deploying/using/osgi-configuration-settings.md#daycqhtmllibrarymanager):

    * enable **Minify** (to remove CRLF and whitespace characters).
    * enable **Gzip** (to allow files to be gzipped and accessed with one request).
    * disable **Debug**
    * disable **Timing**

* [Day CQ WCM Debug Filter](../../../sites/deploying/using/osgi-configuration-settings.md#daycqwcmdebugfilter):

    * uncheck **Enable**

* [Day CQ WCM Filter](../../../sites/deploying/using/osgi-configuration-settings.md#daycqwcmfilter):

    * on publish only, set **WCM Mode** to "disabled"

* [Apache Sling Java Script Handler](../../../sites/deploying/using/osgi-configuration-settings.md#apacheslingjavascripthandler):

    * disable **Generate Debug Info**

* [Apache Sling JSP Script Handler](../../../sites/deploying/using/osgi-configuration-settings.md#apacheslingjspscripthandler):

    * disable **Generate Debug Info**
    * disable **Mapped Content**

For further details see [OSGi Configuration Settings](../../../sites/deploying/using/osgi-configuration-settings.md).

When working with AEM there are several methods of managing the configuration settings for such services; see [Configuring OSGi](../../../sites/deploying/using/configuring-osgi.md) for more details and the recommended practices.

## Further Readings {#further-readings}

### Mitigate Denial of Service (DoS) Attacks {#mitigate-denial-of-service-dos-attacks}

A denial of service (DoS) attack is an attempt to make a computer resource unavailable to its intended users. This is often done by overloading the resource; for example:

* With a flood of requests from an external source.
* With a request for more information than the system can successfully deliver.  
  For example, a JSON representation of the entire repository.  

* By requesting a content page with an unlimited number of URLs, The URL can include a handle, some selectors, an extension, and a suffix - any of which can be modified.  
  For example, `.../en.html` can also be requested as: ``

    * `.../en.ExtensionDosAttack`
    * `.../en.SelectorDosAttack.html`
    * `.../en.html/SuffixDosAttack`

  All valid variations (e.g. return a `200` response and are configured to be cached) will be cached by the dispatcher, eventually leading to a full file system and no service for further requests.

There are many points of configuration for preventing such attacks, here we only discuss those directly related to AEM.

**Configuring Sling to Prevent DoS**

Sling is *content-centric*. This means that processing is focused on the content as each (HTTP) request is mapped onto content in the form of a JCR resource (a repository node):

* The first target is the resource (JCR node) holding the content.
* Secondly, the renderer, or script, is located from the resource properties in combination with certain parts of the request (e.g. selectors and/or the extension).

>[!NOTE]
>
>This is covered in more detail under [Sling Request Processing](../../../sites/developing/using/the-basics.md#slingrequestprocessing).

This approach makes Sling very powerful and very flexible, but as always it is the flexibility that needs to be carefully managed.

To help prevent DoS misuse you can:

1. Incorporate controls at the application level; due to the number of variations possible a default configuration is not feasible.

   In your application you should:

    * Control the selectors in your application, so that you *only* serve the explicit selectors needed and return `404` for all others.
    
    * Prevent the output of an unlimited number of content nodes.

1. Check the configuration of the default renderers, which can be a problem area.

    * In particular the JSON renderer which can transverse the tree structure over multiple levels.  
      For example, the request:  
      `http://localhost:4502/.json`  
      could dump the whole repository in a JSON representation. This would cause significant server problems. For this reason Sling sets a limit on the number of maximum results. To limit the depth of the JSON rendering you can set the value for:  
      **JSON Max results** ( `json.maximumresults`)  
      in the configuration for the [Apache Sling GET Servlet](../../../sites/deploying/using/osgi-configuration-settings.md#apacheslinggetservlet). When this limit is exceeded the rendering will be collapsed. The default value for Sling within AEM is `200`.  
    
    * As a preventive measure disable the other default renderers (HTML, plain text, XML). Again by configuring the [Apache Sling GET Servlet](../../../sites/deploying/using/osgi-configuration-settings.md#apacheslinggetservlet).

   >[!CAUTION]
   >
   >Do not disable the JSON renderer, this is required for the normal operation of AEM.

1. Use a firewall to filter access to your instance.

    * The use of an operating system level firewall is necessary in order to filter access to points of your instance that might lead to denial of service attacks if left unprotected.

**Mitigate Against DoS Caused by Using Form Selectors**

>[!NOTE]
>
>This mitigation should be performed only on AEM environments that are not using Forms.

Since AEM does not provide out of the box indexes for the `FormChooserServlet`, using form selectors in queries will trigger a costly repository traversal, usually grinding the AEM instance to a halt. Form selectors can be detected by the presence of the **&#42;.form.&#42;** string in queries.

In order to mitigate this, please follow the below steps:

1. Go to the Web Console by pointing your browser to *http://serveraddress:serverport/system/console/configMgr* 

1. Search for **Day CQ WCM Form Chooser Servlet**
1. After you click on the entry, disable the **Advanced Search Require** in the following window.  

1. Click **Save**.

### Disable WebDAV {#disable-webdav}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:56.554-0500
<p>There is no known WebDAV vulns. It is however recommended to turn it off in order to reduce the attack surface.<br /> </p>
-->

WebDAV should be disabled on both the author and publish environments. This can be done by stopping the appropriate OSGi bundles.

1. Connect to the **Felix Management Console** running on:

   `http://<*host*>:<*port*>/system/console`

   For example `http://localhost:4503/system/console/bundles`.

1. In the list of bundles, find the bundle named:

   `Apache Sling Simple WebDAV Access to repositories (org.apache.sling.jcr.webdav)`

1. Click the stop button (in the Actions column) to stop this bundle.  

1. Again in the list of bundles, find the bundle named:

   `Apache Sling DavEx Access to repositories (org.apache.sling.jcr.davex)`

1. Click the stop button to stop this bundle.

   >[!NOTE]
   >
   >A restart of AEM is not required.

### Verify That You Are Not Disclosing Personally Identifiable Information In the Users Home Path {#verify-that-you-are-not-disclosing-personally-identifiable-information-in-the-users-home-path}

It is important you protect your users by making sure that you do not expose any personally indetifiable information in the repository users home path.

Since AEM 6.1, the way user (also known as authorizable) ID node names are stored is changed with a new implementation of the `AuthorizableNodeName` interface. The new interface will no longer expose the user ID in the node name, but will generate a random name instead.

No configuration needs to be performed in order to enable it, as this is now the default way of generating authorizable IDs in AEM.

Although not recommended, you can disable it in case you need the old implementation for backwards compatibility with your exsiting applications. In order to do this, you need to:

1. Go to the Web Console and remove the** org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName** entry from property **requiredServicePids** in **Apache Jackrabbit Oak SecurityProvider**.

   You can also find the Oak Security Provider by looking for the **org.apache.jackrabbit.oak.security.internal.SecurityProviderRegistration** PID in the OSGi configurations.

1. Delete the **Apache Jackrabbit Oak Random Authorizable Node Name** OSGi configuration from the Web Console.

   For easier lookup, note that the PID for this configuration is **org.apache.jackrabbit.oak.security.user.RandomAuthorizableNodeName**.

>[!NOTE]
>
>For more information, see the Oak documentation on [Authorizable Node Name Generation](https://jackrabbit.apache.org/oak/docs/security/user/authorizablenodename.html).

### Prevent Clickjacking {#prevent-clickjacking}

<!--
Comment Type: remark
Last Modified By: unknown unknown (ims-author-00AF43764F54BE740A490D44@AdobeID)
Last Modified Date: 2018-02-26T17:04:56.972-0500
<p>Probably not needed since it's in the dispatcher checklist... or maybe just for author as dispatcher is not strongly recommended there.<br /> </p>
-->

To prevent clickjacking we recommend that you configure your webserver to provide the `X-FRAME-OPTIONS` HTTP header set to `SAMEORIGIN`.  
  
For more [information on clickjacking please see the OWASP site](https://www.owasp.org/index.php/Clickjacking).

### Make Sure You Properly Replicate Encryption Keys When Needed {#make-sure-you-properly-replicate-encryption-keys-when-needed}

Certain AEM features and authentication schemes require that you replicate your encryption keys across all AEM instances.

Before you do this, please take note that key replication is done differently between versions because the way in which keys are stored is different between 6.3 and older versions.

See below for more information.

#### Replicating Keys for AEM 6.3 {#replicating-keys-for-aem}

Whereas in older versions the replication keys were stored in the repository, beginning with AEM 6.3 they are stored on the filesystem.

Therefore, in order to replicate your keys across instances you need to copy them from the source instance to the target instances' location on the filesystem.

More specifically, you need to:

1. Access the AEM instance, typically an author instance, that contains the key material to copy;
1. Locate the com.adobe.granite.crypto.file bundle in the local file system. For example, under this path:

    * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21`

   The `bundle.info` file inside each folder will identify the bundle name.

1. Navigate to the data folder. For example:

    * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`

1. Copy the HMAC and master files.
1. Then, go to the target instance you want to duplicate the HMAC key to, and navigate to the data folder. For example:

    * `<publish-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`

1. Paste the two files you previously copied.
1. [Refresh the Crypto Bundle](../../../communities/using/deploy-communities.md#refreshthegranitecryptobundle) if the target instance is already running.
1. Repeat the above steps for all instances you want to replicate the key to.

>[!NOTE]
>
>You can revert to the pre 6.3 method of storing keys by adding the below parameter when you first install AEM:
>
>`-Dcom.adobe.granite.crypto.file.disable=true`

#### Replicating Keys for AEM 6.2 and Older Versions {#replicating-keys-for-aem-and-older-versions}

In AEM 6.2 and older versions, the keys are stored in the repository under the `/etc/key` node.

The recommended way to securely replicate the keys across your instances is to only replicate this node. You can selectively replicate nodes via CRXDE Lite:

1. Open CRXDE Lite by going to *http://serrveraddress:4502/crx/de/index.jsp*
1. Select the `/etc/key` node. ``
1. Go to the **Replication** tab.
1. Press the **Replication** button.

### Perform a Penetration Test {#perform-a-penetration-test}

Adobe strongly recommends to perform a penetration test of your AEM infrastructure before going on production.

### Development Best Practices {#development-best-practices}

It is critical that new development are following the [Security Best Practices](../../../sites/developing/using/security.md) to ensure your AEM environement stays safe.