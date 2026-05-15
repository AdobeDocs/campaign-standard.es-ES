---
title: Creación de un formulario de Campaign en Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear formularios directamente en AEM para crear y actualizar perfiles o administrar suscripciones.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 61683639-3f71-4652-a138-acfc0e91e868
TQID: https://experienceleague.adobe.com/5wklRtwZ6Wubvyo-yu2ogEHufoqYBh6cvaJEoBC-Lkk
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 187
ht-degree: 11%

---

# Creación de un formulario de Campaign en Experience Manager {#creating-a-campaign-form-in-experience-manager}

Puede crear &quot;formularios&quot; en sus sitios de AEM y asignar los campos de un formulario a los campos de la base de datos de Adobe Campaign. Esto le permite crear y actualizar perfiles o administrar las suscripciones a un servicio.

Para crear un formulario de Adobe Campaign en el sitio de AEM:

1. En su sitio de AEM, cree una nueva página basada en la plantilla **Perfil de Adobe Campaign**.

   ![](assets/aem_content_forms.png)

1. En las propiedades de la página, seleccione el **[!UICONTROL Cloud Service]** correspondiente a su instancia de Adobe Campaign.

   ![](assets/aem_content_forms_2.png)

1. Seleccione el tipo de formulario del componente **[!UICONTROL Form Start]**:

   * **Adobe Campaign: guardar perfil**
   * **Adobe Campaign: suscribirse a los servicios**
   * **Adobe Campaign: cancelar la suscripción a los servicios**

1. Edite el contenido del formulario añadiendo diferentes campos y componentes que puede asignar a los campos de la base de datos de Adobe Campaign.
1. Pruebe y publique el formulario para que sea accesible en el sitio de AEM.

Para obtener más información, consulte la [documentación detallada](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/adobe-campaign-forms.html).
