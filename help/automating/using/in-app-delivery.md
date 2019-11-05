---
title: Entrega en la aplicación
description: La actividad de entrega en la aplicación permite configurar el envío de un mensaje en la aplicación dentro de un flujo de trabajo.
page-status-flag: nunca activado
uuid: 528d9472-e447-47af-a6b2-3181aa5fb5ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: channel-activity
discoiquuid: 19796aca-6e9e-4d3a-8917-ba660ec7993c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Entrega en la aplicación{#in-app-delivery}

## Descripción {#description}

![](assets/wkf_in_app_1.png)

La actividad de entrega **** en la aplicación permite configurar el envío de un mensaje en la aplicación dentro de un flujo de trabajo. La mensajería en la aplicación le permite mostrar un mensaje cuando el usuario está activo en la aplicación. Para obtener más información sobre la entrega en la aplicación, consulte esta [sección](../../channels/using/about-in-app-messaging.md).

## Contexto de uso {#context-of-use}

La **[!UICONTROL In-App delivery]** actividad se utiliza generalmente para automatizar el envío de un mensaje en la aplicación a una audiencia de destino calculada en el mismo flujo de trabajo.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Query]** actividad en el flujo de trabajo. Tenga en cuenta que la dimensión de segmentación de **[!UICONTROL Query]** actividades de la **[!UICONTROL Properties]** ficha debe actualizarse según la plantilla elegida en el paso 4:

   * La dimensión de objetivo debe establecerse en **[!UICONTROL mobileApp (mobileAppV5)]** para la **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** plantilla.
   * La dimensión de objetivo debe establecerse en **[!UICONTROL profile (profile)]** para la **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** plantilla.
   * La dimensión de objetivo debe establecerse en **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** para la **[!UICONTROL Target users based on their Mobile profile (inApp)]** plantilla.

1. Arrastre y suelte una **[!UICONTROL In-App delivery]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no a la propia entrega) mediante el ![](assets/dlv_activity_params-24px.png) botón de las acciones rápidas de la actividad.

   ![](assets/wkf_in_app_3.png)

1. Seleccione el tipo de mensaje en la aplicación. Esto dependerá de los datos dirigidos a su **[!UICONTROL Query]** actividad.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**:: Este tipo de mensaje le permite dirigirse a los perfiles de Adobe Campaign que se han suscrito a su aplicación móvil y personalizar los mensajes en la aplicación con atributos de perfil disponibles en Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**:: Este tipo de mensaje le permite enviar un mensaje a todos los usuarios de la aplicación móvil aunque no tengan un perfil existente en Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**:: Este tipo de mensaje le permite dirigirse a todos los usuarios de una aplicación móvil que tengan un perfil móvil en Campaign, ya sea conocido o desconocido, y personalizar los mensajes en la aplicación con cualquier atributo de perfil obtenido desde un dispositivo móvil.
   ![](assets/wkf_in_app_4.png)

1. Introduzca las propiedades de los mensajes en la aplicación y seleccione la aplicación móvil en el **[!UICONTROL Associate a Mobile App to a delivery]** campo.
1. En la **[!UICONTROL Triggers]** ficha, arrastre y suelte el evento que activará el mensaje. Existen tres categorías de eventos:
1. Defina el contenido en la aplicación. Consulte la sección sobre personalización [en la aplicación](../../channels/using/customizing-an-in-app-message.md).
1. De forma predeterminada, la **[!UICONTROL In-App delivery]** actividad no incluye ninguna transición de salida. Si desea agregar una transición de salida a su **[!UICONTROL In-App delivery]** actividad, vaya a la **[!UICONTROL General]** ficha de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**:: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**:: esto le permite generar una transición de salida que contiene la población a la que se envió el mensaje. Los miembros del objetivo excluidos durante la preparación de la entrega quedan excluidos de esta transición.
   ![](assets/wkf_in_app_5.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelve a abrir la actividad, se le redirige directamente al panel en la aplicación. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de entrega solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el tablero de mensajes y solo si el mensaje se creó a partir de un flujo de trabajo, puede desactivar la **[!UICONTROL Request confirmation before sending messages]** opción. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a las entregas creadas en un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de notificaciones push le permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

En las entregas principales, a las que se puede acceder desde la lista de actividades de marketing, puede ver el número total de envíos que se han procesado (según el período de agregación especificado cuando se configuró la **[!UICONTROL In-App delivery]** actividad). Para ello, abra la vista de detalles del **[!UICONTROL Deployment]** bloque de entrega principal seleccionando ![](assets/wkf_dlv_detail_button.png).
