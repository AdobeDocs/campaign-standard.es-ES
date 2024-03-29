---
title: Previsualización de mensajes
description: Obtenga información sobre cómo obtener una vista previa de un mensaje en el editor de contenido o en el Diseñador de correo electrónico.
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

La previsualización de mensajes se realiza mediante **Perfiles de prueba** que se añade al destinatario del mensaje.

Para **email** , el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de destino en lugar de perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md).

Para obtener una vista previa de un mensaje mediante perfiles de prueba, siga estos pasos:

1. En el [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md), haga clic en **[!UICONTROL Preview]** botón.

   ![](assets/sending_preview.png)

   Se muestran una vista de escritorio y una vista móvil adaptable de su correo electrónico en paralelo.

1. Durante cada previsualización se realiza una comprobación automática del contenido no deseado. Haga clic en **[!UICONTROL Anti-spam analysis]** para obtener más información sobre la advertencia.

   ![](assets/sending_anti-spam_analysis.png)

1. Seleccione el **[!UICONTROL Change profile]** para elegir el perfil de prueba en el que desea probar los elementos de personalización.

   ![](assets/sending_test-profile.png)

1. Para salir del **[!UICONTROL Preview]** modo, haga clic en **[!UICONTROL Edit]** en la parte superior izquierda de la pantalla.

   ![](assets/sending_preview_edit.png)

**Temas relacionados**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)

## Previsualización de mensajes SMS {#previewing-sms}

Para **SMS** mensajes, Campaign Standard permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para obtener una vista previa de un mensaje SMS con perfiles de prueba, siga estos pasos:

1. Una vez que haya rellenado el **[!UICONTROL Properties]** de su mensaje SMS y seleccionó sus audiencias, puede personalizar su envío. Para obtener más información, consulte [sección](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. Después de personalizar el contenido, haga clic en **[!UICONTROL Create]** para acceder a **[!UICONTROL Summary]** ventana.

1. Desde el **[!UICONTROL Summary]** , haga clic en **[!UICONTROL Content]** para obtener una vista previa del envío.

   ![](assets/sms_preview_2.png)

1. Clic **[!UICONTROL Preview]** en la barra de herramientas.

   ![](assets/sms_preview_3.png)

1. Clic **[!UICONTROL Change profile]** para seleccionar el perfil de prueba **[!UICONTROL Confirm]**.

   ![](assets/sms_preview_4.png)

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

**Temas relacionados**

* [Acerca de los mensajes SMS](../../channels/using/about-sms-messages.md)
* [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md)
* [Personalización de mensajes SMS](../../channels/using/personalizing-sms-messages.md)

## Previsualización de notificaciones push {#previewing-push}

Para **Notificación push**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para previsualizar una notificación push mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya rellenado el **[!UICONTROL Properties]** de la notificación push y seleccionó las audiencias, puede personalizar el envío. Para obtener más información, consulte [Personalización de una notificación push](../../channels/using/customizing-a-push-notification.md).

1. Después de personalizar el contenido, puede comprobar directamente el procesamiento de las notificaciones push en función de los dispositivos y el sistema operativo en la ventana de vista previa.

   ![](assets/push_preview.png)

1. Para previsualizar la notificación push mediante perfiles de prueba, haga clic en **[!UICONTROL Preview with test profile]**.

   ![](assets/push_preview_2.png)

1. Seleccione el perfil de prueba y luego **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/push_preview_3.png)

**Temas relacionados**

* [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md)
* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Personalización de una notificación push](../../channels/using/customizing-a-push-notification.md)

## Vista previa de mensajes en la aplicación {#previewing-in-app}

Para **En la aplicación**, el Campaign Standard le permite obtener una vista previa de los mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para obtener una vista previa de un mensaje en la aplicación mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya rellenado el **[!UICONTROL Properties]** del mensaje en la aplicación, seleccione las audiencias y configure las **[!UICONTROL Triggers]**, puede personalizar su envío. Para obtener más información, consulte [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md).

1. Después de personalizar el contenido, puede comprobar directamente el procesamiento del mensaje en la aplicación en función de los dispositivos y el sistema operativo en la ventana de vista previa.

   ![](assets/in_app_preview.png)

1. Para obtener una vista previa del mensaje en la aplicación mediante perfiles de prueba, haga clic en **[!UICONTROL Preview]**.

   ![](assets/in_app_preview_2.png)

1. Seleccione el perfil de prueba y luego **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/in_app_preview_3.png)

**Temas relacionados**

* [Acerca de la mensajería en la aplicación](../../channels/using/about-in-app-messaging.md)
* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md)
