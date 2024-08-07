---
title: Entrega en la aplicación
description: La actividad Entrega en la aplicación permite configurar el envío de un mensaje en la aplicación dentro de un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8d5a35c4-e22b-498e-b71c-c5922cf8c2fd
source-git-commit: 21bcc9818b881212985988ef3377687069a1dbea
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 39%

---

# Entrega en la aplicación{#in-app-delivery}

## Descripción {#description}

![](assets/wkf_in_app_1.png)

La actividad **Envío en la aplicación** le permite configurar el envío de un mensaje en la aplicación dentro de un flujo de trabajo. La mensajería en la aplicación permite mostrar un mensaje cuando el usuario está activo en la aplicación. Para obtener más información sobre la entrega en la aplicación, consulte esta [sección](../../channels/using/about-in-app-messaging.md).

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL In-App delivery]** se utiliza generalmente para automatizar el envío de un mensaje en la aplicación a una audiencia de destinatario calculada en el mismo flujo de trabajo.

Los destinatarios se definen antes de la actividad en el mismo flujo de trabajo, a través de actividades de segmentación como consultas, intersecciones, etc.

La preparación del mensaje se activa según los parámetros de ejecución del flujo de trabajo. En el panel de mensajes, puede seleccionar si desea solicitar o no una confirmación manual para enviar el mensaje (requerido de forma predeterminada). Puede realizar el inicio del flujo de trabajo manualmente o colocar una actividad de planificador en el flujo de trabajo para automatizar la ejecución.

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Query]** en el flujo de trabajo. Tenga en cuenta que la dimensión de segmentación de la actividad **[!UICONTROL Query]** en la ficha **[!UICONTROL Properties]** debe actualizarse según la plantilla elegida en el paso 4:

   * La dimensión de segmentación debe establecerse en **[!UICONTROL mobileApp (mobileAppV5)]** para la plantilla **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**.
   * La dimensión de segmentación debe establecerse en **[!UICONTROL profile (profile)]** para la plantilla **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**.
   * La dimensión de segmentación debe establecerse en **[!UICONTROL subscriptions to an application (`nms:appSubscriptionRcp:appSubscriptionRcpDetail`)]** para la plantilla **[!UICONTROL Target users based on their Mobile profile (inApp)]**.

1. Arrastre y suelte una actividad de **[!UICONTROL In-App delivery]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.

   >[!NOTE]
   >
   >Puede acceder a las propiedades generales y a las opciones avanzadas de la actividad (y no al propio envío) mediante el botón ![](assets/dlv_activity_params-24px.png) de las acciones rápidas de la actividad.

   ![](assets/wkf_in_app_3.png)

1. Seleccione el tipo de mensaje en la aplicación. Esto dependerá de los datos segmentados en su actividad **[!UICONTROL Query]**.

   * **[!UICONTROL Target users based on their Campaign profile (inAppProfile)]**: este tipo de mensaje le permite dirigirse a perfiles de Adobe Campaign que se han suscrito a su aplicación móvil y personalizar mensajes en la aplicación con atributos de perfil disponibles en Campaign.
   * **[!UICONTROL Target all users of a Mobile app (inAppBroadcast)]**: este tipo de mensaje le permite enviar un mensaje a todos los usuarios de la aplicación móvil aunque no tengan un perfil existente en Campaign.
   * **[!UICONTROL Target users based on their Mobile profile (inApp)]**: este tipo de mensaje le permite dirigirse a todos los usuarios de una aplicación móvil que tengan un perfil móvil en Campaign, ya sean conocidos o desconocidos, y personalizar los mensajes en la aplicación con cualquier atributo de perfil que se haya obtenido de un dispositivo móvil.

   ![](assets/wkf_in_app_4.png)

1. Introduzca las propiedades de los mensajes en la aplicación y seleccione la aplicación móvil en el campo **[!UICONTROL Associate a Mobile App to a delivery]**.
1. En la pestaña **[!UICONTROL Triggers]**, arrastre y suelte el evento que activará el mensaje. Hay tres categorías de eventos disponibles:
1. Defina el contenido en la aplicación. Consulte la sección [Personalización en la aplicación](../../channels/using/customizing-an-in-app-message.md).
1. De forma predeterminada, la actividad **[!UICONTROL In-App delivery]** no incluye ninguna transición de salida. Si desea añadir una transición de salida a la actividad **[!UICONTROL In-App delivery]**, vaya a la pestaña **[!UICONTROL General]** de las opciones de actividad avanzadas (botón ![](assets/dlv_activity_params-24px.png) en las acciones rápidas de la actividad) y, a continuación, marque una de las siguientes opciones:

   * **[!UICONTROL Add outbound transition without the population]**: esto le permite generar una transición de salida que contiene exactamente la misma población que la transición de entrada.
   * **[!UICONTROL Add outbound transition with the population]**: esto le permite generar una transición de salida que contiene la población a la que se ha enviado el mensaje. Los miembros destinatarios excluidos durante la preparación del envío se excluyen de esta transición.

   ![](assets/wkf_in_app_5.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

Cuando vuelva a abrir la actividad, le lleva directamente al panel en la aplicación. Solo se puede editar su contenido.

De forma predeterminada, iniciar un flujo de trabajo de envío solo activa la preparación del mensaje. El envío de mensajes creados a partir de un flujo de trabajo aún debe confirmarse una vez iniciado el flujo de trabajo. Sin embargo, desde el panel del mensaje, y solo si el mensaje se ha creado a partir de un flujo de trabajo, puede desactivar la opción **[!UICONTROL Request confirmation before sending messages]**. Al desmarcar esta opción, los mensajes se envían sin previo aviso una vez que se ha realizado la preparación.

## Observaciones {#remarks}

Se puede acceder a los envíos creados dentro de un flujo de trabajo en la lista de actividad de marketing de la aplicación. Puede vista del estado de ejecución del flujo de trabajo mediante el panel. Los vínculos del panel de resumen de las notificaciones push permiten acceder directamente a los elementos vinculados (flujo de trabajo, campaña, etc.).

En los envíos principales, a los que se puede acceder desde la lista de actividad de marketing, se puede ver el número total de envíos que se han procesado (según el periodo de acumulación especificado cuando se configuró la actividad **[!UICONTROL In-App delivery]**). Para ello, abra la vista de detalles del bloque del envío principal **[!UICONTROL Deployment]** seleccionando ![](assets/wkf_dlv_detail_button.png).
