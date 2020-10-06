---
title: Mensajes transaccionales de perfil
description: Aprenda a crear y publicar un mensaje transaccional de perfil.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 9c812b0b622b82ba7aa382f04edb7a2a3f717cd4
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 95%

---


# Mensajes transaccionales de perfil{#profile-transactional-messages}

Puede enviar mensajes transaccionales en función de los perfiles de marketing del cliente, lo que le permite lo siguiente:

* Aplicar reglas de tipología de marketing como **[!UICONTROL Address on denylist]** o [reglas de fatiga](../../sending/using/fatigue-rules.md).
* Incluir vínculos de baja en los mensajes.
* Añadir mensajes transaccionales al sistema de informes de envío global.
* Aprovechar mensajes transaccionales en el recorrido del cliente.

Una vez creado y publicado un evento (el abandono del carro de compras según el [ejemplo](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) anterior), se crea el mensaje transaccional correspondiente automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje transaccional de perfil](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de seguridad **[!UICONTROL Administrators (all units)]**.
>
>Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

## Envío de un mensaje transaccional de perfil {#sending-a-profile-transactional-message}

Los pasos para crear, personalizar y publicar un mensaje transaccional de perfil son los mismos que para un mensaje transaccional de evento. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).

Las diferencias se enumeran a continuación.

1. Vaya al mensaje transaccional que se creó para editarlo.
1. En el mensaje transaccional, haga clic en la sección **[!UICONTROL Content]**. Además de la plantilla transaccional, también puede elegir cualquier objetivo de plantilla de correo electrónico para **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleccione la plantilla de correo electrónico predeterminada.

   Al igual que todos los correos electrónicos de marketing, incluye un vínculo de baja.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Además, a diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar su mensaje. Consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitorización de un envío de mensaje transaccional de perfil {#monitoring-a-profile-transactional-message-delivery}

Una vez que se publique el mensaje y se haya completado la integración del sitio, puede supervisar el envío.

1. Para ver el registro de envíos de mensajes, haga clic en el icono situado en la parte inferior derecha del bloque **[!UICONTROL Deployment]**.

   Para obtener más información sobre el acceso a los registros, consulte [Monitorización del envío](../../sending/using/monitoring-a-delivery.md).

1. Seleccione la pestaña **[!UICONTROL Sending logs]** En la columna **[!UICONTROL Status]**, **[!UICONTROL Sent]** indica que un perfil se ha suscrito.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as addresses on denylist.

   ![](assets/message-center_marketing_exclusion_logs.png)

En el caso de cualquier perfil que se haya excluido, la regla de tipología **[!UICONTROL Address on denylist]** excluyó el destinatario correspondiente.

Esta regla forma parte de una tipología específica que se aplica a todos los mensajes transaccionales basados en la tabla **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Temas relacionados**:

* [Integración del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologías](../../sending/using/about-typology-rules.md)
