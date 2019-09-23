---
title: Definición de la línea de asunto y del remitente de un correo electrónico
seo-title: Definición de la línea de asunto y del remitente de un correo electrónico
description: Definición de la línea de asunto y del remitente de un correo electrónico
seo-description: Descubra cómo definir la línea de asunto y el remitente de un correo electrónico en el Diseñador de correo electrónico.
page-status-flag: nunca activado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: diseñar
content-type: referencia
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0cf4807fc3d617b0c5ca33705b6344d1f3994ab3

---


# Definición de la línea de asunto y del remitente de un correo electrónico{#defining-the-subject-line-of-an-email}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>If the subject line is empty, a warning is displayed in the message dashboard and in the Email Designer.

Para configurar el asunto del correo electrónico, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (a la que se puede acceder desde el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

**Para definir la línea de asunto de un correo electrónico**:

1. Create an email.
1. Close homepage.
1. Go the  tab of the Email Designer home page (accessible through the home icon) and fill in the  section.**[!UICONTROL Properties]****[!UICONTROL Subject]**

![](assets/email_designer_subject.png)

You can also add personalization fields, content blocks and dynamic content to the subject line by clicking the corresponding icons.

**Related topics:**

* [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Predictive subject line {#predictive-subject-line}

When editing an email, you can try out different subject lines and get an estimation of its open rate before you send it.

This feature is disabled by default. It is enabled when the first model is imported. A model is the result of training data sets specific to a given industry. Models allow the system to predict the open rate of the email when a new subject line is submitted.

>[!NOTE]
>
>Esta función está disponible para los mensajes de correo electrónico y para las bases de datos que solo contienen contenido en inglés. El modelo entrenado será incoherente y dará lugar a resultados erróneos si la instancia contiene correos electrónicos en otros idiomas. La opción que permite probar un asunto solo está visible si ya hay un modelo disponible en la instancia.

**Tema relacionado**

* [Prueba de una línea de asunto](../../sending/using/testing-subject-line-email.md)

## Enviar correo electrónico {#email-sender}

Para definir el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (accesible a través del icono de inicio).

![](assets/delivery_content_edition16.png)

* El **[!UICONTROL From: name]** campo permite introducir el nombre del remitente. De forma predeterminada, el bloque de nombre **del** remitente predeterminado se introduce automáticamente en el campo. Adobe Campaign hace referencia a la configuración del canal de correo electrónico (en el menú avanzado **[!UICONTROL Administration > Channels > Email > Email accounts]** mediante el logotipo de Adobe Campaign) para designar a este remitente.

   Puede cambiar el nombre del remitente haciendo clic en el bloque de nombre **del** remitente. A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. Para ello, puede agregar campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente.

* El **[!UICONTROL From: email address]** campo no se puede editar desde esta sección. Puede cambiarlo editando las propiedades del correo electrónico desde su tablero. Para obtener más información, consulte [Lista de parámetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avanzados de correo electrónico.

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir el envío de un correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

**Temas relacionados:**

* [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)