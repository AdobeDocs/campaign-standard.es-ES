---
title: 'Creación de un formulario de Campaign en Experience Manager '
description: Con la integración de Adobe Experience Manager, puede crear formularios directamente en AEM para crear y actualizar perfiles o administrar suscripciones.
page-status-flag: never-activated
uuid: 43057f81-d47d-4b96-b150-217c289cd608
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 4a8b5807-87dd-4db4-bd67-890f0adae932
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 12%

---


# Creación de un formulario de Campaign en Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puede crear &quot;formularios&quot; en los sitios AEM y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones de un servicio.

Para crear un formulario de Adobe Campaign en el sitio AEM:

1. En el sitio AEM, cree una nueva página basada en la plantilla de **Adobe Campaign Perfil** .

   ![](assets/aem_content_forms.png)

1. En las propiedades de página, seleccione la **[!UICONTROL Cloud Service]** correspondiente a la instancia de Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleccione el tipo de formulario del **[!UICONTROL Form Start]** componente:

   * **Adobe Campaign: Guardar perfil**
   * **Adobe Campaign: Suscripción a Servicios**
   * **Adobe Campaign: Cancelar suscripción a Servicios**

1. Edite el contenido del formulario agregando distintos campos y componentes que puede asignar a los campos de la base de datos de Adobe Campaign.
1. Pruebe y publique el formulario para que sea accesible en su sitio AEM.

Para obtener más información, consulte la [documentación detallada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
