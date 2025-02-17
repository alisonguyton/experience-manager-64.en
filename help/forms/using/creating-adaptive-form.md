---
title: Creating an adaptive form
seo-title: Creating an adaptive form
description: How to create an adaptive form using AEM Forms. Adaptive forms are responsive HTML5 forms that streamline information gathering and processing.
seo-description: How to create an adaptive form using AEM Forms. Adaptive forms are responsive HTML5 forms that streamline information gathering and processing.
uuid: 444f461a-9e88-4385-b5ee-e985067ab7bc
content-type: reference
topic-tags: author
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: f06b8cb2-6f98-465f-beec-1e91e3f45707
---

# Creating an adaptive form {#creating-an-adaptive-form}

## <strong>Create an adaptive form</strong> {#strong-create-an-adaptive-form-strong}

Follow these steps to create an adaptive form.

1. Access AEM Forms Author instance at `https://*[server]:[port]*/*<custom-context-if-any*>.`

   ```
   
   ```

1. Enter your credentials on the AEM login page.

   After you are logged in, in the top-left corner, tap **[!UICONTROL Adobe Experience Manager &gt; Forms &gt; Forms & Documents]**.

   >[!NOTE]
   >
   >For a default installation, the login is `admin` and the password is `admin`.

1. Tap **[!UICONTROL Create]** and select **[!UICONTROL Adaptive Form]**.
1. An option to select a template appears. For more information about templates, see [Adaptive form templates](/help/forms/using/creating-adaptive-form.md#p-adaptive-form-templates-p). Tap a template to select it and tap Next.
1. An option to 'Add Properties' appears. Specify the values for following property fields. The Title and Name fields are mandatory:

    * **[!UICONTROL Title:]** Specifies the display name of the form. The title helps you identify the form in the AEM Forms user interface.
    * **[!UICONTROL Name:]** Specifies the name of the form. A node with the specified name is created in the repository. As you start typing a title, value for the name field is automatically generated. You can change the suggested value. The name field can include only alphanumeric characters, hyphens, and underscores. All the invalid inputs are replaced with a hyphen.
    * **[!UICONTROL Description:]** Specifies the detailed information about the form. 
    * **[!UICONTROL Tags:]** Specifies tags to uniquely identify the adaptive form. Tags help in searching the form. To create tags, type new tag names in the **Tags **box.

1. You can create an adaptive form based on one of following form models:

    * [Form data model](#fdm)
    * [XFA form template](/help/forms/using/creating-adaptive-form.md#p-create-an-adaptive-form-based-on-an-xfa-form-template-p)
    * [XML or JSON schema](/help/forms/using/creating-adaptive-form.md#p-create-an-adaptive-form-based-on-xml-or-json-schema-p)
    * None or without any form model

   You can configure these from the **[!UICONTROL Form Model]** tab on the **[!UICONTROL Add Properties]** page. By default, the form model selected is **[!UICONTROL None]**.

1. Tap **Create**. An adaptive form is created and a dialog to open the form for editing appears.

   Once you have finished specifying all the properties, click **[!UICONTROL Create]**. An adaptive form is created and a dialog to open the form for editing appears. 

   Once you have finished specifying all the properties, click **[!UICONTROL Create]**. An adaptive form is created and a dialog to open the form for editing appears.  

1. Tap **[!UICONTROL Open]** to open the newly created form in a new tab. The form opens for editing and displays the contents available in the template. It also displays the sidebar to customize the newly created form according to the needs.

   Based on the type of adaptive form, the form elements present in the associated XFA form template, XML schema, or JSON schema are displayed in the **[!UICONTROL Data Model Objects]** tab of the **[!UICONTROL Content Browser]** in the sidebar. You can also drag-drop these elements to build your adaptive form.

   For information about adaptive form authoring interface and available components, see [Introduction to authoring adaptive forms](/help/forms/using/introduction-forms-authoring.md).

   >[!NOTE] {grayBox="true"}
   >
   >Allow pop up windows in your browser to open the newly created form in a new tab.

## Create an adaptive form based on a form data model {#fdm}

[AEM Forms data integration](/help/forms/using/data-integration.md) lets you integrate multiple data sources and bring their entities and services together to create a form data model. It is an extension of JSON schema. You can use a form data model to create an adaptive form. The entities or data model objects configured in a form data model are available as data model objects for form authoring. They are bound to respective data sources and used to prefill a form and write submitted data back to the respective data sources. You can also invoke services configured in a form data model using adaptive form rules.

To use a form data model for creating an adaptive form:

1. In Form Model tab on Add Properties screen, select **[!UICONTROL Form Data Model]** in the **[!UICONTROL Select From]** drop-down list.

   ![create-af-1-1](assets/create-af-1-1.png)

1. Tap to expand **[!UICONTROL Select Form Data Model]**. All available form data models are listed.

   Select a from data model.

   ![create-af-2-1](assets/create-af-2-1.png)

>[!NOTE]
>
>You can also change the form data model for an adaptive form. For detailed steps, see [Edit Form Model properties of an adaptive form](#edit-form-model).

## Create an adaptive form based on an XFA Form template {#create-an-adaptive-form-based-on-an-xfa-form-template}

You can repurpose your XFA form templates to create adaptive forms. To repurpose, upload and associate an XFA form template with an adaptive form. The elements of the Form Template (XFA form) are made available for use in the content finder at the time of adaptive form authoring. From the Content Finder, you can drag-and-drop the form template elements on the form.

>[!NOTE]
>
>[Upload the XFA Form Template](/help/forms/using/get-xdp-pdf-documents-aem.md) to AEM Forms before you start creating an adaptive form based on the form template.

Do the following to use an XFA form template as form model for your adaptive form:

1. On the **[!UICONTROL Add Properties]** page, open the **[!UICONTROL Form Model]** tab.
1. In the Form Model tab, from the drop-down list, select **[!UICONTROL Form Templates]**. All the form templates that are uploaded to the repository via AEM Forms UI are listed for selection. Select a template from the list.

   ![Associate XFA Form Template with an Adaptive Form](assets/form_model_xfa_associate.png)
**Figure:** *Selecting a form template*

   >[!NOTE]
   >
   >You can also change the form template for an adaptive form. For detailed steps, see [Edit Form Model properties of an adaptive form](#edit-form-model).

## Create an adaptive form based on XML or JSON schema {#create-an-adaptive-form-based-on-xml-or-json-schema}

XML and JSON schemas represent the structure in which data is produced or consumed by the back-end system in your organization. You can associate a schema to an adaptive form and use its elements to add dynamic content to the adaptive form. The elements of the schema are available in the Data Model Object tab of the content browser for authoring adaptive forms. You can drag-drop the schema elements to build the form.

See the following documents to understand how to design XML or JSON schema for authoring adaptive forms.

* [Creating adaptive forms using XML schema](/help/forms/using/adaptive-form-xml-schema-form-model.md)
* [Creating adaptive forms using JSON schema](/help/forms/using/adaptive-form-json-schema-form-model.md)

Do the following to use XML or JSON schema as form model for an adaptive form:

1. On the **[!UICONTROL Add Properties]** step of adaptive form creation page, tap on the **[!UICONTROL Form Model]** tab.
1. In the Form Model tab, select **[!UICONTROL Schema]** from the **[!UICONTROL Select From]** drop-down field.

1. Tap **[!UICONTROL Select Schema]** and do one of the following:

    * **[!UICONTROL Upload from disk]** - Select this option and tap Upload Schema Definition to browse and upload an XML schema or JSON schema from your file system. The uploaded schema file resides with the form and is not accessible to other adaptive forms.
    * **[!UICONTROL Search in repository]** - Select this option to select from the list of schema definition files available in the repository. Select the XML or JSON schema file as form model. The selected schema will be associated with the form by reference and will be accessible for use in other adaptive forms.

   >[!CAUTION] {grayBox="true"}
   >
   >Ensure that the JSON schema filename ends with **.schema.json**. For example: mySchema.schema.json

   ![Selecting XML or JSON schema](assets/upload-schema.png)
**Figure:** *Selecting XML or JSON schema*

1. (For XML schema only) After you select or upload an XML Schema, specify a root element of the selected XSD file to map with the adaptive form.

   ![Selecting XSD root element](assets/xsd-root-element.png)
**Figure:** *Selecting XSD root element*

>[!NOTE]
>
>You can also change the schema for an adaptive form. For detailed steps, see [Edit Form Model properties of an adaptive form](#edit-form-model).

## Adaptive form templates {#adaptive-form-templates}

A template provides a basic structure and defines appearance (layouts and styles) of an adaptive form. It has pre-formatted components containing certain properties and content structure. Out of the box, AEM Forms provides some adaptive form templates. To get the complete template package including advanced templates, you need to install the AEM Forms add-on package. For more information, see [Installing AEM Forms add-on package](/help/forms/using/installing-configuring-aem-forms-osgi.md).

In addition, you can use the template editor to create your own templates. For more information about working with templates, see [Adaptive form templates](/help/forms/using/template-editor.md).

>[!NOTE]
>
>When you open an adaptive form created using the advanced template for editing, an error message appears. The advanced template has a Signature Step component and Adobe Sign is enabled for it by default. Create and select an [Adobe Sign cloud configuration](/help/forms/using/adobe-sign-integration-adaptive-forms.md) and [configure a signer](/help/forms/using/working-with-adobe-sign.md#main-pars-header-1374317451) to resolve the error.

## Edit Form Model properties of an adaptive form {#edit-form-model}

Adaptive forms are created without a form model (using the None option for form model) or using a form model such as a form template, XML schema or JSON schema, or form data model. You can change the form model for an adaptive form from None to another form model. For adaptive form based on a form model, you can choose another form template, XML schema, JSON schema, or form data model for the same form model. However, you cannot change from one form model to another.

1. Select the adaptive form and tap the **Properties **icon.
1. Open the **[!UICONTROL Form Model]** tab and do one the following.

    * If the adaptive form is without a form model, you can choose another form model and accordingly select a form template, XML or JSON schema, or form data model.
    * If the adaptive form is based on a form model, you can choose another form template, XML or JSON schema, or form data model for the same form model.

1. Tap **[!UICONTROL Save]** to save the properties.

## Auto save an adaptive form {#auto-save-an-adaptive-form}

By default, the contents of an adaptive form are saved on a user action, such as on pressing the save button. You can also configure an adaptive form to automatically start saving the content based on an event or time-interval. The auto save option is helpful in:

* Automatically saving the content for anonymous and logged-in users
* Saving the content of a form without or minimal user intervention
* Start saving content of a form based on a user event
* Saving the content of a form repeatedly after a specified time interval

### Enable Auto Save for an adaptive form {#enable-auto-save-for-an-adaptive-form}

By default, the auto save option is not enabled. You can enable the auto save option from the Auto Save tab of an adaptive form. The Auto Save tab also provides several other configuration options. Perform the following steps to enable and configure the auto save option for an adaptive form: 
