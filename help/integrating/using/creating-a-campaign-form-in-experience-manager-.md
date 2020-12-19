---
solution: Campaign Standard
product: campaign
title: 'Creación de un formulario de Campaign en Experience Manager '
description: Con la integración de Adobe Experience Manager, puede crear formularios directamente en AEM para crear y actualizar perfiles o administrar suscripciones.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Creación de un formulario de Campaign en Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puede crear &quot;formularios&quot; en los sitios AEM y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones de un servicio.

Para crear un formulario de Adobe Campaign en el sitio AEM:

1. En el sitio AEM, cree una nueva página basada en la plantilla **Adobe Campaign Perfil**.

   ![](assets/aem_content_forms.png)

1. En las propiedades de página, seleccione el **[!UICONTROL Cloud Service]** correspondiente a la instancia de Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleccione el tipo de formulario del componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Guardar perfil**
   * **Adobe Campaign: Suscripción a Servicios**
   * **Adobe Campaign: Cancelar suscripción a Servicios**

1. Edite el contenido del formulario agregando distintos campos y componentes que puede asignar a los campos de la base de datos de Adobe Campaign.
1. Pruebe y publique el formulario para que sea accesible en su sitio AEM.

Para obtener más información, consulte la [documentación detallada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
