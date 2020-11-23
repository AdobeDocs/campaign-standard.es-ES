---
solution: Campaign Standard
product: campaign
title: Definición de la línea de asunto y del remitente de un correo electrónico
description: Descubra cómo definir la línea de asunto y el remitente de un correo electrónico en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 11%

---


# Definición de la línea de asunto y del remitente de un correo electrónico{#defining-the-subject-line-of-an-email}

## Defining the subject line of an email {#subject-line}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>Si la línea de asunto está vacía, se muestra una advertencia en el panel de mensajes y en el Diseñador de correo electrónico.

1. Creación de un correo electrónico.
1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (a la que se puede acceder desde el icono de inicio).
1. Fill in the **[!UICONTROL Subject]** section.

   ![](assets/email_designer_subject.png)

1. También puede agregar campos de personalización, bloques de contenido y contenido dinámico a la línea de asunto haciendo clic en los iconos correspondientes. For more on this, see [Personalization](../../designing/using/personalization.md).
1. Puede probar distintas líneas de asunto para obtener una estimación de la tasa de apertura de correo electrónico antes de enviarla. Para obtener más información sobre esto, consulte [Prueba de la línea de asunto de un correo electrónico](../../sending/using/testing-subject-line-email.md).

## Definición del remitente de correo electrónico de un mensaje de correo electrónico {#email-sender}

Para definir el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio del Diseñador de correo electrónico (accesible mediante el icono de inicio).

![](assets/delivery_content_edition16.png)

* El **[!UICONTROL From: name]** campo permite introducir el nombre del remitente. De forma predeterminada, el bloque de nombre **del** remitente predeterminado se introduce automáticamente en el campo. La dirección de correo electrónico y el nombre del remitente predeterminados se definen en **[!UICONTROL Brands]** accesible mediante el logotipo de Adobe Campaign en el menú avanzado **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Puede cambiar el nombre del remitente haciendo clic en el bloque de nombre **del** remitente. A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. Para ello, puede añadir campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente. For more on this, see [Personalization](../../designing/using/personalization.md).

* El **[!UICONTROL From: email address]** campo no se puede editar desde esta sección. Puede cambiarlo editando las propiedades del correo electrónico desde su panel. Para obtener más información, consulte [Lista de parámetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avanzados de correo electrónico.

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

**Temas relacionados:**

* [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).
* [Añadir un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
