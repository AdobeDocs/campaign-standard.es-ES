---
title: Personalización de mensajes SMS
seo-title: Personalización de mensajes SMS
description: Personalización de mensajes SMS
seo-description: Descubrir la especificidad de las opciones de transliteración al personalizar mensajes SMS.
page-status-flag: no activado nunca
uuid: 123 fe 70 c-c 279-40 a 3-88 b 6-6 bfb 2453 ec 83
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: sms-messages
discoiquuid: 7 c 64785 c-e 3 c 2-4 caa-a 547-002990 aae 3 f 9
delivercontext-tags: Deliverycreation, wizard; delivery, smscontent, back; entrega, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personalizing SMS messages{#personalizing-sms-messages}

The principles for personalizing SMS messages are the same as those for [emails](../../designing/using/inserting-a-personalization-field.md). No obstante, debe tener en cuenta las opciones de transliteración, ya que éstas pueden afectar a la codificación y, por lo tanto, al número de mensajes SMS que se envían. For more on this, refer to the [Transliteration and SMS length](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

Aquí tomamos un mensaje SMS de muestra que contiene campos de personalización que, dependiendo de si se ha seleccionado o no la transliteración, no generarán el mismo número de envíos:

**Hola &lt; firstname &gt; &lt; lastname &gt;, los nuevos productos ahora están disponibles. Come and check them out in store!**

* Para un destinatario llamado'John Smith ', ya que no contiene caracteres especiales, Adobe Campaign seleccionará la codificación GSM que autorizará hasta 160 caracteres por mensaje SMS. Por lo tanto, el mensaje se enviará en una sola parte.
* Para un destinatario llamado'Raphaël Forêt ', los caracteres'ë'y'ê'no se pueden codificar en GSM. En función de si la transliteración se ha habilitado o no, Adobe Campaign puede seleccionar entre dos comportamientos:

   * Si se autoriza la transliteración'ë'y'ê'se reemplazará por'e ', lo que significa que se puede utilizar la codificación GSM y así se pueden utilizar hasta 160 caracteres en el SMS. Este mensaje se enviará como un único mensaje SMS, pero se modificará ligeramente.
   * Si la transliteración no está autorizada, Adobe Campaign elegirá enviar el mensaje en formato binario (Unicode): Por lo tanto, todos los caracteres se enviarán como tales. Como los mensajes SMS en Unicode están limitados a 70 caracteres, Adobe Campaign tendrá que enviar el mensaje en dos partes.

>[!NOTE]
>
>El algoritmo que elige automáticamente la mejor codificación se ejecuta de forma independiente para cada mensaje, por caso. De esta forma, solo se enviarán en Unicode los mensajes personalizados que requieren codificación Unicode; todos los demás utilizarán la codificación GSM.

