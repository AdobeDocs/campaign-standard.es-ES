---
solution: Campaign Standard
product: campaign
title: Control del contenido del correo electrónico en Adobe Campaign Standard
description: Aprenda a mejorar la capacidad de envío en Adobe Campaign Standard al editar el contenido del correo electrónico.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Capacidad de entrega
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 38%

---


# Control del contenido del correo electrónico{#control-email-content}

Para mejorar la tasa de envíos de correo electrónico y asegurarse de que los mensajes de correo electrónico llegan a los destinatarios, el correo electrónico debe respetar un determinado número de reglas.

* **Nombre y dirección** del remitente: La dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado en él. El registro de dominios no debe privatizarse.
* **Asunto**: Evite mayúsculas y minúsculas excesivas y la puntuación, y las palabras que suelen utilizar los remitentes de spam (&quot;Win&quot;, &quot;Free&quot;, etc.).
* **Personalice el correo electrónico**: La personalización del correo electrónico aumenta las posibilidades de que se abra el mensaje.
* **Imágenes y texto**: Respete una proporción de texto/imagen adecuada (por ejemplo, 60% de texto e imágenes 40%).
* **Vínculo de baja y página** de aterrizaje: El enlace de baja es esencial. Debe ser visible y válido, y el formulario debe ser funcional.
* **Utilice las** herramientas que Adobe Campaign proporciona para optimizar el contenido del correo electrónico (análisis de envío, análisis de correo no deseado).

Para obtener más información sobre la edición del contenido del correo electrónico, consulte la [información general del Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) y las [Prácticas recomendadas del diseño de mensaje](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nombre y dirección del remitente {#sender-name}

Algunos ISP verifican la validez de la dirección del remitente (Desde) antes de aceptar mensajes. Una dirección mal formada puede resultar en que el servidor receptor la rechace. Debe asegurarse de proporcionar una dirección correcta en el nivel de instancia o en los escenarios más utilizados. Póngase en contacto con su administrador.

![](assets/delivery_content_edition16.png)

Para obtener más información, consulte [Personalización del nombre del remitente](../../designing/using/personalization.md#personalizing-the-sender).

## Optimización del tiempo de envío {#send-time-optimization}

Para mejorar la tasa de éxito de los mensajes, puede definir manualmente una hora de envío por destinatario. Cada perfil recibe el mensaje en la fecha y hora especificadas, siempre que sea posible.

Para obtener más información sobre esto, consulte [Optimizing the sending time](../../sending/using/optimizing-the-sending-time.md).

## Formulario y vínculo de exclusión {#opt-out}

De forma predeterminada, cuando se analiza el mensaje, una regla de tipología comprueba si se ha incluido un vínculo de exclusión y genera una advertencia si falta.

Debe comprobar que el vínculo de exclusión funciona correctamente antes de cada envío. Por ejemplo, al enviar la prueba, asegúrese de que el vínculo sea válido, de que el formulario esté en línea y de que al validarlo se cambie el valor de las casillas de contacto Ya no se active. Debe realizar esta comprobación sistemáticamente porque siempre es posible el error humano al introducir el vínculo o al cambiar el formulario.

Si se detecta un problema relacionado con la baja después de que se inicie la entrega, aún es posible realizar una baja manualmente (mediante la función de actualización masiva, por ejemplo) para los destinatarios que hacen clic en el vínculo de exclusión incluso si no pudieron confirmar su elección.

Como regla general, no intente interferir con los destinatarios que deseen optar por la exclusión obligándolos a rellenar campos como, por ejemplo, su dirección de correo electrónico o su nombre. La página de aterrizaje de baja de suscripción solo debe tener un botón de validación. La solicitud de confirmación adicional no es fiable: un usuario puede tener dos direcciones de correo electrónico redirigidas al mismo cuadro (por ejemplo: firstname.lastname@club.com y firstname.lastname@internet-club.com). Si el perfil solo puede recordar la primera dirección y desea cancelar la suscripción a través de un mensaje enviado al otro, el formulario lo rechazará porque el identificador cifrado y la dirección de correo electrónico introducidos no coincidirán.

## Análisis de correo no deseado {#anti-spam-analysis}

El editor de mensajes de Adobe Campaign integra un **análisis de correo no deseado** que le permite puntuar correos electrónicos para determinar si un mensaje corre el riesgo de que las herramientas de filtrado de correo no deseado utilizadas durante la recepción lo consideren como no deseado. Para obtener más información, consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).

En el editor de contenido del mensaje, haga clic en **[!UICONTROL Preview]**. Un mensaje le advierte si la comprobación de correo no deseado ha detectado un alto riesgo para este mensaje. Haga clic en **[!UICONTROL Anti-spam analysis]** para ver los detalles.

![](assets/sending_anti-spam_analysis.png)

## Comprobación de la capacidad de respuesta del mensaje {#message-responsiveness}

Antes de enviar el mensaje, puede comprobar cómo se verá el mensaje en distintos dispositivos. Esto sirve para asegurarse de que se muestre de una manera óptima en una variedad de clientes, correos y dispositivos web.

Para permitirlo, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite previsualizar el mensaje enviado en los diferentes contextos en los que se puede recibir.

Para obtener más información, consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
