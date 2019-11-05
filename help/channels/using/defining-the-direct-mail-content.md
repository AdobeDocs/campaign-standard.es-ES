---
title: Definición del contenido de correo postal
description: Obtenga información sobre cómo definir el contenido para la entrega directa de correo.
page-status-flag: nunca activado
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: entrega,directMailContent,retroceso
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Definición del contenido de correo postal{#defining-the-direct-mail-content}

Puede definir el contenido en la última pantalla del asistente de creación o haciendo clic en la sección **Contenido** del tablero de envío.

![](assets/direct_mail_6.png)

La pantalla de **[!UICONTROL Content]** definición es específica del canal de correo directo. Se divide en cuatro fichas: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** y **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definición de la extracción {#defining-the-extraction}

1. Comience definiendo el nombre del archivo de extracción. Haga clic en el botón a la derecha del **[!UICONTROL Output file]** campo e introduzca la etiqueta deseada. Puede utilizar campos de personalización, bloques de contenido y texto dinámico (consulte [Definición de contenido](../../designing/using/personalization.md#example-email-personalization)). Por ejemplo, puede completar la etiqueta con el ID de entrega o la fecha de extracción.

   ![](assets/direct_mail_12.png)

1. Haga clic en el botón **[!UICONTROL +]** o **[!UICONTROL Add an element]** para agregar una columna de salida. Permite **[!UICONTROL Output columns]** definir la información de perfil (columnas) que se va a exportar al archivo de salida.

   >[!CAUTION]
   >
   >Asegúrese de que sus perfiles incluyen una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de marcar la **[!UICONTROL Address specified]** casilla en la información de sus perfiles. Consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Cree tantas columnas como necesite. Puede editar las columnas haciendo clic en sus expresiones y etiquetas.

>[!NOTE]
>
>Para obtener más información sobre la definición de la columna de salida, consulte la sección [Extraer la actividad del flujo de trabajo de archivos](../../automating/using/extract-file.md) .

## Definición de la estructura de archivos {#defining-the-file-structure}

La ficha Estructura **de** archivos permite configurar los formatos de salida, fecha y número del archivo que se exportará.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Las opciones disponibles se detallan en las secciones de actividad del flujo de trabajo [Extraer archivo](../../automating/using/extract-file.md) .

## Definición del encabezado y el pie de página {#defining-the-header-and-footer}

A veces es posible que necesite agregar información al principio o al final del archivo de extracción. Para ello, utilice las fichas **[!UICONTROL Header]** y **[!UICONTROL Footer]** de la pantalla de **[!UICONTROL Content]** configuración.

![](assets/direct_mail_7.png)

Por ejemplo, es posible que desee incluir, para el proveedor de correo directo, la información del remitente en el encabezado del archivo. Es posible personalizar el pie de página y el encabezado con la información disponible en el contexto de la entrega. Consulte [Definición de contenido](../../designing/using/personalization.md#example-email-personalization).

La dirección del remitente se define en la **[!UICONTROL Send]** sección de las propiedades de correo directo o en el nivel de plantilla.

![](assets/direct_mail_24.png)

