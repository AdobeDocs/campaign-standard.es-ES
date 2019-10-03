---
title: Defining the subject line and the sender of an email
seo-title: Defining the subject line and the sender of an email
description: Defining the subject line and the sender of an email
seo-description: Discover how to define the subject line and the sender of an email in the Email Designer.
page-status-flag: never-activated
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
source-git-commit: 5847c89b97ede8b03e75d1d90f31c88ed5c8a84e

---


# Definición de la línea de asunto y del remitente de un correo electrónico{#defining-the-subject-line-of-an-email}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>Si la línea de asunto está vacía, se muestra una advertencia en el panel de mensajes y en el Diseñador de correo electrónico.

Para configurar el asunto del correo electrónico, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (a la que se puede acceder desde el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

**Para definir la línea de asunto de un correo electrónico**:

1. Cree un correo electrónico.
1. Cierre la página principal.
1. Vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (accesible mediante el icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

![](assets/email_designer_subject.png)

También puede agregar campos de personalización, bloques de contenido y contenido dinámico a la línea de asunto haciendo clic en los iconos correspondientes.

**Temas relacionados:**

* [Inserción de un campo personalizado](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Línea de asunto predictiva {#predictive-subject-line}

Al editar un mensaje de correo electrónico, puede probar distintas líneas de asunto y obtener una estimación de su tasa de apertura antes de enviarlo.

Esta función está deshabilitada de forma predeterminada. Se activa cuando se importa el primer modelo. Un modelo es el resultado de conjuntos de datos de capacitación específicos de un sector determinado. Los modelos permiten al sistema predecir la velocidad de apertura del correo electrónico cuando se envía una nueva línea de asunto.

>[!NOTE]
>
>Esta función está disponible para los mensajes de correo electrónico y para las bases de datos que solo contienen contenido en inglés. The trained model will be inconsistent and will lead to erroneous results if your instance contains emails in other languages. La opción que permite probar un asunto solo está visible si ya hay un modelo disponible en la instancia.

**Tema relacionado**

* [Prueba de la línea de asunto de un correo electrónico](../../sending/using/testing-subject-line-email.md)

## Enviar correo electrónico {#email-sender}

Para definir el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio de Email Designer (accesible a través del icono de inicio).

![](assets/delivery_content_edition16.png)

* El **[!UICONTROL From: name]** campo permite introducir el nombre del remitente. De forma predeterminada, el bloque de nombre **del** remitente predeterminado se introduce automáticamente en el campo. Adobe Campaign hace referencia a la configuración del canal de correo electrónico (en el menú avanzado **[!UICONTROL Administration > Channels > Email > Email accounts]** mediante el logotipo de Adobe Campaign) para designar a este remitente.

   Puede cambiar el nombre del remitente haciendo clic en el bloque de nombre **del** remitente. A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. To do this, you can add personalization fields, content blocks and dynamic content by clicking the icons below the sender name.

* The **[!UICONTROL From: email address]** field cannot be edited from this section. You can change it by editing the properties of the email from its dashboard. For more information, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

**Temas relacionados:**

* [Inserción de un campo personalizado](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adding a content block](../../designing/using/personalization.md#adding-a-content-block)
* [Defining dynamic content in an email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
