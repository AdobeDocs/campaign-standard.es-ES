---
solution: Campaign Standard
product: campaign
title: Personalización de mensajes SMS
description: Descubra la especificidad de las opciones de transliteración al personalizar los mensajes SMS.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: 6c01662e-1e19-4cec-aa21-6e84b9b7a677
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 100%

---

# Personalización de mensajes SMS{#personalizing-sms-messages}

Los principios para personalizar los mensajes SMS son los mismos que para los [correos electrónicos](../../designing/using/personalization.md#inserting-a-personalization-field). No obstante, debe tener en cuenta las opciones de transliteración, ya que estas pueden afectar a la codificación y, por tanto, al número de mensajes SMS que enviar. Para obtener más información, consulte la sección [Transliteración y longitud de un SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

Aquí tomamos un ejemplo de mensaje SMS que contiene campos de personalización que, dependiendo de si se ha seleccionado o no transliteración, no generan el mismo número de envíos:

**Oye, &lt; Nombre > &lt; Apellido >. Los nuevos productos ya están disponibles. ¡Echa un vistazo a la tienda!**

* Para un destinatario llamado “Jose García”, ya que no contiene caracteres especiales, Adobe Campaign elige la codificación GSM, que autoriza hasta 160 caracteres por mensaje SMS. Por lo tanto, el mensaje se envía de una.
* Para un destinatario llamado “Raphaël Forêt”, los caracteres “ë” y “ê” no se pueden codificar en GSM. Según si la transliteración se ha activado o no, Adobe Campaign puede seleccionar entre dos comportamientos:

   * Si se autoriza la transliteración, “ë” y “ê” se cambian por “e”, lo que significa que se puede utilizar la codificación GSM y se pueden usar hasta 160 caracteres en el SMS. Este mensaje se envía como un solo mensaje SMS, pero se modifica ligeramente.
   * Si no se autoriza la transliteración, Adobe Campaign elige enviar el mensaje en formato binario (Unicode): todos los caracteres se envían tal como son. Como los mensajes SMS en Unicode están limitados a 70 caracteres, Adobe Campaign tiene que enviar el mensaje en dos partes.

>[!NOTE]
>
>El algoritmo que elige automáticamente la mejor codificación se ejecuta de forma independiente para cada mensaje, caso por caso. De este modo, solo se envían en Unicode los mensajes personalizados que requieran codificación Unicode; todos los demás utilizan la codificación GSM.

## Remitente del SMS {#sms-sender}

>[!IMPORTANT]
>
>Verifique la legislación de su país con respecto a la modificación de la dirección del remitente. También debe consultar a su proveedor de servicio de SMS para ver si ofrece esta funcionalidad.

La opción **[!UICONTROL From]** le permite personalizar el nombre del remitente del mensaje SMS con una cadena de caracteres. Este es el nombre que aparecerá como el nombre del remitente del mensaje SMS en el teléfono móvil del destinatario.

Si este campo está vacío, será el número de origen proporcionado en la cuenta externa que se utilizará. Si no se proporciona ningún número de origen, será el código corto que se utilizará. La cuenta externa específica del envío SMS aparece en la sección [Definición de un enrutamiento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

![](assets/sms_creation_8.png)



