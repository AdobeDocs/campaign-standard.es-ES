---
title: 'Creación de un formulario de campaña en Experience Manager '
seo-title: 'Creación de un formulario de campaña en Experience Manager '
description: 'Creación de un formulario de campaña en Experience Manager '
seo-description: Con la integración de Adobe Experience Manager, puede crear formularios directamente en AEM para crear y actualizar perfiles o gestionar suscripciones.
page-status-flag: no activado nunca
uuid: 43057 f 81-d 47 d -4 b 96-b 150-217 c 289 cd 608 cd 608
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4 a 8 b 5807-87 dd -4 db 4-bd 67-890 f 0 adae 932
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eed2e3597548c97345f51fe62dd2b56af5042e87

---


# Creating a Campaign form in Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puede crear "formularios" en los sitios de AEM y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones a un servicio.

Para crear un formulario de Adobe Campaign en su sitio de AEM:

1. In your AEM site, create a new page based on the **Adobe Campaign Profile** template.

   ![](assets/aem_content_forms.png)

1. In the page properties, select the **[!UICONTROL Cloud Service]** corresponding to your Adobe Campaign instance.

   ![](assets/aem_content_forms_2.png)

1. Select the form type from the **[!UICONTROL Form Start]** component:

   * **Adobe Campaign: Guardar perfil**
   * **Adobe Campaign: Suscribirse a Servicios**
   * **Adobe Campaign: Cancelar suscripción de Servicios**

1. Edite el contenido del formulario agregando diferentes campos y componentes que pueda asignar a los campos de la base de datos de Adobe Campaign.
1. Pruebe y publique el formulario para que sea accesible en su sitio de AEM.

For more information, refer to the [detailed documentation](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/adobe-campaign-forms.html).
