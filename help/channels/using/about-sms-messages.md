---
title: Acerca de los mensajes SMS
seo-title: Acerca de los mensajes SMS
description: Acerca de los mensajes SMS
seo-description: Descubra las principales características del canal SMS en Adobe Campaign.
page-status-flag: nunca activado
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,asistente;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 96001355220a9dd0cd3851d3f7de9f4dc8ea2782

---


# Acerca de los mensajes SMS{#about-sms-messages}

Adobe Campaign permite enviar mensajes SMS (Servicio de mensajes cortos).

>[!NOTE]
>
>El canal SMS es un complemento. Compruebe el acuerdo de licencia.

En los mensajes SMS, puede crear, modificar y personalizar mensajes solo de formato de texto. También puede obtener una previsualización de los mensajes SMS antes de enviarlos.

La longitud de un mensaje SMS está restringida a 160 caracteres si está en codificación GSM y sólo a 70 caracteres si está en Unicode. Sin embargo, algunos caracteres especiales pueden influir en la longitud del mensaje. For more on this, refer to the [SMS encoding](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

Los mensajes SMS se pueden crear desde el **[!UICONTROL Marketing activities]** menú, desde una campaña o en un flujo de trabajo, consulte [Creación de un mensaje](../../channels/using/creating-an-sms-message.md)SMS.

Para enviar mensajes SMS a un teléfono móvil necesitas:

* Cuenta **[!UICONTROL Routing]** externa configurada en el **[!UICONTROL Mobile (SMS)]** canal con el **[!UICONTROL Bulk delivery]** modo. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Una plantilla de entrega que está correctamente vinculada a esta cuenta externa.

**Temas relacionados:**

* [Administración de plantillas](../../start/using/about-templates.md)
* [Configuración de SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Informe SMS](../../reporting/using/sms-report.md)

## Plantilla de envío SMS {#sms-delivery-template}

Adobe Campaign ofrece una plantilla de entrega para dispositivos móviles. Esta plantilla debe estar correctamente vinculada a la cuenta externa utilizada para el **[!UICONTROL Mobile (SMS)]** canal. Para acceder y modificarlo:

1. Seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery templates]** en el menú avanzado.
1. Pase el ratón sobre la **[!UICONTROL Send via SMS]** plantilla y seleccione la opción **Duplicar elemento** .
1. Seleccione la nueva plantilla.
1. Click the **[!UICONTROL Edit properties]** button.
1. En la **[!UICONTROL Advanced parameters]** sección de las propiedades de la plantilla, asegúrese de que la plantilla está vinculada a la cuenta externa que se va a utilizar para enviar SMS.

   ![](assets/sms_template.png)

**Temas relacionados:**

* [Administración de plantillas](../../start/using/about-templates.md)

