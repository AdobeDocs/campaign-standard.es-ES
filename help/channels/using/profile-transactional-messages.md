---
title: Mensajes transaccionales de perfil
description: Obtenga información sobre cómo crear y publicar un mensaje transaccional de perfil.
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
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Mensajes transaccionales de perfil{#profile-transactional-messages}

Puede enviar mensajes transaccionales en función de los perfiles de mercadotecnia del cliente, lo que le permite:

* Aplicar reglas de tipología de marketing como **[!UICONTROL Blacklisted address]** o reglas de [fatiga](../../sending/using/fatigue-rules.md).
* Incluya el vínculo baja dentro de los mensajes.
* Añadir los mensajes transaccionales al sistema de informes de envío global.
* Aproveche los mensajes transaccionales en el viaje del cliente.

Una vez creado y publicado un evento (el abandono del carro de compras según el [ejemplo](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) anterior), el mensaje transaccional correspondiente se crea automáticamente.

Los pasos de configuración se presentan en la sección [Configuración de un evento para enviar un mensaje transaccional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de perfil.

Para que el evento active el envío de un mensaje transaccional, debe personalizar el mensaje, probarlo y publicarlo.

>[!NOTE]
>
>Para acceder a mensajes transaccionales, debe formar parte del grupo de **[!UICONTROL Administrators (all units)]** seguridad.
>
>Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte Reglas [de fatiga](../../sending/using/fatigue-rules.md).

## Envío de un mensaje transaccional de perfil {#sending-a-profile-transactional-message}

Los pasos para crear, personalizar y publicar un mensaje transaccional de perfil son los mismos que para un mensaje transaccional de evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Las diferencias se enumeran a continuación.

1. Vaya al mensaje transaccional que se creó para editarlo.
1. En el mensaje transaccional, haga clic en la **[!UICONTROL Content]** sección . Además de la plantilla transaccional, también puede elegir cualquier objetivo de plantilla de correo electrónico **[!UICONTROL Profile]**.

   ![](assets/message-center_marketing_templates.png)

1. Seleccione la plantilla de correo electrónico predeterminada.

   Al igual que todos los correos electrónicos de marketing, incluye un vínculo baja.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   Además, a diferencia de las configuraciones basadas en eventos en tiempo real, tiene acceso directo a toda la información de perfil para personalizar su mensaje. See [Inserting a personalization field](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Guarde los cambios y publique el mensaje. Consulte [Publicación de un mensaje transaccional](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Monitoreo de un envío de mensaje transaccional de perfil {#monitoring-a-profile-transactional-message-delivery}

Una vez que se publique el mensaje y se haya completado la integración del sitio, puede supervisar el envío.

1. Para vista del registro de envíos de mensajes, haga clic en el icono situado en la parte inferior derecha del **[!UICONTROL Deployment]** bloque.

   Para obtener más información sobre el acceso a los registros, consulte [Supervisión del envío](../../sending/using/monitoring-a-delivery.md).

1. Select the **[!UICONTROL Sending logs]** tab. En la **[!UICONTROL Status]** columna, **[!UICONTROL Sent]** indica que un perfil ha adhesión.

   ![](assets/message-center_marketing_sending_logs.png)

1. Seleccione la **[!UICONTROL Exclusions logs]** ficha para vista de destinatarios que se han excluido del destinatario de mensajes, como direcciones en la lista negra.

   ![](assets/message-center_marketing_exclusion_logs.png)

Para cualquier perfil que haya exclusión, la **[!UICONTROL Blacklisted address]** reglas de tipología excluyó el destinatario correspondiente.

Esta regla forma parte de una tipología específica que se aplica a todos los mensajes transaccionales basados en la **[!UICONTROL Profile]** tabla.

![](assets/message-center_marketing_typology.png)

**Temas relacionados**:

* [Integración del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Tipologías](../../sending/using/about-typology-rules.md)

