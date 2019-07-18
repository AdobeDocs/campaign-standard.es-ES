---
title: Entrega en la aplicación
seo-title: Entrega en la aplicación
description: Entrega en la aplicación
seo-description: La actividad de envío desde la propia aplicación permite configurar el envío de un mensaje en la aplicación dentro de un flujo de trabajo.
page-status-flag: no activado nunca
uuid: 528 d 9472-e 447-47 af-a 6 b 2-3181 aa 5 fb 5 ad
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: channel-activities
discoiquuid: 19796 aca -6 e 9 e -4 d 3 a -8917-ba 660 ec 7993 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# In-App delivery{#in-app-delivery}

## Description {#description}

![](assets/wkf_in_app_1.png)

The **In-App delivery** activity allows you to configure sending an In-App message within a workflow. La mensajería en la aplicación permite mostrar un mensaje cuando el usuario está activo dentro de la aplicación. For more information concerning the In-App delivery, refer to this [section](../../channels/using/about-in-app-messaging.md).

## Context of use {#context-of-use}

The **[!UICONTROL In-App delivery]** activity is generally used to automate sending an In-App message to a target audience calculated in the same workflow.

Los destinatarios están definidos como flujo ascendente de la actividad en el mismo flujo de trabajo mediante actividades de segmentación como consultas, intersecciones, etc.

La preparación de los mensajes se activa según los parámetros de ejecución del flujo de trabajo. Desde el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (obligatorio de forma predeterminada). Puede iniciar el flujo de trabajo manualmente o colocar una actividad de programador en el flujo de trabajo para automatizar la ejecución.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Query]** activity to your workflow. Please note that the **[!UICONTROL Query]** activity targeting dimension in the **[!UICONTROL Properties]** tab needs to be updated according to the template chosen in Step 4:

   * Targeting dimension should be set to **[!UICONTROL mobileApp (mobileAppV5)]** for the **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]** template.
   * Targeting dimension should be set to **[!UICONTROL profile (profile)]** for the **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]** template.
   * Targeting dimension should be set to **[!UICONTROL subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** for the **[!UICONTROL Target users based on their Mobile profile (inApp)]** template.

1. Drag and drop a **[!UICONTROL In-App delivery]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.

   >[!NOTE]
   >
   >You can access the general properties and advanced options of the activity (and not of the delivery itself) via the ![](assets/dlv_activity_params-24px.png) button from the activity's quick actions.

   ![](assets/wkf_in_app_3.png)

1. Seleccione el tipo de mensaje En la aplicación. This will depend on the data targeted in your **[!UICONTROL Query]** activity.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: Este tipo de mensaje le permite segmentar perfiles de Adobe Campaign que se han suscrito a su aplicación móvil y personalizar mensajes en la aplicación con atributos de perfil disponibles en Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: Este tipo de mensaje permite enviar un mensaje a todos los usuarios de la aplicación móvil aunque no tengan un perfil existente en Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: Este tipo de mensaje le permite dirigirse a todos los usuarios de una aplicación móvil que tengan un perfil móvil en Campaign, ya sea conocido o desconocido, y para personalizar mensajes en la aplicación con cualquier atributo de perfil obtenido desde dispositivos móviles.
   ![](assets/wkf_in_app_4.png)

1. Enter your In-App message properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.
1. In the **[!UICONTROL Triggers]** tab, drag and drop the event that will trigger your message. Hay tres categorías de eventos disponibles:
1. Defina el contenido dentro de la aplicación. Refer to the section concerning [In-App customization](../../channels/using/customizing-an-in-app-message.md).
1. By default, the **[!UICONTROL In-App delivery]** activity does not include any outbound transitions. If you would like to add an outbound transition to your **[!UICONTROL In-App delivery]** activity, go to the **[!UICONTROL General]** tab of the advanced activity options ( ![](assets/dlv_activity_params-24px.png) button in the activity's quick actions) then check one of the following options:

   * **[!UICONTROL Add outbound transition without the population]**: esto permite generar una transición saliente que contiene exactamente la misma población que la transición entrante.
   * **[!UICONTROL Add outbound transition with the population]**: esto permite generar una transición saliente que contenga la población a la que se envió el mensaje. Los miembros del objetivo excluido durante la preparación de la entrega se excluyen de esta transición.
   ![](assets/wkf_in_app_5.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, se le dirigirá directamente al tablero en la aplicación. Solo se puede editar su contenido.

De forma predeterminada, al iniciar un flujo de trabajo de entrega, se activa la preparación de los mensajes. El envío de mensajes creados a partir de un flujo de trabajo todavía debe confirmarse después de haber iniciado el flujo de trabajo. But from the message dashboard, and only if the message was created from a workflow, you can disable the **[!UICONTROL Request confirmation before sending messages]** option. Al desmarcar esta opción, los mensajes se envían sin previo aviso cuando se realiza la preparación.

## Remarks {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividades de marketing de la aplicación. Puede ver el estado de ejecución del flujo de trabajo mediante el tablero. Los vínculos del panel de resumen de notificaciones Push permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

In the parent deliveries, which can be accessed from the marketing activity list, you can view the total number of sends that have been processed (according to the aggregation period specified when the **[!UICONTROL In-App delivery]** activity was configured). To do this, open the detail view of the parent delivery's **[!UICONTROL Deployment]** block by selecting ![](assets/wkf_dlv_detail_button.png).
