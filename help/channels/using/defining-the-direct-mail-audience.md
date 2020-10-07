---
title: Definición de la audiencia de correo postal
description: Aprenda a definir el destinatario de su envío de correo postal.
page-status-flag: never-activated
uuid: f843e368-5c07-4b53-8943-46f7bf45b62b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: f993d1b6-4b9a-4f95-81fc-60c126211bd2
context-tags: delivery,directMailContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 100%

---


# Definición de la audiencia de correo postal{#defining-the-direct-mail-audience}

Puede definir la audiencia en el asistente de creación o haciendo clic en la sección de **Audiencia** del panel de envío.

![](assets/direct_mail_15.png)

## Definición del destinatario principal {#defining-the-main-target}

Para el correo postal, los perfiles de destino son los que se incluyen en el archivo de extracción que ha de enviar a su proveedor de correo postal.

Para cada perfil de destino se añade una nueva línea en el archivo de extracción. La cantidad de información de perfiles que se incluye para cada destinatario se define en la pantalla [Definición de la extracción](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction).

>[!CAUTION]
>
>Asegúrese de que los perfiles incluyan una dirección postal, ya que esta información es esencial para el proveedor de correo. Asegúrese también de haber marcado la casilla **[!UICONTROL Address specified]** en la información de los perfiles. Consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations).

## Añadir perfiles de prueba y trampa {#adding-test-and-trap-profiles}

Añada perfiles de prueba para poder probar el archivo con un pequeño número de perfiles. Permite crear rápidamente un ejemplo de archivo para probar y validar la estructura antes de preparar el archivo real. Consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

El uso de trampas es esencial para dirigir envíos de correo postal. Permiten comprobar que su proveedor de correo postal realmente envía la comunicación y que no relega la lista de su cliente a otro proveedor. Consulte [Uso de trampas](../../sending/using/using-traps.md).

Para las entregas de correo postal, las trampas se añaden durante la extracción y la mezcla en el documento de salida. De forma predeterminada, se insertan en el orden de clasificación del archivo de salida, pero se puede elegir insertarlos al final o al principio del archivo. Al definir la audiencia, seleccione la opción que desee en la pestaña **[!UICONTROL Trap insertion mode]**.

![](assets/direct_mail_trap_insertion_mode.png)
