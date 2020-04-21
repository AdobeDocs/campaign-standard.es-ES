---
title: Comprensión de los errores de entrega
description: Obtenga información sobre cómo administrar los errores de envío con la Campaña.
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
source-git-commit: c1287a360cdd1750996b47a27b85a11e90b29df0

---


# Comprensión de los errores de entrega{#understanding-delivery-failures}

## Acerca de los errores de entrega {#about-delivery-failures}

Cuando no se puede enviar un envío a un perfil, el servidor remoto envía automáticamente un mensaje de error, que recoge la plataforma de Adobe Campaign y que está cualificado para determinar si la dirección de correo electrónico o el número de teléfono deben ponerse en cuarentena. Consulte [Cualificación de correo rechazado](#bounce-mail-qualification).

>[!NOTE]
>
>**Los mensajes de error de correo electrónico** (o &quot;devoluciones&quot;) están calificados por el MTA mejorado (devoluciones sincrónicas) o por el proceso de inMail (devoluciones asincrónicas).
>
>**Los mensajes de error de SMS (o “SR”, de “informe de estado”) se clasifican mediante el proceso MTA.**

Los mensajes también se pueden excluir durante la preparación de la entrega si una dirección está en cuarentena o si un perfil está en la lista negra. Los mensajes excluidos se enumeran en la **[!UICONTROL Exclusion logs]** ficha del panel de envío (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Temas relacionados:**

* [Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Administración de listas negras en Campaña](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identificación de errores de envío para un mensaje {#identifying-delivery-failures-for-a-message}

Una vez que se envía un envío, la **[!UICONTROL Sending logs]** ficha (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#sending-logs)) permite realizar vistas del estado de envío de cada perfil y del tipo y motivo de error asociados (consulte los tipos y motivos [de error de](#delivery-failure-types-and-reasons)Envío).

![](assets/sending_logs.png)

También hay disponible un informe personalizado. Este informe detalla los errores generales, tanto los errores duros como los suaves que se han encontrado durante los envíos, así como el procesamiento automático de las devoluciones. Para obtener más información, consulte [esta sección](../../reporting/using/bounce-summary.md).

## Tipos y motivos de errores de entrega {#delivery-failure-types-and-reasons}

Existen tres tipos de errores cuando falla un envío:

* **Hard**: Un error “grave” indica una dirección no válida. Esto implica un mensaje de error que indica explícitamente que la dirección no es válida, como: “Usuario desconocido”.
* **Soft**: Podría tratarse de un error temporal o uno que no se pudiera categorizar, como: “Dominio no válido” o “Buzón lleno”.
* **Ignored**: Se trata de un error temporal, como “Fuera de la oficina”, o un error técnico, por ejemplo, si el tipo de remitente es “Administrador de correo”.

Los posibles motivos de un error de entrega son:

* **[!UICONTROL User unknown]** (Tipo duro): la dirección no existe. No se intenta realizar entregas adicionales para este perfil.
* **[!UICONTROL Quarantined address]** (Tipo duro): la dirección se colocó en cuarentena.
* **[!UICONTROL Unreachable]** (Tipo suave/duro): se ha producido un error en la cadena de envío de mensajes (como un dominio temporalmente inaccesible). Según el error devuelto por el proveedor, la dirección se enviará directamente a la cuarentena o el envío se volverá a intentar hasta que la Campaña reciba un error que justifique el estado de la Cuarentena o hasta que el número de errores alcance el 5.
* **[!UICONTROL Address empty]** (Tipo duro): la dirección no está definida.
* **[!UICONTROL Mailbox full]** (Tipo suave): el buzón de este usuario está lleno y no puede aceptar más mensajes. Esta dirección se puede eliminar de la lista de cuarentena para realizar otro intento. Se elimina automáticamente al cabo de 30 días.

   Para que la dirección se elimine de forma automática de la lista de direcciones en cuarentena, debe iniciarse el flujo de trabajo técnico **[!UICONTROL Database cleanup]**.

* **[!UICONTROL Refused]** (Tipo suave/duro): la dirección se ha colocado en cuarentena debido a los comentarios de seguridad como un informe de spam. Según el error devuelto por el proveedor, la dirección se enviará directamente a la cuarentena o el envío se volverá a intentar hasta que la Campaña reciba un error que justifique el estado de la Cuarentena o hasta que el número de errores alcance el 5.
* **[!UICONTROL Duplicate]**:: la dirección ya se ha detectado en la segmentación.
* **[!UICONTROL Not defined]** (Tipo suave): la dirección está cualificada porque aún no se han incrementado los errores.

   Este tipo de error se produce cuando el servidor envía un nuevo mensaje de error: puede tratarse de un error aislado; sin embargo, si vuelve a producirse, el contador de errores aumenta, lo que advierte a los equipos técnicos.

* **[!UICONTROL Error ignored]**:: la dirección está en la lista blanca y se le enviará un correo electrónico en cualquier caso.
* **[!UICONTROL Blacklisted address]**:: la dirección estaba en la lista negra en el momento del envío.
* **[!UICONTROL Account disabled]** (Tipo suave/duro): cuando el proveedor de acceso a Internet (IAP) detecta un largo período de inactividad, puede cerrar la cuenta del usuario: Los envíos a la dirección del usuario serán imposibles. El tipo Suave o Duro depende del tipo de error recibido: si la cuenta se desactiva temporalmente debido a seis meses de inactividad y aún puede activarse, el estado **[!UICONTROL Erroneous]** se asignará y el envío se volverá a intentar. Si el error recibido indica que la cuenta está desactivada de forma permanente, se enviará directamente a la Cuarentena.
* **[!UICONTROL Not connected]**:: el teléfono móvil del perfil está apagado o no conectado a la red cuando se envía el mensaje.
* **[!UICONTROL Invalid domain]** (Tipo suave): el dominio de la dirección de correo electrónico es incorrecto o ya no existe. Este perfil se vuelve a seleccionar hasta que el recuento de errores llegue a 5. Después de esto, el registro se pone en estado de cuarentena y no se realiza ningún reintento.
* **[!UICONTROL Text too long]**:: el número de caracteres del mensaje SMS supera el límite. Para obtener más información sobre esto, consulte Codificación, longitud y transliteración [SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**:: el mensaje SMS contiene uno o varios caracteres que no son compatibles con la codificación. &amp;Para obtener más información sobre esto, consulte [Tabla de caracteres - Estándar](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard)GSM.

## Reintentos tras un fallo temporal de entrega {#retries-after-a-delivery-temporary-failure}

Si un mensaje falla debido a un error temporal del tipo **Ignorado** , se realizarán reintentos durante el envío. Para obtener más información sobre los tipos de errores, consulte Tipos y motivos [de errores de](#delivery-failure-types-and-reasons)Envío.

El número de reintentos (cuántos reintentos se deben realizar el día siguiente al inicio del envío) y el retraso mínimo entre reintentos ahora son administrados por el MTA mejorado de Adobe Campaign, en función del rendimiento histórico y actual de una IP en un dominio determinado. La configuración de **Reintentos** en la Campaña se ignora.

Para modificar la duración de un envío, vaya a los parámetros avanzados del envío o la Plantilla de envíos y edite el **[!UICONTROL Delivery duration]** campo de la sección Período [de](../../administration/using/configuring-email-channel.md#validity-period-parameters) validez.

>[!IMPORTANT]
>
>**El **[!UICONTROL Delivery duration]**parámetro de los envíos de Campaña ahora solo se utiliza si se establece en 3,5 días o menos.** Si define un valor superior a 3,5 días, no se tendrá en cuenta, ya que ahora está administrado por el MTA mejorado de Adobe Campaign.

Por ejemplo, si desea que los reintentos de un envío se detengan después de un día, puede establecer la duración del envío en **1d** y el MTA mejorado respetará esa configuración eliminando los mensajes de la cola de reintentos pasados un día.

>[!NOTE]
>
>Una vez que un mensaje ha estado en la cola de MTA mejorada durante 3,5 días y no se ha podido entregar, se agotará el tiempo de espera y se actualizará su estado de **[!UICONTROL Sent]** a **[!UICONTROL Failed]** los [registros de envío](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Errores sincrónicos y asíncronos {#synchronous-and-asynchronous-errors}

Un envío puede fallar inmediatamente (error sincrónico), o más tarde, después de haber sido enviado (error asincrónico).

* **Error** sincrónico: el servidor remoto con el que se puso en contacto el servidor de Adobe Campaign envío devolvió inmediatamente un mensaje de error; no se permite que el envío se envíe al servidor del perfil.
* **Error** asincrónico: el servidor receptor envió posteriormente un mensaje de devolución o un SR. Pueden producirse errores asíncronos hasta una semana después de mandar la entrega.

## Clasificación del correo rechazado {#bounce-mail-qualification}

En el caso de los mensajes de error de error de envío sincrónico, el MTA mejorado determina el tipo de devolución y la calificación, y devuelve esa información a la Campaña.

Las devoluciones asincrónicas siguen siendo calificadas por el proceso enMail a través de las **[!UICONTROL Inbound email]** reglas. Para acceder a estas reglas, haga clic en el **[!UICONTROL Adobe Campaign]** logotipo, en la parte superior izquierda, seleccione **[!UICONTROL Administration > Channels > Email > Email processing rules]** y seleccione **[!UICONTROL Bounce mails]**. For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>La certificación de correo de devolución ahora la administra el MTA mejorado de Adobe Campaign. Ya no se utilizan las cualificaciones de devolución de la tabla de Campaña **[!UICONTROL Message qualification]** .

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimización de la capacidad de entrega de correo con el mecanismo de selección de dobles {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

El mecanismo de selección de Doble es una práctica recomendada al enviar correos electrónicos. Protege la plataforma de direcciones de correo electrónico equivocadas o no válidas, spambots y evita posibles quejas de spam.

El principio es enviar un correo electrónico para confirmar el acuerdo del visitante antes de almacenarlo como &quot;perfiles&quot; en la base de datos de Campañas: el visitante rellena una página de aterrizaje en línea, luego recibe un correo electrónico y tiene que hacer clic en el vínculo de confirmación para finalizar su suscripción.

Para obtener más información, consulte [esta sección](../../channels/using/setting-up-a-double-opt-in-process.md).
