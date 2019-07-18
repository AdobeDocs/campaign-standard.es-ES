---
title: Acerca de los mensajes SMS
seo-title: Acerca de los mensajes SMS
description: Acerca de los mensajes SMS
seo-description: Descubrir las principales especificidades del canal SMS en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 14 dc 7434-8171-4 ad 1-9540-52 ca 637659 a 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134 fe 72-77 de -4 fd 0-b 794-4 d 966 effaccf
delivercontext-tags: Deliverycreation, wizard; entrega, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About SMS messages{#about-sms-messages}

Adobe Campaign permite enviar mensajes SMS (servicio de mensajes cortos).

>[!NOTE]
>
>SMS channel es un complemento. Verifique su contrato de licencia.

Para los mensajes SMS, puede crear, modificar y personalizar mensajes solo en formato de texto. También puede obtener una vista previa de los mensajes SMS antes de enviarlos.

La longitud de un mensaje SMS está restringida a 160 caracteres si se encuentra en codificación GSM y solo 70 caracteres si se encuentra en Unicode. Sin embargo, ciertos caracteres especiales pueden influir en la longitud del mensaje. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

SMS messages can be created from the **[!UICONTROL Marketing activities]** menu, from a campaign, or in a workflow, see [Creating an SMS message](../../channels/using/creating-an-sms-message.md).

Para enviar mensajes SMS a un teléfono móvil que necesite:

* A **[!UICONTROL Routing]** external account configured on the **[!UICONTROL Mobile (SMS)]** channel with the **[!UICONTROL Bulk delivery]** mode. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Una plantilla de envío que está correctamente vinculada a esta cuenta externa.

**Temas relacionados:**

* [Administración de plantillas](../../start/using/about-templates.md)
* [Configuración SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## SMS delivery template {#sms-delivery-template}

Adobe Campaign ofrece una plantilla de envío para dispositivos móviles. This template must be correctly linked to the external account used for the **[!UICONTROL Mobile (SMS)]** channel. Para acceder y modificarla:

1. Select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** from the advanced menu.
1. Hover over the **[!UICONTROL Send via SMS]** template with the mouse and select the **Duplicate element** option.
1. Seleccione la nueva plantilla.
1. Click the **[!UICONTROL Edit properties]** button.
1. In the **[!UICONTROL Advanced parameters]** section of the template properties, make sure that the template is linked to the external account to be used for delivering SMS.

   ![](assets/sms_template.png)

**Temas relacionados:**

* [Administración de plantillas](../../start/using/about-templates.md)

