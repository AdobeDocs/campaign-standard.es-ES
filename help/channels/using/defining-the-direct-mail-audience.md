---
title: Definición del audiencia de correo postal
description: Obtenga información sobre cómo definir el objetivo para la entrega directa de correo.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 32bcfd57dfe881fa07c8d8e5700d0ae3996a78ec

---


# Definición del audiencia de correo postal{#defining-the-direct-mail-audience}

Puede definir la audiencia en el asistente de creación o haciendo clic en la sección **Audiencia** del panel de envío.

![](assets/direct_mail_15.png)

## Definición del objetivo principal {#defining-the-main-target}

Para el correo directo, los perfiles de destino son los que se incluirán en el archivo de extracción que se enviará a su proveedor de correo directo.

Para cada perfil de destino se agrega una nueva línea en el archivo de extracción. La cantidad de información de perfil que se incluirá para cada destinatario se define en la pantalla [Definición de la extracción](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) .

>[!CAUTION]
>
>Asegúrese de que sus perfiles incluyen una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Asegúrese también de haber marcado la **[!UICONTROL Address specified]** casilla en la información de sus perfiles. Consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations).

## Adición de perfiles de prueba y captura {#adding-test-and-trap-profiles}

Agregue perfiles de prueba para probar el archivo con un pequeño número de perfiles. Permite crear rápidamente un ejemplo de archivo para probar y validar la estructura antes de preparar el archivo real. See [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

El uso de trampas es esencial para dirigir las entregas por correo. Le permiten verificar que su proveedor de correo directo está enviando realmente la comunicación y que no está enviando su lista de clientes a otro proveedor. Consulte [Uso de trampas](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).

Para las entregas por correo directo, las trampas se agregan durante la extracción y se mezclan en el documento de salida. De forma predeterminada, se insertan en el orden de clasificación del archivo de salida, pero puede optar por insertarlo al final o al principio del archivo. Al definir la audiencia, seleccione la opción que desee en la **[!UICONTROL Trap insertion mode]** ficha.

![](assets/direct_mail_trap_insertion_mode.png)
