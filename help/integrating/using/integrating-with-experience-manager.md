---
title: Acerca de la integración de Campaign-Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: ff94f69b-3036-4103-a841-6b85feb0eb7e
TQID: https://experienceleague.adobe.com/OuQgaZgJVeL04fw3rvn5nydbp2fOSdQOVpiFhrUcEl4
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616aid: a658c786-869b-4194-a780-2594d663addaid: d5ef99fa-df0c-4153-bf94-105ad0724167
subfeature_v2: id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0id: df0d6518-6f49-46e2-b46e-3bcc513f553f
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e0eb8757-182f-49f3-94a4-1587d16f5094id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 676
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

  La configuración del externalizador al implementar Experience Manager para Adobe Campaign Standard permite transformar una ruta de recursos en una dirección URL. Esto le permite hacer que las imágenes sean visibles en la página. Si el externalizador no está configurado correctamente, los correos electrónicos contendrán imágenes rotas.

  Para aprender a configurar el externalizador, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/externalizer.html).

* **Organice sus plantillas de correo electrónico para evitar un uso indebido.**

  Mantener las plantillas organizadas garantiza que las plantillas adecuadas estén en las carpetas adecuadas y que no se elijan las incorrectas por error. Durante la implementación, se deben crear rutas para guardar las plantillas en los lugares adecuados.

  Para obtener más información sobre las plantillas, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/developing/platform/templates/templates.html#template-availability).

* **Empiece rápidamente con los componentes predeterminados.**

  Los componentes listos para usar de Adobe Experience Manager para Adobe Campaign Standard pueden ayudarle a empezar rápidamente si las plantillas no son complejas.
Hay siete componentes listos para usar en Experience Manager que puede empezar a utilizar:

   * Encabezado
   * Imagen
   * Vínculo
   * Plantilla de imagen de Scene7
   * Referencia de destino
   * Texto e imagen
   * Texto y Personalization

* **HTML para correos electrónicos es diferente de HTML para la web**

  Es importante comprender que no puede utilizar los mismos componentes utilizados en el contenido web para las plantillas de correo electrónico. El uso de componentes listos para usar garantiza que los componentes serán compatibles con el correo electrónico.

* **Desvincule el contenido de las plantillas y vuelva a utilizarlo una y otra vez.**

  Al configurar los correos electrónicos en Campaign Standard y seleccionar una plantilla de Experience Manager, solo puede elegir una que aún no se haya vinculado a otra campaña. De lo contrario, si cambia el contenido en Adobe Experience Manager para una campaña y lo actualiza, puede afectar de forma involuntaria al contenido en la otra campaña.
Para evitarlo, una vez que haya terminado de utilizar la plantilla, puede desvincularla para volver a utilizarla. Solo tiene que seleccionar la plantilla y hacer clic en **[!UICONTROL Delete the link with Adobe Experience Manager content]**.

* **Use Adobe Experience Manager para crear variaciones de correos electrónicos para Adobe Campaign Standard.**

  Esta integración le permite convertir fácilmente un correo electrónico en varias versiones con la segmentación.
Para obtener información sobre cómo configurar la segmentación en Adobe Experience Manager y cómo crear correo electrónico con contenido de destino, consulte esta [página](https://experienceleague.adobe.com/docs/experience-manager-65/authoring/aem-adobe-campaign/target-adobe-campaign.html#setting-up-segmentation-in-aem).

* **Para que la sincronización se realice correctamente, el nombre del segmento en Experience Manager debe coincidir con el nombre del segmento en Campaign.**
