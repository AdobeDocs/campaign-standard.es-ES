---
title: Mensajes transaccionales de perfil
seo-title: Mensajes transaccionales de perfil
description: Mensajes transaccionales de perfil
seo-description: Obtenga información sobre cómo crear y publicar un mensaje transaccional de perfil.
page-status-flag: nunca activado
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: transaccional-mensajería
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Mensajes transaccionales de perfil{#profile-transactional-messages}

Puede enviar mensajes transaccionales basados en perfiles de marketing de clientes, lo que le permite:

* Aplicar reglas de tipología de marketing como **[!UICONTROL Blacklisted address]** o reglas [de](../../administration/using/fatigue-rules.md)fatiga.
* Incluya el vínculo de cancelación de suscripción en los mensajes.
* Agregue los mensajes transaccionales a los informes de entrega global.
* Aproveche los mensajes transaccionales en el viaje del cliente.

Una vez creado y publicado un evento (el abandono del carro de compras según el [ejemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) anterior), el mensaje transaccional correspondiente se crea automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transaccional de perfil.

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración o aparecer en el grupo de seguridad **[!UICONTROL Message Center agents]** (mcExec). Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

## Envío de un mensaje transaccional de perfil {#sending-a-profile-transactional-message}

Los pasos para crear, personalizar y publicar un mensaje transaccional de perfil son los mismos que para un mensaje transaccional de evento. Consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.

Las diferencias se enumeran a continuación.

1. Vaya al mensaje transaccional que se creó para editarlo.
1. En el mensaje transaccional, haga clic en la **[!UICONTROL Content]** sección . Además de la plantilla transaccional, también puede elegir la plantilla de correo electrónico predeterminada, que se dirige **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleccione la plantilla de correo electrónico predeterminada.

   Al igual que todos los correos electrónicos de marketing, incluye un vínculo de cancelación de suscripción.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Además, a diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar su mensaje. Consulte [Inserción de un campo](../../designing/using/personalization.md#inserting-a-personalization-field)de personalización.

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message)transaccional.

## Supervisión de la entrega de mensajes transaccionales de perfil {#monitoring-a-profile-transactional-message-delivery}

Una vez que se publique el mensaje y se haya completado la integración del sitio, puede supervisar la entrega.

1. Para ver el registro de entrega de mensajes, haga clic en el icono en la parte inferior derecha del **[!UICONTROL Deployment]** bloque.

   Para obtener más información sobre el acceso a los registros, consulte [Supervisión del envío](../../sending/using/monitoring-a-delivery.md).

1. Seleccione la **[!UICONTROL Sending logs]** ficha. En la **[!UICONTROL Status]** columna, **[!UICONTROL Sent]** indica que un perfil ha elegido.

   ![](assets/message-center_marketing_sending_logs.png)

1. Seleccione la **[!UICONTROL Exclusions logs]** ficha para ver los destinatarios que se han excluido del destino del mensaje, como las direcciones bloqueadas.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para cualquier perfil que haya optado por no participar, la regla de **[!UICONTROL Blacklisted address]** tipología excluyó al destinatario correspondiente.

Esta regla forma parte de una tipología específica que se aplica a todos los mensajes transaccionales basados en la **[!UICONTROL Profile]** tabla.

![](assets/message-center_marketing_typology.png)

**Temas** relacionados:

* [Integración del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipos](../../administration/using/about-typology-rules.md)

