---
title: Definición de la línea de asunto y del remitente de un correo electrónico
description: Descubra cómo definir la línea de asunto y el remitente de un correo electrónico en el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 259f7033310982298024462c0134989404c096f4

---


# Definición de la línea de asunto y del remitente de un correo electrónico{#defining-the-subject-line-of-an-email}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>Si la línea de asunto está vacía, se muestra una advertencia en el panel de mensajes y en el Diseñador de correo electrónico.

Para configurar el asunto del correo electrónico, vaya a la **[!UICONTROL Properties]**ficha de la página de inicio de Email Designer (a la que se puede acceder desde el icono de inicio) y rellene la**[!UICONTROL Subject]** sección.

**Para definir la línea de asunto de un correo electrónico**:

1. Cree un correo electrónico.
1. Cierre la página principal.
1. Vaya a la **[!UICONTROL Properties]**ficha de la página de inicio de Email Designer (accesible mediante el icono de inicio) y rellene la**[!UICONTROL Subject]** sección.

![](assets/email_designer_subject.png)

También puede agregar campos de personalización, bloques de contenido y contenido dinámico a la línea de asunto haciendo clic en los iconos correspondientes.

## Línea de asunto predictiva {#predictive-subject-line}

Al editar un mensaje de correo electrónico, puede probar distintas líneas de asunto y obtener una estimación de su tasa de apertura antes de enviarlo.

Esta función está deshabilitada de forma predeterminada. Se activa cuando se importa el primer modelo. Un modelo es el resultado de conjuntos de datos de capacitación específicos de un sector determinado. Los modelos permiten al sistema predecir la velocidad de apertura del correo electrónico cuando se envía una nueva línea de asunto.

>[!NOTE]
>
>Esta función está disponible para los mensajes de correo electrónico y para las bases de datos que solo contienen contenido en inglés. El modelo entrenado será incoherente y dará lugar a resultados erróneos si la instancia contiene correos electrónicos en otros idiomas. La opción que permite probar un asunto solo está visible si ya hay un modelo disponible en la instancia.

**Tema relacionado**

* [Prueba de la línea de asunto de un correo electrónico](../../sending/using/testing-subject-line-email.md)

## Definición del remitente de correo electrónico de un mensaje de correo electrónico {#email-sender}

Para definir el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]**ficha de la página de inicio de Email Designer (accesible a través del icono de inicio).

![](assets/delivery_content_edition16.png)

* El **[!UICONTROL From: name]**campo permite introducir el nombre del remitente. De forma predeterminada, el bloque de nombre** del **remitente predeterminado se introduce automáticamente en el campo. La dirección de correo electrónico y el nombre del remitente predeterminados se definen en**[!UICONTROL Brands]** accesible mediante el logotipo de Adobe Campaign en el menú avanzado **[!UICONTROL Administration > Instance settings > Brand configuration]**.

   Puede cambiar el nombre del remitente haciendo clic en el bloque de nombre **del** remitente. A continuación, el campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. Para ello, puede agregar campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente.

* El **[!UICONTROL From: email address]**campo no se puede editar desde esta sección. Puede cambiarlo editando las propiedades del correo electrónico desde su tablero. Para obtener más información, consulte[Lista de parámetros](../../administration/using/configuring-email-channel.md#advanced-parameters)avanzados de correo electrónico.

>[!NOTE]
>
>Los parámetros de encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico introducidas.

**Temas relacionados:**

* [Inserción de un campo personalizado](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
