---
title: Previsualización de mensajes
description: Obtenga información sobre cómo previsualizar un mensaje en el editor de contenido o en el Designer de correo electrónico.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Seed Address
role: User
level: Intermediate
exl-id: ac8c1265-f530-4438-ab2d-3ca17615ca85
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 16%

---

# Vista previa de envíos {#previewing-messages}

## Previsualización de correos electrónicos {#previewing-emails}

Campaign Standard permite obtener una vista previa de los mensajes antes de enviarlos para comprobar su personalización y cómo los verán los destinatarios.

La vista previa de mensajes se realiza con **perfiles de prueba** que agrega al destinatario del mensaje.

Para los mensajes de **email**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de destino en lugar de perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md).

Para obtener una vista previa de un mensaje mediante perfiles de prueba, siga estos pasos:

1. En [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), haga clic en el botón **[!UICONTROL Preview]**.

   ![](assets/sending_preview.png)

   Se muestran una vista de escritorio y una vista móvil adaptable de su correo electrónico en paralelo.

1. Durante cada previsualización se realiza una comprobación automática del contenido no deseado. Haga clic en el botón **[!UICONTROL Anti-spam analysis]** para obtener más información sobre la advertencia.

   ![](assets/sending_anti-spam_analysis.png)

1. Seleccione el botón **[!UICONTROL Change profile]** para elegir el perfil de prueba en el que desea probar los elementos de personalización.

   ![](assets/sending_test-profile.png)

1. Para salir del modo **[!UICONTROL Preview]**, haga clic en el botón **[!UICONTROL Edit]** en la parte superior izquierda de la pantalla.

   ![](assets/sending_preview_edit.png)

**Temas relacionados**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)

## Previsualización de mensajes SMS {#previewing-sms}

Para **mensajes SMS**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para obtener una vista previa de un mensaje SMS con perfiles de prueba, siga estos pasos:

1. Una vez que haya completado **[!UICONTROL Properties]** de su mensaje SMS y haya seleccionado sus audiencias, puede personalizar su envío. Para obtener más información, consulte [sección](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. Después de personalizar el contenido, haga clic en **[!UICONTROL Create]** para obtener acceso a la ventana de **[!UICONTROL Summary]**.

1. En la ventana **[!UICONTROL Summary]**, haga clic en **[!UICONTROL Content]** para obtener una vista previa del envío.

   ![](assets/sms_preview_2.png)

1. Haga clic en **[!UICONTROL Preview]** en la barra de herramientas.

   ![](assets/sms_preview_3.png)

1. Haga clic en **[!UICONTROL Change profile]** para seleccionar el perfil de prueba y luego **[!UICONTROL Confirm]**.

   ![](assets/sms_preview_4.png)

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

**Temas relacionados**

* [Acerca de los mensajes SMS](../../channels/using/about-sms-messages.md)
* [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md)
* [Personalización de mensajes SMS](../../channels/using/personalizing-sms-messages.md)

## Previsualización de notificaciones push {#previewing-push}

Para **notificación push**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para previsualizar una notificación push mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya completado **[!UICONTROL Properties]** de la notificación push y haya seleccionado las audiencias, puede personalizar la entrega. Para obtener más información, consulte [Personalizar una notificación push](../../channels/using/customizing-a-push-notification.md).

1. Después de personalizar el contenido, puede comprobar directamente el procesamiento de las notificaciones push en función de los dispositivos y el sistema operativo en la ventana de vista previa.

   ![](assets/push_preview.png)

1. Para previsualizar la notificación push mediante perfiles de prueba, haga clic en **[!UICONTROL Preview with test profile]**.

   ![](assets/push_preview_2.png)

1. Seleccione el perfil de prueba y después **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/push_preview_3.png)

**Temas relacionados**

* [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md)
* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Personalización de una notificación push](../../channels/using/customizing-a-push-notification.md)

## Vista previa de mensajes en la aplicación {#previewing-in-app}

Para **En la aplicación**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para obtener una vista previa de un mensaje en la aplicación mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya rellenado **[!UICONTROL Properties]** de su mensaje en la aplicación, haya seleccionado las audiencias y haya establecido **[!UICONTROL Triggers]**, puede personalizar su envío. Para obtener más información, consulte [Personalizar un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md).

1. Después de personalizar el contenido, puede comprobar directamente el procesamiento del mensaje en la aplicación en función de los dispositivos y el sistema operativo en la ventana de vista previa.

   ![](assets/in_app_preview.png)

1. Para obtener una vista previa del mensaje en la aplicación mediante perfiles de prueba, haga clic en **[!UICONTROL Preview]**.

   ![](assets/in_app_preview_2.png)

1. Seleccione el perfil de prueba y después **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/in_app_preview_3.png)

**Temas relacionados**

* [Acerca de la mensajería en la aplicación](../../channels/using/about-in-app-messaging.md)
* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md)
