---
title: Acerca de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager AEM Adobe Campaign, puede crear contenido directamente en y usarlo más adelante en.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 1%

---

# Acerca de la integración de Campaign-Experience Manager{#integrating-with-experience-manager}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar el contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Por lo tanto, puede aprovechar al máximo las funcionalidades de edición de contenido de Adobe Experience Manager, así como las funcionalidades de entrega y administración de datos de Adobe Campaign. Tenga en cuenta que no puede realizar pruebas A/B con contenido importado de Adobe Experience Manager.

Adobe Campaign Standard es compatible con Adobe Experience Manager 6.1, 6.2, 6.3, 6.4 y 6.5. Las secciones siguientes presentan una descripción general de las acciones que puede ejecutar. Para obtener más información, consulte las secciones dedicadas a [configuración](https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html) y el [uso](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/campaign.html) de la integración.

>[!NOTE]
>
> Las plantillas de Adobe Campaign Standard ya no están disponibles con Adobe Experience Manager 6.5.

## Sugerencias sobre cómo utilizar la integración de Campaign y Experience Manager {#tips-aem}

* **Saber qué plantilla usar con la integración**

  Dado que las plantillas de correo electrónico se pueden editar dentro de Adobe Experience Manager, puede resultar más fácil editar cualquier plantilla en Adobe Experience Manager. Sin embargo, algunas plantillas no se adaptan fácilmente. No se recomiendan plantillas individualizadas específicas de un cliente para esta integración y deben editarse directamente en Adobe Campaign Standard.

  Para obtener más información sobre las plantillas, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html).

* **Asegúrese de que el externalizador se configuró durante la implementación**

  La configuración del externalizador al implementar el Experience Manager para Adobe Campaign Standard permite transformar una ruta de recurso en una dirección URL. Esto le permite hacer que las imágenes sean visibles en la página. Si el externalizador no está configurado correctamente, los correos electrónicos contendrán imágenes rotas.

  Para aprender a configurar el externalizador, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organice sus plantillas de correo electrónico para evitar un uso indebido.**

  Mantener las plantillas organizadas garantiza que las plantillas adecuadas estén en las carpetas adecuadas y que no se elijan las incorrectas por error. Durante la implementación, se deben crear rutas para guardar las plantillas en los lugares adecuados.

  Para obtener más información sobre las plantillas, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Empiece rápidamente con los componentes predeterminados.**

  Los componentes listos para usar de Adobe Experience Manager para Adobe Campaign Standard pueden ayudarle a empezar rápidamente si las plantillas no son complejas.
Hay siete componentes listos para usar en Experience Manager que puede empezar a utilizar:

   * Encabezado
   * Imagen
   * Enlace
   * Plantilla de imagen de Scene7
   * Referencia de destino
   * Texto e imagen
   * Texto y Personalization

* **El HTML de los correos electrónicos no coincide con el HTML de la web**

  Es importante comprender que no puede utilizar los mismos componentes utilizados en el contenido web para las plantillas de correo electrónico. El uso de componentes listos para usar garantiza que los componentes serán compatibles con el correo electrónico.

* **Desvincule el contenido de las plantillas y vuelva a utilizarlo una y otra vez.**

  Al configurar los correos electrónicos en Campaign Standard y seleccionar una plantilla de Experience Manager, solo puede elegir una que aún no se haya vinculado a otra campaña. De lo contrario, si cambia el contenido en Adobe Experience Manager para una campaña y lo actualiza, puede afectar de forma involuntaria al contenido en la otra campaña.
Para evitarlo, una vez que haya terminado de utilizar la plantilla, puede desvincularla para volver a utilizarla. Solo tiene que seleccionar la plantilla y hacer clic en **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Use Adobe Experience Manager para crear variaciones de correos electrónicos para Adobe Campaign Standard.**

  Esta integración le permite convertir fácilmente un correo electrónico en varias versiones con la segmentación.
Para obtener información sobre cómo configurar la segmentación en Adobe Experience Manager y cómo crear correo electrónico con contenido de destino, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para que la sincronización se realice correctamente, el nombre del segmento en el Experience Manager debe coincidir con el nombre del segmento en la campaña exacta.**
