---
title: 'Creación de un formulario de Campaign en Experience Manager '
description: Con la integración de Adobe Experience Manager, puede crear formularios directamente en AEM para crear y actualizar perfiles o administrar suscripciones.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 12%

---

# Creación de un formulario de Campaign en Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puede crear &quot;formularios&quot; en sus sitios AEM y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones a un servicio.

Para crear un formulario de Adobe Campaign en el sitio AEM:

1. En el sitio AEM, cree una nueva página basada en la plantilla **Adobe Campaign Profile**.

   ![](assets/aem_content_forms.png)

1. En las propiedades de página, seleccione el **[!UICONTROL Cloud Service]** correspondiente a la instancia de Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleccione el tipo de formulario del componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: Guardar perfil**
   * **Adobe Campaign: Suscripción a servicios**
   * **Adobe Campaign: Cancelar suscripción a los servicios**

1. Edite el contenido del formulario añadiendo diferentes campos y componentes que pueda asignar a los campos de la base de datos de Adobe Campaign.
1. Pruebe y publique el formulario para que sea accesible en su sitio AEM.

Para obtener más información, consulte la [documentación detallada](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
