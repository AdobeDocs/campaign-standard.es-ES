---
title: Personalización de mensajes SMS
seo-title: Personalización de mensajes SMS
description: Personalización de mensajes SMS
seo-description: Descubra la especificidad de las opciones de transliteración al personalizar los mensajes SMS.
page-status-flag: nunca activado
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990ae3f9
delivercontext-tags: deliveryCreation,asistente;delivery,smsContent,back;delivery,smsContent,backCreation
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Personalización de mensajes SMS{#personalizing-sms-messages}

Los principios para personalizar los mensajes SMS son los mismos que para los [correos electrónicos](../../designing/using/personalization.md#inserting-a-personalization-field). No obstante, debe tener en cuenta las opciones de transliteración, ya que éstas pueden afectar a la codificación y, por tanto, al número de mensajes SMS que enviar. Para más información sobre esto, consulte la sección [Transliteración y longitud](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) de SMS.

Aquí tomamos un ejemplo de mensaje SMS que contiene campos de personalización que, dependiendo de si se ha seleccionado o no transcripción, no generará el mismo número de envíos:

**Hey &lt; Nombre &gt; &lt; Apellido &gt;, los nuevos productos ya están disponibles. ¡Ven y revisa en la tienda!**

* Para un destinatario llamado 'John Smith', ya que no contiene caracteres especiales, Adobe Campaign elegirá la codificación GSM, que autorizará hasta 160 caracteres por mensaje SMS. Por lo tanto, el mensaje se enviará en una sola parte.
* Para un destinatario llamado 'Raphaël Forêt', los caracteres 'ë' y 'ê' no se pueden codificar en GSM. Según si la transliteración se ha activado o no, Adobe Campaign puede seleccionar entre dos comportamientos:

   * Si la transliteración está autorizada, 'ë' y 'ê' se reemplazarán por 'e', lo que significa que se puede utilizar la codificación GSM y se pueden usar hasta 160 caracteres en el SMS. Este mensaje se enviará como un solo mensaje SMS, pero se modificará ligeramente.
   * Si la transliteración no está autorizada, Adobe Campaign elegirá enviar el mensaje en formato binario (Unicode): todos los caracteres se enviarán como tales. Como los mensajes SMS en Unicode están limitados a 70 caracteres, Adobe Campaign tendrá que enviar el mensaje en dos partes.

>[!NOTE]
>
>El algoritmo que elige automáticamente la mejor codificación se ejecuta independientemente para cada mensaje, caso por caso. De este modo, solo se enviarán en Unicode los mensajes personalizados que requieran codificación Unicode; todos los demás utilizarán la codificación GSM.

## Enviador SMS {#sms-sender}

Puede personalizar el nombre del remitente del SMS. Para obtener más información sobre esto, consulte la sección de configuración [de](../../administration/using/configuring-sms-channel.md#configuring-sms-properties) SMS.
