---
title: Acerca de los mensajes SMS
description: Descubra las principales características del canal SMS en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 30%

---

# Acerca de los mensajes SMS{#about-sms-messages}

Adobe Campaign le permite enviar mensajes SMS (servicio de mensajes cortos).

>[!NOTE]
>
>El canal SMS es un complemento. Compruebe el acuerdo de licencia.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

La longitud de un mensaje SMS está restringida a 160 caracteres si está en codificación GSM y solo a 70 caracteres si está en Unicode. Sin embargo, ciertos caracteres especiales pueden influir en la longitud del mensaje. Para obtener más información, consulte la sección [Codificación SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

Los mensajes SMS se pueden crear desde el menú **[!UICONTROL Marketing activities]**, desde una campaña o en un flujo de trabajo. Consulte [Creación de un mensaje SMS](../../channels/using/creating-an-sms-message.md).

Para enviar mensajes SMS a un teléfono móvil necesita:

* Una cuenta externa de **[!UICONTROL Routing]** configurada en el canal **[!UICONTROL Mobile (SMS)]** con el modo **[!UICONTROL Bulk delivery]**. Para obtener más información, consulte la sección [Enrutamiento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Una plantilla de envíos que esté correctamente vinculada a esta cuenta externa.

**Temas relacionados:**

* [Administración de plantillas](../../start/using/marketing-activity-templates.md)
* [Configuración de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Informe SMS](../../reporting/using/sms-report.md)
* [Guía de Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Plantilla de envíos por SMS {#sms-delivery-template}

Adobe Campaign ofrece una plantilla de envíos para dispositivos móviles. Esta plantilla debe estar vinculada correctamente a la cuenta externa utilizada para el canal **[!UICONTROL Mobile (SMS)]**. Para acceder y modificarla:

1. Seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** en el menú avanzado.
1. Pase el ratón sobre la plantilla **[!UICONTROL Send via SMS]** y seleccione la opción **Duplicar elemento**.
1. Seleccione la nueva plantilla.
1. Haga clic en el botón **[!UICONTROL Edit properties]**.
1. En la sección **[!UICONTROL Advanced parameters]** de las propiedades de la plantilla, asegúrese de que la plantilla esté vinculada a la cuenta externa que se utilizará para enviar SMS.

   ![](assets/sms_template.png)

**Temas relacionados:**

* [Administración de plantillas](../../start/using/marketing-activity-templates.md)
