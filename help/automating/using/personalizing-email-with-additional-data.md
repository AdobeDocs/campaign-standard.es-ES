---
title: Personalización de un correo electrónico con datos adicionales
description: Este caso de uso muestra cómo agregar diferentes tipos de datos adicionales a una consulta y utilizarlos como campo de personalización en un mensaje de correo electrónico.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---


# Personalización de un correo electrónico con datos adicionales {#example--personalizing-an-email-with-additional-data}

El siguiente ejemplo ilustra la adición de diferentes tipos de datos adicionales a una consulta y su uso como campo de personalización en un mensaje de correo electrónico. Para obtener más información sobre cómo enriquecer los datos dirigidos por una **[!UICONTROL Query]** actividad, consulte [esta sección](../../automating/using/query.md#enriching-data).

Para este ejemplo, se utilizan recursos [](../../developing/using/data-model-concepts.md) personalizados:

* El recurso de **perfil** se amplió para agregar un campo que permite guardar los puntos de lealtad de cada perfil.
* Se creó un recurso de **transacciones** que identifica todas las compras realizadas por los perfiles en la base de datos. La fecha, el precio y el producto comprados se guardan para cada transacción.
* Se creó un recurso de **productos** que hace referencia a los productos disponibles para la compra.

El objetivo es enviar un correo electrónico a los perfiles para los que se ha guardado al menos una transacción. A través de este correo electrónico, los clientes recibirán un recordatorio de la última transacción realizada, así como una visión general de todas sus transacciones: el número de productos comprados, el total gastado, un recordatorio del número total de puntos de lealtad que han acumulado.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/enrichment_example1.png)

1. Añada una actividad de [Consulta](../../automating/using/query.md) que le permita realizar el destinatario de los perfiles que han realizado al menos una transacción.

   ![](assets/enrichment_example2.png)

   En la ficha **[!UICONTROL Additional data]** de la consulta, defina los diferentes datos que se mostrarán en el correo electrónico final:

   * Campo simple de la dimensión de **perfil** correspondiente a los puntos de lealtad. Consulte la sección [Añadir un campo](../../automating/using/query.md#adding-a-simple-field) sencillo.
   * Dos agregados basados en la recopilación de transacciones: el número de productos comprados y la cantidad total gastada. Puede agregarlos desde la **[!UICONTROL Data]** ficha de la ventana de configuración acumulada mediante los agregados **Recuento** y **Suma** . Consulte [Añadir una sección acumulada](../../automating/using/query.md#adding-an-aggregate) .
   * Recopilación que devuelve el importe gastado, la fecha y el producto de la última transacción realizada.

      Para ello, debe agregar los diferentes campos que desea mostrar desde la ficha de la ventana de configuración de la colección **[!UICONTROL Data]** .

      Para devolver solo la transacción más reciente, debe introducir &quot;1&quot; para la **[!UICONTROL Number of lines to return]** y aplicar un orden descendente en el campo **Fecha** de la colección desde la **[!UICONTROL Sort]** ficha.

      Consulte las secciones [Añadir una colección](../../automating/using/query.md#adding-a-collection) y [Ordenar datos](../../automating/using/query.md#sorting-additional-data) adicionales.
   ![](assets/enrichment_example4.png)

   Si desea comprobar que la transición saliente de la actividad transfiere correctamente los datos, inicio el flujo de trabajo por primera vez (sin la **[!UICONTROL Email delivery]** actividad) y abra la transición saliente de la consulta.

   ![](assets/enrichment_example5.png)

1. Añada una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico. En el contenido del correo electrónico, inserte los campos de personalización correspondientes a los datos calculados en la consulta. Puede encontrarlo a través del **[!UICONTROL Additional data (targetData)]** enlace del explorador de campos de personalización.

   ![](assets/enrichment_example3.png)

El flujo de trabajo ya está listo para ejecutarse. Los perfiles objetivo en la consulta recibirán un correo electrónico personalizado con los datos calculados a partir de sus transacciones.
