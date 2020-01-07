---
title: Acerca de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 85f4d6d7ea4bdf63505bb2c8b586de3a10073345

---


# Acerca de la integración de Campaign-Experience Manager{#integrating-with-experience-manager}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Por lo tanto, puede aprovechar al máximo las funciones de edición de contenido de Adobe Experience Manager, así como las funciones de administración de datos y entrega de Adobe Campaign.

>[!NOTE]
>
>No se pueden realizar pruebas A/B para el contenido importado de Adobe Experience Manager.

Adobe Campaign Standard es compatible con Adobe Experience Manager 6.1, 6.2, 6.3 y 6.4. Las siguientes secciones presentan una descripción general de las acciones que puede ejecutar. Para obtener más información, consulte las secciones dedicadas a la [configuración](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) y el [uso](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) de la integración.

## Sugerencias sobre cómo utilizar la integración de Campaign-Experience Manager {#tips-aem}

* **Saber qué plantilla utilizar con la integración**

   Dado que las plantillas de correo electrónico se pueden editar en Adobe Experience Manager, puede que resulte más fácil editar cualquier plantilla en Adobe Experience Manager. Sin embargo, algunas plantillas no son fáciles de acomodar. No se recomiendan plantillas personalizadas específicas de un cliente para esta integración y deben editarse directamente en Adobe Campaign Standard.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-64/developing/platform/templates/templates.html).

* **Asegúrese de que Externalizer se configuró durante la implementación**

   La configuración del Externalizador al implementar Experience Manager para Adobe Campaign Standard permite transformar una ruta de recursos en una dirección URL. Esto le permite hacer que las imágenes estén visibles en la página. Si el Externalizador no está configurado correctamente, los mensajes de correo electrónico contendrán imágenes rotas.

   Para obtener información sobre cómo configurar el Externalizador, consulte esta [página](https://docs.adobe.com/content/help/en/experience-manager-64/developing/platform/externalizer.html)

* **Organice las plantillas de correo electrónico para evitar un uso indebido.**

   Mantener las plantillas organizadas garantiza que las plantillas adecuadas se encuentren en las carpetas adecuadas y que no se elijan por error las que están equivocadas. Durante la implementación, se deben crear rutas para guardar las plantillas en los lugares adecuados.

   For more information on templates, refer to this [page](https://docs.adobe.com/content/help/en/experience-manager-64/developing/platform/templates/templates.html#template-availability)

* **Empiece rápidamente con los componentes integrados.**

   Los componentes integrados en Adobe Experience Manager para Adobe Campaign Standard pueden ayudarle a iniciarse rápidamente si las plantillas no son complejas.
Hay siete componentes integrados en Experience Manager que puede empezar a utilizar:
   1. Encabezado
   1. Imagen
   1. Enlace
   1. Plantilla de imagen de Scene7
   1. Referencia de objetivo
   1. Texto e imagen
   1. Texto y personalización

* **HTML para correos electrónicos es diferente de HTML para Web**

   Es importante comprender que no puede utilizar los mismos componentes utilizados en el contenido web para las plantillas de correo electrónico. El uso de componentes integrados garantiza que los componentes sean compatibles con el correo electrónico.

* **Desvincule el contenido de las plantillas y vuelva a utilizarlo una y otra vez.**

   Al configurar los mensajes de correo electrónico en Campaign Standard y seleccionar una plantilla de Experience Manager, solo puede elegir uno que aún no esté vinculado a otra campaña. De lo contrario, si cambia el contenido de Adobe Experience Manager para una campaña y se actualiza, puede influir de forma involuntaria en el contenido de la otra campaña.
Para evitarlo, una vez que haya terminado de usar la plantilla, puede desvincularla para volver a utilizarla. Solo tiene que seleccionar la plantilla y hacer clic en **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Utilice Adobe Experience Manager para crear variaciones de correos electrónicos para Adobe Campaign Standard.**

   Esta integración le permite convertir fácilmente un correo electrónico en varias versiones con la segmentación.
Para obtener información sobre cómo configurar la segmentación en Adobe Experience Manager y cómo crear correos electrónicos con contenido de destino, consulte esta [página](https://docs.adobe.com/help/en/experience-manager-64/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para una sincronización correcta, el nombre del segmento en Experience Manager debe coincidir exactamente con el nombre del segmento en Campaign.**