---
title: Control del contenido del correo electrónico en Adobe Campaign Standard
description: Aprenda a mejorar la capacidad de envío en Adobe Campaign Standard al editar el contenido del correo electrónico.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 54%

---

# Control del contenido del correo electrónico{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Para asegurarse de que los mensajes de correo electrónico llegan a los destinatarios y mejoran la tasa de envío de correo electrónico, deben respetar una serie de reglas. De lo contrario, el contenido de ciertos mensajes puede detectarse como correo no deseado. Adobe Campaign proporciona varias herramientas para que el contenido cumpla con estas reglas.

Siga los principios que se enumeran a continuación al diseñar el contenido del mensaje:

* [Nombre y dirección](#sender-name) del remitente: la dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado por él. El registro de dominios no debe privatizarse.

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personalización y optimización](#perso-send-time-optimization) del tiempo de envío: la personalización del contenido y la definición de una hora de envío por destinatario aumentan las posibilidades de que se abra el mensaje.
* Imágenes y texto: respete una proporción de texto/imagen adecuada (por ejemplo, 60 % de texto y 40 % de imágenes).
* [Vínculo de baja de suscripción](#opt-out) y página de aterrizaje: el vínculo de baja es esencial. Debe ser visible y válido, y el formulario debe ser funcional.
* Vista previa: utilice las herramientas que ofrece Adobe Campaign para comprobar y optimizar el contenido de su correo electrónico ([Anti-spam analysis](#anti-spam-analysis), [Email rendering](#message-responsiveness)).

Para obtener sugerencias adicionales para optimizar la capacidad de entrega al diseñar contenido, consulte la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=es).

>[!NOTE]
>
>Para obtener más información sobre la edición del contenido del correo electrónico, consulte la [información general del Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) y las [Prácticas recomendadas del diseño de mensaje](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nombre y dirección del remitente {#sender-name}

Algunos ISP verifican la validez de la dirección del remitente (**[!UICONTROL From]**) antes de aceptar mensajes. Una dirección mal formada puede hacer que el servidor receptor la rechace.

![](assets/delivery_content_edition16.png)

Debe asegurarse de proporcionar una dirección correcta en el nivel de instancia o en los escenarios más utilizados. Para ello, póngase en contacto con el administrador.

Para obtener más información, consulte [Definición del remitente de correo electrónico de un correo electrónico](../../designing/using/subject-line.md#email-sender).

## Personalización y optimización del tiempo de envío {#perso-send-time-optimization}

Para mejorar la experiencia de los destinatarios y hacer que abran su correo electrónico, Adobe Campaign le permite personalizar sus mensajes. Para obtener más información, consulte [esta sección](../../designing/using/personalization.md).

Para aumentar la tasa de apertura de los mensajes, también puede definir manualmente una hora de envío por destinatario. Cada perfil recibe el mensaje en la fecha y hora especificadas, siempre que sea posible. Para obtener más información sobre esto, consulte [Optimizing the sending time](../../sending/using/optimizing-the-sending-time.md).

## Formulario y vínculo de no participación {#opt-out}

De forma predeterminada, cuando se analiza el mensaje, una regla de tipología comprueba si se ha incluido un vínculo de exclusión y genera una advertencia si falta. Para obtener más información sobre la administración de vínculos, consulte [esta sección](../../designing/using/links.md).

Debe comprobar que el vínculo de exclusión funciona correctamente antes de cada envío. Por ejemplo, al [enviar la prueba](../../sending/using/sending-proofs.md), asegúrese de que el vínculo sea válido, de que el formulario esté en línea y de que al validarlo se comprueben las casillas **[!UICONTROL No longer contact]**. Debe realizar esta comprobación sistemáticamente porque siempre puede haber errores humanos al introducir el vínculo o al cambiar el formulario. Para obtener más información sobre la administración de la inclusión y la exclusión, consulte [esta sección](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Si se detecta un problema relacionado con la baja después de que se inicie la entrega, aún es posible realizar una baja manualmente (mediante la función de actualización masiva, por ejemplo) para los destinatarios que hacen clic en el vínculo de exclusión incluso si no pudieron confirmar su elección.

Como regla general, no debe intentar interferir en los destinatarios que deseen optar por la exclusión obligándolos a rellenar campos como, por ejemplo, su dirección de correo electrónico o su nombre. La página de aterrizaje de baja de suscripción solo debe tener un botón de validación.

La solicitud de confirmación adicional no es fiable: un usuario puede tener dos direcciones de correo electrónico redirigidas al mismo cuadro (por ejemplo: firstname.lastname@club.com y firstname.lastname@internet-club.com). Si el perfil solo puede recordar la primera dirección y desea cancelar la suscripción a través de un mensaje enviado al otro, el formulario lo rechazará porque el identificador cifrado y la dirección de correo electrónico introducidos no coincidirán.

## Análisis de correo no deseado {#anti-spam-analysis}

El editor de mensajes de Adobe Campaign integra un **análisis de correo no deseado** que le permite puntuar correos electrónicos para determinar si un mensaje corre el riesgo de que las herramientas de filtrado de correo no deseado utilizadas durante la recepción lo consideren como no deseado. Para obtener más información, consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).

En el editor de contenido del mensaje, haga clic en **[!UICONTROL Preview]**. Un mensaje le advierte si la comprobación de correo no deseado ha detectado un alto riesgo para este mensaje. Haga clic en **[!UICONTROL Anti-spam analysis]** para ver los detalles.

![](assets/sending_anti-spam_analysis.png)

## Procesamiento de correo electrónico {#message-responsiveness}

Antes de enviar el mensaje, puede probar la capacidad de respuesta comprobando el aspecto que tendrá el mensaje en diferentes dispositivos. Esto le permite asegurarse de que su mensaje se mostrará de una forma óptima en una gran variedad de clientes, correos web y dispositivos.

![](assets/inbox_rendering_report_3.png)

Para permitirlo, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite previsualizar el mensaje enviado en los diferentes contextos en los que se puede recibir.

Para obtener más información, consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).
