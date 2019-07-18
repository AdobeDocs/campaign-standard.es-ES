---
title: Definición de la audiencia de correo directo
seo-title: Definición de la audiencia de correo directo
description: Definición de la audiencia de correo directo
seo-description: Descubra cómo definir el objetivo para la entrega de correo directo.
page-status-flag: no activado nunca
uuid: f 843 e 368-5 c 07-4 b 53-8943-46 f 7 bf 45 b 62 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: correo directo
discoiquuid: f 993 d 1 b 6-4 b 9 a -4 f 95-81 fc -60 c 126211 bd 2
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail audience{#defining-the-direct-mail-audience}

You can either define the audience in the creation wizard or by clicking on the **Audience** section of the delivery dashboard.

![](assets/direct_mail_15.png)

## Defining the main target {#defining-the-main-target}

Para el correo directo, los perfiles de objetivo son los que se incluirán en el archivo de extracción que se enviarán al proveedor de correo directo.

Para cada perfil de destino, se agrega una nueva línea en el archivo de extracción. The amount of profile information that will be included for each recipient is defined in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) screen.

>[!CAUTION]
>
>Asegúrese de que los perfiles incluyan una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

## Adding test and trap profiles {#adding-test-and-trap-profiles}

Agregue perfiles de prueba para poder probar el archivo con un pequeño número de perfiles. Permite crear rápidamente un ejemplo de archivo para probar y validar la estructura antes de preparar el archivo real. Refer to [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

El uso de trampas es esencial para enviar envíos de correo electrónico. Por ejemplo, permiten verificar que el proveedor de correo directo realmente esté enviando la comunicación y que no envían la lista de clientes a otro proveedor.

Para envíos de correo directo, se agregan trampas durante la extracción y se mezclan en el documento de salida. By default, they are inserted in the sorting order of the output file, but you can choose to insert them at the end or the beginning of the file ( **[!UICONTROL Trap insertion mode]** tab).
