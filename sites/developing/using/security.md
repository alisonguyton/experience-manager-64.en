---
title: Security
seo-title: Security
description: null
seo-description: Application Security starts during the development phase
uuid: 0fef0434-6017-4c01-869e-596eadbe13fe
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: c23cd228-8b27-44a5-8527-277159cc25df
isreadyforlocalization: false
index: y
internal: n
snippet: y
---

# Security{#security}

Application Security starts during the development phase. Adobe recommends to apply the following security best practices.

### Use Request Session {#use-request-session}

Following the principle of leas privilegies, Adobe recommends that every repository access is done by using the session bound to the user request and proper access control.

### Protect against Cross-Site Scripting (XSS) {#protect-against-cross-site-scripting-xss}

Cross-site scripting (XSS) allows attackers to inject code into web pages viewed by other users. This security vulnerability can be exploited by malicious web users to bypass access controls.

AEM applies the principle of filtering all user-supplied content upon output. Preventing XSS is given the highest priority during both development and testing.

The XSS protection mechanism provided by AEM is based on the [AntiSamy Java Library](https://www.owasp.org/index.php/Category:OWASP_AntiSamy_Project) provided by [OWASP (The Open Web Application Security Project)](https://www.owasp.org/). The default AntiSamy configuration can be found at  
  
`/libs/cq/xssprotection/config.xml`  
  
It is important that you adapt this configuration to your own security needs by overlaying the configuration file. The official [AntiSamy documentation](https://www.owasp.org/index.php/Category:OWASP_AntiSamy_Project) will provide you with all the information you need in order to implement your security requirements.

>[!NOTE]
>
>We strongly recommend you always access to the XSS protection API by using the [XSSAPI provided by AEM](/developing/using/reference-materials/javadoc/com/adobe/granite/xss/XSSAPI).

Additionally, a web application firewall, such as [mod_security for Apache](https://www.modsecurity.org), can provide reliable, central control over the security of the deployment environment and protect against previously undetected cross-site scripting attacks.

### Access to Cloud Service Information {#access-to-cloud-service-information}

>[!NOTE]
>
>ACLs for the Cloud Service Information as well as the OSGi settings required to secure your instance are automated as part of the [Production Ready Mode](../../administering/using/production-ready.md). While this means that you do not need to make the configuration changes manually, it is still recommended that you review them before you go live with your deployment.

When you [integrate your AEM instance with the Adobe Marketing Cloud](../../administering/using/marketing-cloud.md) you use [Cloud Service configurations](../../developing/using/extending-cloud-config.md). Information about these configurations, together with any statistics collected are stored in the repository. We recommend that, if you are using this functionality, you review whether the default security on this information matches your requirements.

The webservicesupport module writes statistics and configuration information under:

`/etc/cloudservices`

With the default permissions:

* Author environment: `read` for `contributors`

* Publish environment: `read` for `everyone`

### Protect against Cross-Site Request Forgery Attacks {#protect-against-cross-site-request-forgery-attacks}

For more information on the security mechanisms AEM employs to mitigate CSRF attacks, see the [Sling Referrer Filter](../../administering/using/security-checklist.md#main-pars-title-1046104842) section of the Security Checklist and the [CSRF Protection Framwork documentation](../../developing/using/csrf-protection.md).  
