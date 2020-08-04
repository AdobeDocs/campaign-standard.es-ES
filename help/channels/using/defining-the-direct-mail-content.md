---
title: Definición del contenido de correo postal
description: Aprenda a definir el contenido de su envío de correo postal.
page-status-flag: never-activated
uuid: c1234c06-4d22-46d7-ad1b-3c88660f9b06
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 9e73d6b5-41b4-474b-a880-a0cd5999c2d1
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e
workflow-type: ht
source-wordcount: '337'
ht-degree: 100%

---


# Definición del contenido de correo postal{#defining-the-direct-mail-content}

Puede definir el contenido en la última pantalla del asistente para la creación o haciendo clic en la sección **Contenido** del panel de envío.

![](assets/direct_mail_6.png)

La pantalla de definición de **[!UICONTROL Content]** es específica para el canal de correo postal. Se divide en cuatro pestañas: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** y **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Definición de la extracción {#defining-the-extraction}

1. Empiece definiendo el nombre del archivo de extracción. Haga clic en el botón a la derecha del campo **[!UICONTROL Output file]** e introduzca la etiqueta deseada. Puede utilizar campos de personalización, bloques de contenido y texto dinámico (consulte [Definición de contenido](../../designing/using/personalization.md#example-email-personalization)). Por ejemplo, puede completar la etiqueta con el ID de envío o la fecha de extracción.

   ![](assets/direct_mail_12.png)

1. Haga clic en el botón **[!UICONTROL +]** o **[!UICONTROL Add an element]** para añadir una columna de salida. La opción **[!UICONTROL Output columns]** permite definir la información de perfil (columnas) que se va a exportar al archivo de salida.

   >[!CAUTION]
   >
   >Asegúrese de que los perfiles incluyan una dirección postal, ya que esta información es esencial para el proveedor de correo. Asegúrese también de haber marcado la casilla **[!UICONTROL Address specified]** en la información de los perfiles. Consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Cree tantas columnas como necesite. Puede editar las columnas haciendo clic en sus expresiones y etiquetas.

>[!NOTE]
>
>Para obtener más información sobre la definición de la columna de salida, consulte la sección de la actividad del flujo de trabajo [Extraer archivo](../../automating/using/extract-file.md).

## Definición de la estructura del archivo {#defining-the-file-structure}

La pestaña **Estructura del archivo** permite configurar los formatos de salida, fecha y número del archivo que se van a exportar.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>Las opciones disponibles se detallan en las secciones de la actividad del flujo de trabajo [Extraer archivo](../../automating/using/extract-file.md).

## Definición del encabezado y el pie de página {#defining-the-header-and-footer}

A veces quizá deba añadir información al principio o al final del archivo de extracción. Para ello, utilice las pestañas **[!UICONTROL Header]** y **[!UICONTROL Footer]** de la pantalla de configuración de **[!UICONTROL Content]**.

![](assets/direct_mail_7.png)

Por ejemplo, es posible que desee incluir, para el proveedor de correo postal, la información del remitente en el encabezado del archivo. Es posible personalizar el pie de página y el encabezado con la información disponible en el contexto del envío. Consulte [Definición de contenido](../../designing/using/personalization.md#example-email-personalization).

La dirección del remitente se define en la sección **[!UICONTROL Send]** de las propiedades de correo postal o en el nivel de plantilla.

![](assets/direct_mail_24.png)

