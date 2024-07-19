---
title: Creación de un formulario de Campaign en Experience Manager
description: Con la integración de Adobe Experience Manager AEM, puede crear formularios directamente en para crear y actualizar perfiles o administrar suscripciones, y, a continuación, puede crear formularios directamente en la interfaz de usuario de.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
source-git-commit: dcfd4e2610cbf9d250359cab6ed43e8c97dd4536
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 12%

---

# Creación de un formulario de Campaign en Experience Manager {#creating-a-campaign-form-in-experience-manager}

AEM Puede crear &quot;formularios&quot; en los sitios de la y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones a un servicio.

Para crear un formulario de Adobe Campaign AEM en el sitio de la:

1. AEM En el sitio de la, cree una nueva página basada en la plantilla **Perfil de Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. En las propiedades de la página, seleccione el **[!UICONTROL Cloud Service]** correspondiente a su instancia de Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleccione el tipo de formulario del componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: guardar perfil**
   * **Adobe Campaign: suscribirse a los servicios**
   * **Adobe Campaign: cancelar la suscripción a los servicios**

1. Edite el contenido del formulario añadiendo diferentes campos y componentes que puede asignar a los campos de la base de datos de Adobe Campaign.
1. AEM Pruebe y publique el formulario para que sea accesible en el sitio de la.

Para obtener más información, consulte la [documentación detallada](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
