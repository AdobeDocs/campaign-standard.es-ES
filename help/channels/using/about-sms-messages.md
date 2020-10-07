---
title: Acerca de los mensajes SMS
description: Descubra las principales características del canal SMS en Adobe Campaign.
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 32%

---


# Acerca de los mensajes SMS{#about-sms-messages}

Adobe Campaign le permite enviar mensajes SMS (Servicio de mensajes cortos).

>[!NOTE]
>
>El canal SMS es un complemento. Compruebe el acuerdo de licencia.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

La longitud de un mensaje SMS está restringida a 160 caracteres si está en codificación GSM y sólo a 70 caracteres si está en Unicode. Sin embargo, algunos caracteres especiales pueden influir en la longitud del mensaje. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

Los mensajes SMS se pueden crear desde el **[!UICONTROL Marketing activities]** menú, desde una campaña o en un flujo de trabajo, consulte [Creación de un mensaje](../../channels/using/creating-an-sms-message.md)SMS.

Para enviar mensajes SMS a un teléfono móvil necesitas:

* Una cuenta externa de **[!UICONTROL Routing]** configurada en el canal **[!UICONTROL Mobile (SMS)]** con el modo **[!UICONTROL Bulk delivery]**. Para obtener más información, consulte la sección [Enrutamiento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* Una plantilla de envíos que esté correctamente vinculada a esta cuenta externa.

**Temas relacionados:**

* [Administración de plantillas](../../start/using/marketing-activity-templates.md)
* [Configuración de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Informe SMS](../../reporting/using/sms-report.md)
* [Guía de Campaign Standard Mobile](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html)

## PLANTILLA DE ENVÍOS SMS {#sms-delivery-template}

Adobe Campaign oferta una Plantilla de envíos para dispositivos móviles. Esta plantilla debe estar correctamente vinculada a la cuenta externa utilizada para el **[!UICONTROL Mobile (SMS)]** canal. Para acceder y modificarlo:

1. Seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery templates]** en el menú avanzado.
1. Pase el ratón sobre la **[!UICONTROL Send via SMS]** plantilla y seleccione la opción de elemento **de** Duplicado.
1. Seleccione la nueva plantilla.
1. Haga clic en el botón **[!UICONTROL Edit properties]**.
1. En la **[!UICONTROL Advanced parameters]** sección de las propiedades de la plantilla, asegúrese de que la plantilla está vinculada a la cuenta externa que se va a utilizar para enviar SMS.

   ![](assets/sms_template.png)

**Temas relacionados:**

* [Administración de plantillas](../../start/using/marketing-activity-templates.md)
