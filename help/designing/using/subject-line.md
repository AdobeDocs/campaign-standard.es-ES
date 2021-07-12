---
solution: Campaign Standard
product: campaign
title: Definición del asunto y del remitente de un correo electrónico
description: Descubra cómo definir la línea de asunto y el remitente de un correo electrónico en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Diseño de correo electrónico
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 12%

---

# Definición del asunto y del remitente de un correo electrónico{#defining-the-subject-line-of-an-email}

## Definición de la línea de asunto de un correo electrónico {#subject-line}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>Si la línea de asunto está vacía, se muestra una advertencia en el panel de mensajes y en el Diseñador de correo electrónico.

1. Creación de un correo electrónico.
1. Vaya a la pestaña **[!UICONTROL Properties]** de la página de inicio del Diseñador de correo electrónico (accesible a través del icono de inicio).
1. Complete la sección **[!UICONTROL Subject]** .

   ![](assets/email_designer_subject.png)

1. También puede añadir campos de personalización, bloques de contenido y contenido dinámico a la línea de asunto haciendo clic en los iconos correspondientes. Para obtener más información, consulte [Personalización](../../designing/using/personalization.md).

## Definición del remitente del correo electrónico de un correo electrónico {#email-sender}

Para definir el nombre del remitente que aparece en el encabezado de los mensajes enviados, vaya a la pestaña **[!UICONTROL Properties]** de la página de inicio del Diseñador de correo electrónico (accesible a través del icono de inicio).

![](assets/delivery_content_edition16.png)

* El campo **[!UICONTROL From: name]** permite introducir el nombre del remitente. De forma predeterminada, el bloque predeterminado **Sender name** se introduce automáticamente en el campo . La dirección de correo electrónico del remitente y el nombre del remitente predeterminados se definen en **[!UICONTROL Brands]** accesible a través del logotipo de Adobe Campaign en el menú avanzado **[!UICONTROL Administration > Instance settings > Brand configuration]** .

   Puede cambiar el nombre del remitente haciendo clic en el bloque **Sender name** . A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. Para ello, puede añadir campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente. Para obtener más información, consulte [Personalización](../../designing/using/personalization.md).

* El campo **[!UICONTROL From: email address]** no se puede editar desde esta sección. Puede cambiarlo editando las propiedades del correo electrónico desde su panel. Para obtener más información, consulte [Lista de parámetros avanzados de correo electrónico](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

**Temas relacionados:**

* [Inserción de un campo de personalización.](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Añadir un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
