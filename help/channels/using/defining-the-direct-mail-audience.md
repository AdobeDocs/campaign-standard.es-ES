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
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# Definición de la audiencia de correo directo{#defining-the-direct-mail-audience}

Puede definir la audiencia en el asistente para creación o haciendo clic en la **sección Audiencia** del tablero de envío.

![](assets/direct_mail_15.png)

## Definición del objetivo principal {#defining-the-main-target}

Para el correo directo, los perfiles de objetivo son los que se incluirán en el archivo de extracción que se enviarán al proveedor de correo directo.

Para cada perfil de destino, se agrega una nueva línea en el archivo de extracción. La cantidad de información de perfil que se incluirá para cada destinatario se define en [la definición de la](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) pantalla de extracción.

>[!CAUTION]
>
>Asegúrese de que los perfiles incluyan una dirección postal, ya que esta información es esencial para el proveedor de correo directo. También asegúrese de que ha marcado **[!UICONTROL Address specified]** la casilla en la información de los perfiles. Consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations).

## Adición de perfiles de prueba y de reventado {#adding-test-and-trap-profiles}

Agregue perfiles de prueba para poder probar el archivo con un pequeño número de perfiles. Permite crear rápidamente un ejemplo de archivo para probar y validar la estructura antes de preparar el archivo real. Consulte [Administración de perfiles de prueba y envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md).

El uso de trampas es esencial para enviar envíos de correo electrónico. Permiten verificar que el proveedor de correo directo realmente esté enviando la comunicación y que no envían la lista de clientes a otro proveedor. Consulte [Uso de trampas](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).

Para envíos de correo directo, se agregan trampas durante la extracción y se mezclan en el documento de salida. De forma predeterminada, se insertan en el orden de clasificación del archivo de salida, pero puede optar por insertarlos al final o al principio del archivo. Al definir la audiencia, seleccione la opción que desee en **[!UICONTROL Trap insertion mode]** la ficha.

![](assets/direct_mail_trap_insertion_mode.png)
