---
title: Comprensión de los errores de envío
description: Obtenga información sobre cómo administrar los errores de entrega con Campaign.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# Comprensión de los errores de envío{#understanding-delivery-failures}

## Acerca de los errores de envío {#about-delivery-failures}

Cuando no se puede enviar una entrega a un perfil, el servidor remoto envía automáticamente un mensaje de error, que recoge la plataforma de Adobe Campaign y que está cualificado para determinar si la dirección de correo electrónico o el número de teléfono se deben poner en cuarentena. Consulte [Rebotar cualificación](#bounce-mail-qualification)de correo.

>[!NOTE]
>
>**Los mensajes de error de correo electrónico (o “rechazos”) se clasifican mediante el proceso de inMail.** **Los mensajes de error de SMS (o “SR”, de “informe de estado”) se clasifican mediante el proceso MTA.**

Los mensajes también se pueden excluir durante la preparación del envío si una dirección está en cuarentena o si un perfil está en la lista negra. Los mensajes excluidos se enumeran en la **[!UICONTROL Exclusion logs]** ficha del tablero de envío (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Temas relacionados:**

* [Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Administración de la lista negra en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identificación de errores de entrega para un mensaje {#identifying-delivery-failures-for-a-message}

Una vez enviado el envío, la **[!UICONTROL Sending logs]** ficha (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#sending-logs)) le permite ver el estado de entrega de cada perfil y el tipo y motivo de error asociado (consulte Tipos y motivos [de error de](#delivery-failure-types-and-reasons)entrega).

![](assets/sending_logs.png)

También hay disponible un informe personalizado. Este informe detalla los errores generales de hardware y software encontrados durante las entregas, así como el procesamiento automático de las devoluciones. Para obtener más información, consulte [esta sección](../../reporting/using/bounce-summary.md).

## Tipos y motivos de errores de envío {#delivery-failure-types-and-reasons}

Existen tres tipos de errores cuando falla una entrega:

* **Duro**: Un error &quot;duro&quot; indica una dirección no válida. Esto implica un mensaje de error que indica explícitamente que la dirección no es válida, como: &quot;Usuario desconocido&quot;.
* **Suave**: Podría tratarse de un error temporal o uno que no se pudiera categorizar, como: &quot;Dominio no válido&quot; o &quot;Buzón lleno&quot;.
* **Ignorado**: Se trata de un error que se sabe que es temporal, como &quot;Fuera de la oficina&quot;, o un error técnico, por ejemplo, si el tipo de remitente es &quot;maestro de correo&quot;.

Los posibles motivos de un error de envío son:

* **[!UICONTROL User unknown]** (Tipo duro): la dirección no existe. No se intenta realizar envíos adicionales para este perfil.
* **[!UICONTROL Quarantined address]** (Tipo duro): la dirección se puso en cuarentena.
* **[!UICONTROL Unreachable]** (Tipo suave/duro): se ha producido un error en la cadena de entrega de mensajes (por ejemplo, no se puede acceder temporalmente al dominio). Según el error devuelto por el proveedor, la dirección se enviará directamente a cuarentena o la entrega se volverá a intentar hasta que Campaign reciba un error que justifique el estado de cuarentena o hasta que el número de errores alcance el 5.
* **[!UICONTROL Address empty]** (Tipo duro): la dirección no está definida.
* **[!UICONTROL Mailbox full]** (Tipo suave): el buzón de este usuario está lleno y no puede aceptar más mensajes. Esta dirección se puede eliminar de la lista de cuarentena para realizar otro intento. Se elimina automáticamente al cabo de 30 días.

   Para que la dirección se elimine de forma automática de la lista de direcciones en cuarentena, debe iniciarse el flujo de trabajo técnico **[!UICONTROL Database cleanup]**.

* **[!UICONTROL Refused]** (Tipo suave/duro): la dirección se ha colocado en cuarentena debido a los comentarios de seguridad como un informe de spam. Según el error devuelto por el proveedor, la dirección se enviará directamente a cuarentena o la entrega se volverá a intentar hasta que Campaign reciba un error que justifique el estado de cuarentena o hasta que el número de errores alcance el 5.
* **[!UICONTROL Duplicate]**:: la dirección ya se ha detectado en la segmentación.
* **[!UICONTROL Not defined]** (Tipo suave): la dirección está cualificada porque aún no se han incrementado los errores.

   Este tipo de error se produce cuando el servidor envía un nuevo mensaje de error: puede tratarse de un error aislado; sin embargo, si vuelve a producirse, el contador de errores aumenta, lo que advierte a los equipos técnicos.

* **[!UICONTROL Error ignored]**:: la dirección está en la lista blanca y se le enviará un correo electrónico en cualquier caso.
* **[!UICONTROL Blacklisted address]**:: la dirección estaba bloqueada en el momento del envío.
* **[!UICONTROL Account disabled]** (Tipo suave/duro): cuando el proveedor de acceso a Internet (IAP) detecta un largo período de inactividad, puede cerrar la cuenta del usuario: las entregas a la dirección del usuario serán imposibles. El tipo Suave o Duro depende del tipo de error recibido: si la cuenta se desactiva temporalmente debido a seis meses de inactividad y aún se puede activar, se **[!UICONTROL Erroneous]** asignará el estado y se volverá a intentar la entrega. Si el error recibido indica que la cuenta está desactivada de forma permanente, se enviará directamente a cuarentena.
* **[!UICONTROL Not connected]**:: el teléfono móvil del perfil está apagado o no conectado a la red cuando se envía el mensaje.
* **[!UICONTROL Invalid domain]** (Tipo suave): el dominio de la dirección de correo electrónico es incorrecto o ya no existe. Este perfil se vuelve a seleccionar hasta que el recuento de errores llegue a 5. Después de esto, el registro se pone en estado de cuarentena y no se realiza ningún reintento.
* **[!UICONTROL Text too long]**:: el número de caracteres del mensaje SMS supera el límite. Para obtener más información sobre esto, consulte Codificación, longitud y transliteración [SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**:: el mensaje SMS contiene uno o varios caracteres que no son compatibles con la codificación. &amp;Para obtener más información sobre esto, consulte [Tabla de caracteres - Estándar](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)GSM.

## Reintentos tras un fallo temporal de envío {#retries-after-a-delivery-temporary-failure}

Si un mensaje falla debido a un error temporal del tipo **Ignorado** , los reintentos se realizarán durante la duración de la entrega. Para obtener más información sobre los tipos de errores, consulte Tipos y motivos [de error de](#delivery-failure-types-and-reasons)entrega.

Para modificar la duración de un envío, vaya a los parámetros avanzados del envío o de la plantilla de envío y especifique la duración deseada en el campo correspondiente. Las propiedades de envío avanzadas se presentan en [esta sección](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configuración predeterminada permite cinco intentos en intervalos de una hora, seguidos de un reintento diario durante cuatro días. El número de reintentos se puede cambiar a nivel global (póngase en contacto con el administrador técnico de Adobe) o para cada envío o plantilla de envío (consulte [esta sección](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Errores sincrónicos y asíncronos {#synchronous-and-asynchronous-errors}

Una entrega puede fallar inmediatamente (error sincrónico), o más tarde, después de haber sido enviada (error asincrónico).

* **Error** sincrónico: el servidor remoto con el que se puso en contacto el servidor de entrega de Adobe Campaign devolvió inmediatamente un mensaje de error; no se permite que la entrega se envíe al servidor del perfil.
* **Error** asincrónico: el servidor receptor envió posteriormente un mensaje de devolución o un SR. Pueden producirse errores asíncronos hasta una semana después de mandar el envío.

## Clasificación del correo rechazado {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>Una vez actualizado a la MTA mejorada, ya no se utilizan las cualificaciones de devolución de la tabla Campaña **[!UICONTROL Message qualification]** .

Para los mensajes de error de error de entrega sincrónica, el MTA mejorado determina el tipo de devolución y la calificación, y envía esa información a Campaign. Para obtener más información sobre el MTA mejorado de Adobe Campaign, consulte este [documento](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Las devoluciones asincrónicas siguen siendo calificadas por el proceso enMail a través de las **[!UICONTROL Inbound email]** reglas. Para acceder a estas reglas, haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la parte superior izquierda, seleccione **[!UICONTROL Administration > Channels > Email > Email processing rules]** y seleccione **[!UICONTROL Bounce mails]**. For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimización de la capacidad de entrega de correo con el mecanismo de doble inclusión {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

El mecanismo de doble inclusión es una práctica recomendada al enviar correos electrónicos. Protege la plataforma de direcciones de correo electrónico equivocadas o no válidas, spambots y evita posibles quejas de spam.

El principio es enviar un correo electrónico para confirmar el acuerdo del visitante antes de almacenarlo como &quot;perfiles&quot; en la base de datos de Campaign: el visitante rellena una página de aterrizaje en línea, luego recibe un correo electrónico y tiene que hacer clic en el vínculo de confirmación para finalizar su suscripción.

Para obtener más información, consulte [esta sección](../../channels/using/setting-up-a-double-opt-in-process.md).
