---
title: Personalización del remitente
seo-title: Personalización del remitente
description: Personalización del remitente
seo-description: Obtenga información sobre cómo personalizar el nombre o la dirección del remitente de los mensajes.
page-status-flag: no activado nunca
uuid: 7 aa 08 d 5 d -9 e 6 c -4 dac-bff 8-6 fde 85368 c 2 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: personalizar contenido
discoiquuid: 49532 f 6 b -3 cd 0-4 d 03-932 e-bcb 7 d 05 c 74 d 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personalizing the sender{#personalizing-the-sender}

## Email sender {#email-sender}

To define the name of the sender which will appear in the header of messages sent, go the **[!UICONTROL Properties]** tab of the Email Designer home page (accessible through the home icon).

![](assets/delivery_content_edition16.png)

* **[!UICONTROL From: name]** El campo permite introducir el nombre del remitente. By default, the default **Sender name** block is automatically entered in the field. Adobe Campaign refers to the email channel configuration (from the advanced menu **[!UICONTROL Administration > Channels > Email > Email accounts]** via the Adobe Campaign logo) to designate this sender.

   You can change the sender name by clicking the **Sender name** block. El campo se puede editar y puede introducir el nombre que desee utilizar.

   Este campo se puede personalizar. Para ello, puede agregar campos de personalización, bloques de contenido y contenido dinámico haciendo clic en los iconos situados debajo del nombre del remitente.

* The **[!UICONTROL From: email address]** field cannot be edited from this section. Puede cambiarla editando las propiedades del correo electrónico desde su tablero. For more on this, see [List of email advanced parameters](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Los parámetros del encabezado no deben estar vacíos. La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico (estándar RFC). Adobe Campaign comprueba la sintaxis de las direcciones de correo electrónico ingresadas.

**Temas relacionados:**

* [Inserción de un campo de personalización](../../designing/using/inserting-a-personalization-field.md)
* [Adición de un bloque de contenido](../../designing/using/adding-a-content-block.md)
* [Definición de contenido dinámico en un mensaje de correo electrónico](../../designing/using/defining-dynamic-content-in-an-email.md)

## SMS sender {#sms-sender}

Puede personalizar el nombre del remitente SMS. For more on this, refer to the [SMS configuration](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) section.
