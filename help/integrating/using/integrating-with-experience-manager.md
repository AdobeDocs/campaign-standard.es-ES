---
title: Acerca de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 1%

---

# Acerca de la integración de Campaign-Experience Manager{#integrating-with-experience-manager}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Por lo tanto, puede sacar el máximo partido a las funcionalidades de edición de contenido de Adobe Experience Manager, así como a las funciones de administración de datos y envío de Adobe Campaign. Tenga en cuenta que no puede realizar pruebas A/B para el contenido importado de Adobe Experience Manager.

Adobe Campaign Standard es compatible con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 y 6.5. Las siguientes secciones presentan una descripción general de las acciones que puede ejecutar. Para obtener más información, consulte las secciones dedicadas a [configuración](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) y [use](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) de la integración.

>[!NOTE]
>
> Las plantillas de Adobe Campaign Standard ya no están disponibles con Adobe Experience Manager 6.5.

## Sugerencias sobre el uso de la integración Experience Manager de Campaign {#tips-aem}

* **Saber qué plantilla utilizar con la integración**

   Dado que las plantillas de correo electrónico se pueden editar en Adobe Experience Manager, puede que sea más fácil editar cualquier plantilla en Adobe Experience Manager. Sin embargo, algunas plantillas no se adaptan fácilmente. No se recomiendan plantillas individuales específicas de un cliente para esta integración y deben editarse directamente en Adobe Campaign Standard.

   Para obtener más información sobre las plantillas, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **Asegúrese de que el externalizador se configuró durante la implementación**

   La configuración del externalizador al implementar el Experience Manager para Adobe Campaign Standard permite transformar una ruta de recurso en una dirección URL. Esto le permite hacer que las imágenes estén visibles en la página. Si el externalizador no está configurado correctamente, los mensajes de correo electrónico contendrán imágenes rotas.

   Para aprender a configurar el externalizador, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organice las plantillas de correo electrónico para evitar el uso indebido.**

   Mantener las plantillas organizadas garantiza que las plantillas adecuadas se encuentren en las carpetas adecuadas y que no se elijan las erróneas por error. Durante la implementación, las rutas deben crearse para guardar las plantillas en los lugares adecuados.

   Para obtener más información sobre las plantillas, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Empiece rápidamente con los componentes integrados.**

   Los componentes integrados en Adobe Experience Manager para Adobe Campaign Standard pueden ayudarle a empezar rápidamente si las plantillas no son complejas.
Hay siete componentes listos para usar en Experience Manager que puede empezar a utilizar:

   * Encabezado
   * Imagen
   * Vínculo
   * Plantilla de imagen de Scene7
   * Referencia de destino
   * Texto e imagen
   * Texto y personalización

* **HTML para correos electrónicos es diferente de HTML para web**

   Es importante comprender que no puede utilizar los mismos componentes utilizados en el contenido web para las plantillas de correo electrónico. El uso de componentes integrados garantiza que los componentes sean compatibles con el correo electrónico.

* **Desvincule el contenido de las plantillas y vuelva a utilizarlo una y otra vez.**

   Al configurar los correos electrónicos en Campaign Standard y seleccionar una plantilla de Experience Manager, solo puede elegir uno que no se haya vinculado a otra campaña. De lo contrario, si cambia el contenido en Adobe Experience Manager para una campaña y la actualiza, puede influir de forma involuntaria en el contenido de la otra campaña.
Para evitarlo, una vez que haya terminado de usar la plantilla, puede desvincularla para volver a utilizarla. Solo tiene que seleccionar la plantilla y hacer clic en **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilice Adobe Experience Manager para crear variaciones de correos electrónicos para Adobe Campaign Standard.**

   Esta integración le permite convertir fácilmente un correo electrónico en varias versiones con la segmentación.
Para obtener información sobre cómo configurar la segmentación en Adobe Experience Manager y cómo crear correos electrónicos con contenido de destino, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para que la sincronización se realice correctamente, el nombre del segmento en el Experience Manager debe coincidir con el nombre del segmento en Campaña exactamente.**
