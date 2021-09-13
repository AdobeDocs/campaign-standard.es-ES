---
title: Personalización de un correo electrónico con datos adicionales
description: Este caso de uso presenta cómo añadir diferentes tipos de datos adicionales a una consulta y utilizarlos como campo de personalización en un correo electrónico.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: b207dc73-03dc-4f25-95e5-573e4b4bce54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 86%

---

# Personalización de un correo electrónico con datos adicionales {#example--personalizing-an-email-with-additional-data}

El siguiente ejemplo ilustra la adición de diferentes tipos de datos adicionales a una consulta y su uso como campo de personalización en un mensaje de correo electrónico. Para obtener más información sobre cómo enriquecer los datos segmentados por una actividad **[!UICONTROL Query]**, consulte [esta sección](../../automating/using/query.md#enriching-data).

Para este ejemplo, se utilizan [recursos personalizados](../../developing/using/data-model-concepts.md):

* El recurso de **perfil** se amplió para agregar un campo que permite guardar los puntos de lealtad de cada perfil.
* Se creó un recurso de **transacciones** que identifica todas las compras realizadas por los perfiles de la base de datos. La fecha, el precio y el producto comprado se guardan para cada transacción.
* Se creó un recurso de **productos** que hace referencia a los productos disponibles para comprar.

El objetivo es enviar un correo electrónico a los perfiles para los que se ha guardado al menos una transacción. A través de este correo electrónico, los clientes recibirán un recordatorio de la última transacción realizada, así como una vista general de todas sus transacciones: el número de productos comprados, el total gastado, un recordatorio del número total de puntos de lealtad que han acumulado.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/enrichment_example1.png)

1. Agregue una actividad [Query](../../automating/using/query.md) , que le permite dirigirse a los perfiles que han realizado al menos una transacción.

   ![](assets/enrichment_example2.png)

1. En la pestaña **[!UICONTROL Additional data]** de la consulta, defina los diferentes datos que se mostrarán en el correo electrónico final:

   * El campo simple de la dimensión de **perfil** correspondiente a los puntos de lealtad. Consulte la sección [Adición de un campo simple](../../automating/using/query.md#adding-a-simple-field).
   * Dos agregados basados en la recopilación de transacciones: el número de productos comprados y la cantidad total gastada. Puede agregarlos desde la pestaña **[!UICONTROL Data]** de la ventana de configuración de agregados mediante los agregados **Count** y **Sum**. Consulte la sección [Adición de un agregado](../../automating/using/query.md#adding-an-aggregate) .
   * Una colección que devuelve la cantidad gastada, la fecha y el producto de la última transacción efectuada.

      Para ello, debe agregar los diferentes campos que desea mostrar desde la pestaña **[!UICONTROL Data]** de la ventana de configuración de la colección.

      Para devolver solo la transacción más reciente, debe introducir &quot;1&quot; en **[!UICONTROL Number of lines to return]** y aplicar un orden descendente en el campo **Fecha** de la colección desde la pestaña **[!UICONTROL Sort]**.

      Consulte las secciones [Adición de una colección](../../automating/using/query.md#adding-a-collection) y [Clasificación de datos adicionales](../../automating/using/query.md#sorting-additional-data).
   ![](assets/enrichment_example4.png)

1. Si desea comprobar que la transición saliente de la actividad transfiere correctamente los datos, inicie el flujo de trabajo por primera vez (sin la actividad **[!UICONTROL Email delivery]**) y abra la transición saliente de la consulta.

   ![](assets/enrichment_example5.png)

1. Agregue una actividad [Email delivery](../../automating/using/email-delivery.md). En el contenido del correo electrónico, inserte los campos de personalización correspondientes a los datos calculados en la consulta. Puede encontrarlo a través del vínculo **[!UICONTROL Additional data (targetData)]** del explorador de campos de personalización.

   ![](assets/enrichment_example3.png)

Su flujo de trabajo está listo para ejecutarse. Los perfiles objetivo en la consulta recibirán un correo electrónico personalizado con los datos calculados a partir de sus transacciones.
