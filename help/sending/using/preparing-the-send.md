---
title: Preparación del envío
seo-title: Preparación del envío
description: Preparación del envío
seo-description: Descubra cómo definir preparación antes del envío.
page-status-flag: no activado nunca
uuid: 1038 dae 2-164 c -4579-9294-bdf 2 a 4 eb 12 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 003 abc 83-7 f 07-471 f-ab 2 f -1 d 352 d 22 c 26 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Preparing the send{#preparing-the-send}

La preparación se corresponde con el paso de calcular la población objetivo y generar el contenido de los mensajes para cada perfil incluido en el objetivo. Once preparation is finished, the messages are ready to be sent, either immediately or at [the scheduled date and time](../../sending/using/about-scheduling-messages.md).

1. To start preparing the send, click the **Prepare** button located in the action bar.

   ![](assets/preparing_delivery_2.png)

1. **[!UICONTROL Deployment]** El bloque muestra el progreso de preparación y las estadísticas de preparación: número de mensajes dirigidos, número de mensajes que enviar, etc.

   Según el tamaño de la población objetivo, esta operación podría llevar cierto tiempo.

   ![](assets/preparing_delivery.png)

1. Stop the preparation at any time using the **Stop** button, located in the action bar.

   Durante la fase de preparación, no se envían mensajes. Por lo tanto, puede iniciar o detener esto sin riesgo de afectar nada.

   ![](assets/preparing_delivery_6.png)

1. El mensaje se guarda automáticamente durante la preparación para la etapa de envío. If you need to make any changes to your message's schedule after the preparation step, you will need to make sure that you click the **[!UICONTROL Prepare]** button again for those changes to be taken into account. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Para ver los registros de preparación, haga clic en el botón situado en la parte inferior derecha del bloque.

   ![](assets/preparing_delivery_4.png)

1. The **[!UICONTROL Deployment]** window opens, correct any errors then restart the preparation.

   El último mensaje de registro muestra los mensajes de error y el número de errores. Un icono específico muestra el tipo de error encontrado: El icono amarillo indica un error de procesamiento no crítico, el icono rojo indica un error crítico que impide que se inicie la entrega.

   ![](assets/preparing_delivery_3.png)

1. Compruebe las estadísticas de preparación antes de confirmar el envío de los mensajes. If the number of messages to send does not correspond to your configuration, edit the targeted population (see [Selecting an audience in a message](../../audiences/using/selecting-an-audience-in-a-message.md)) and restart the preparation.

Una vez completada la preparación, el mensaje estará listo para enviarse. For more on this, see [Confirming send](../../sending/using/confirming-the-send.md).

**Reglas de tipología**

Adobe Campaign incluye un conjunto de reglas de tipología de diseño que se aplican durante la preparación de los mensajes. Se utilizan para comprobar si un mensaje es válido y cumple los criterios de calidad. See [Typologies](../../administration/using/about-typology-rules.md). Puede definir sus propias reglas de tipología, por ejemplo, puede establecer reglas globales de fatiga entre canales que excluirán automáticamente perfiles sobresoltados de las campañas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Comprobación del mensaje SMS**

Si ha insertado campos de personalización o texto condicional en el contenido del mensaje SMS, estos factores pueden introducir caracteres que la codificación GSM no tenga en cuenta. Cuando se ejecuta la preparación, se supervisa la duración del mensaje y se mostrará un mensaje de advertencia si pasa el límite.

For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) and [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) sections.
