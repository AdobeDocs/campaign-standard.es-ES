---
title: Vista previa de mensajes
description: Obtenga información sobre cómo previsualización de un mensaje en el editor de contenido o en el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 8dffca95-59fe-4e9b-93cb-73b33ffde020
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 8428f8ac-8ef5-46cd-9d93-10ec0ecd3ded
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 15%

---


# Vista previa de entregas {#previewing-messages}

## Vista previa de correos electrónicos {#previewing-emails}

Campaign Standard le permite realizar previsualizaciones de mensajes antes de enviarlos, para comprobar su personalización y cómo los verán sus destinatarios.

La previsualización de mensajes se realiza mediante perfiles **de** prueba que se agregan al destinatario del mensaje.

En el caso de los mensajes de **correo electrónico** , el Campaign Standard le permite realizar previsualizaciones de mensajes mediante perfiles de destino en lugar de probar perfiles. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md).

Para previsualización de un mensaje mediante perfiles de prueba, siga estos pasos:

1. En el Diseñador de [correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md), haga clic en el **[!UICONTROL Preview]** botón .

   ![](assets/sending_preview.png)

   Una vista de escritorio y una vista móvil adaptable del correo electrónico se muestran una al lado de la otra.

1. Durante cada previsualización se realiza una comprobación automática del contenido no deseado. Haga clic en el **[!UICONTROL Anti-spam analysis]** botón para obtener más información sobre la advertencia.

   ![](assets/sending_anti-spam_analysis.png)

1. Seleccione el **[!UICONTROL Change profile]** botón para elegir el perfil de prueba en el que desea probar los elementos de personalización.

   ![](assets/sending_test-profile.png)

1. Para salir del **[!UICONTROL Preview]** modo, haga clic en el **[!UICONTROL Edit]** botón situado en la parte superior izquierda de la pantalla.

   ![](assets/sending_preview_edit.png)

**Temas relacionados**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)

## Vista previa de mensajes SMS {#previewing-sms}

En el caso de los mensajes **SMS** , el Campaign Standard le permite realizar previsualizaciones de mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para previsualización de un mensaje SMS mediante perfiles de prueba, siga estos pasos:

1. Una vez que hayas completado el mensaje **[!UICONTROL Properties]** de SMS y seleccionado tus audiencias, puedes personalizar tu envío. For more information, refer to [section](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_preview.png)

1. Después de personalizar el contenido, haga clic en **[!UICONTROL Create]** para acceder a la **[!UICONTROL Summary]** ventana.

1. Desde la **[!UICONTROL Summary]** ventana, haga clic en **[!UICONTROL Content]** para obtener una vista previa del inicio del envío.

   ![](assets/sms_preview_2.png)

1. Haga clic **[!UICONTROL Preview]** en la barra de herramientas.

   ![](assets/sms_preview_3.png)

1. Haga clic **[!UICONTROL Change profile]** para seleccionar el perfil de prueba y, a continuación, **[!UICONTROL Confirm]**.

   ![](assets/sms_preview_4.png)

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

**Temas relacionados**

* [Acerca de los mensajes SMS](../../channels/using/about-sms-messages.md)
* [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md)
* [Personalización de mensajes SMS](../../channels/using/personalizing-sms-messages.md)

## Vista previa de notificaciones push {#previewing-push}

En el caso de las notificaciones **** push, el Campaign Standard permite realizar previsualizaciones de mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para previsualización de una notificación Push mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya completado la notificación **[!UICONTROL Properties]** push y seleccionado las audiencias, podrá personalizar su envío. Para obtener más información, consulte [Personalización de una notificación](../../channels/using/customizing-a-push-notification.md)push.

1. Después de personalizar el contenido, puede comprobar directamente el procesamiento de las notificaciones push en función de los dispositivos y el sistema operativo en la ventana de previsualización.

   ![](assets/push_preview.png)

1. Para previsualización de la notificación push mediante perfiles de prueba, haga clic en **[!UICONTROL Preview with test profile]**.

   ![](assets/push_preview_2.png)

1. Seleccione el perfil de la prueba **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/push_preview_3.png)

**Temas relacionados**

* [Acerca de las notificaciones push](../../channels/using/about-push-notifications.md)
* [Preparación y envío de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md)
* [Personalización de una notificación push](../../channels/using/customizing-a-push-notification.md)

## Vista previa de mensajes en la aplicación {#previewing-in-app}

En el caso de **In-App**, Campaign Standard le permite realizar previsualizaciones de mensajes mediante perfiles de prueba. Esto le permite obtener una representación exacta del mensaje que recibirá un perfil específico. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

Para previsualización de un mensaje en la aplicación mediante perfiles de prueba, siga estos pasos:

1. Una vez que haya rellenado el mensaje en la aplicación, haya seleccionado las audiencias y haya configurado el **[!UICONTROL Properties]** mensaje en la aplicación, **[!UICONTROL Triggers]** podrá personalizar el envío. Para obtener más información, consulte [Personalización de un mensaje](../../channels/using/customizing-an-in-app-message.md)en la aplicación.

1. Después de personalizar el contenido, puede comprobar directamente la representación del mensaje en la aplicación en función de los dispositivos y el sistema operativo en la ventana de previsualización.

   ![](assets/in_app_preview.png)

1. Para previsualización del mensaje en la aplicación mediante perfiles de prueba, haga clic en **[!UICONTROL Preview]**.

   ![](assets/in_app_preview_2.png)

1. Seleccione el perfil de la prueba **[!UICONTROL Confirm]**.

Ahora puede ver la representación exacta del mensaje en función de los perfiles de prueba seleccionados.

![](assets/in_app_preview_3.png)

**Temas relacionados**

* [Acerca de la mensajería en la aplicación](../../channels/using/about-in-app-messaging.md)
* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)
* [Personalización de un mensaje en la aplicación](../../channels/using/customizing-an-in-app-message.md)