---
title: Explicación de los fallos de entrega
seo-title: Explicación de los fallos de entrega
description: Explicación de los fallos de entrega
seo-description: Descubra cómo administrar errores de entrega con Campaign.
page-status-flag: no activado nunca
uuid: 2735 aa 05-7 b 6 f -47 c 9-98 c 4-a 15 cc 33 be 39 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: monitoreo de mensajes
discoiquuid: 38452841-4 cd 4-4 f 92-a 5 c 3-1 dfdd 54 ff 6 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f 4 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Understanding delivery failures{#understanding-delivery-failures}

## About delivery failures {#about-delivery-failures}

Cuando una entrega no se puede enviar a un perfil, el servidor remoto envía automáticamente un mensaje de error, que la plataforma de Adobe Campaign recoge y califica para determinar si la dirección de correo electrónico o el número de teléfono deben colocarse en cuarentena. See [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification).

>[!NOTE]
>
>**Los mensajes** de error de correo electrónico (o «devoluciones») se califican mediante el proceso de inmail. **Los mensajes** de error SMS (o "SR" para "Informe de estado") están cualificados mediante el proceso de MTA.

Los mensajes también pueden excluirse durante la preparación de la entrega si se coloca en cuarentena una dirección o si un perfil está bloqueado. Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Temas relacionados:**

* [Información sobre la administración de cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Administración de listas bloqueadas en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifying delivery failures for a message {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

También hay disponible un informe predeterminado específico. Este informe detalla los errores generales y duros que se encontraron durante los envíos, así como el procesamiento automático de devoluciones. For more on this, refer to [this section](../../reporting/using/bounce-summary.md).

## Delivery failure types and reasons {#delivery-failure-types-and-reasons}

Hay tres tipos de errores cuando falla una entrega:

* **Duro**: Un error "duro" indica una dirección no válida. Esto implica un mensaje de error que indica explícitamente que la dirección no es válida, como: " Usuario desconocido ".
* **Suave**: Puede ser un error temporal o uno que no se pueda categorizar, por ejemplo: " Dominio no válido "o" Buzón de mailbox lleno ".
* **Ignorado**: Se trata de un error que se conoce como temporal, como "Fuera de oficina", o bien un error técnico, por ejemplo, si el tipo de remitente es "postmaster".

Los posibles motivos de un fallo de entrega son:

* **[!UICONTROL User unknown]** (Tipo duro): la dirección no existe. No se intentarán realizar más entregas para este perfil.
* **[!UICONTROL Quarantined address]** (Tipo duro): la dirección se colocó en cuarentena.
* **[!UICONTROL Unreachable]** (Tipo suave/duro): se ha producido un error en la cadena de entrega de mensajes (incidente en el rellamado SMTP, dominio no disponible temporalmente, etc.). Según el error devuelto por el proveedor, la dirección se enviará a cuarentena directamente o la entrega se volverá a probar hasta que Campaign reciba un error que justifique el estado de Cuarentena o hasta que el número de errores alcance 5.
* **[!UICONTROL Address empty]** (Tipo duro): la dirección no está definida.
* **[!UICONTROL Mailbox full]** (Tipo suave): El buzón de correo de este usuario está lleno y no puede aceptar más mensajes. Esta dirección se puede eliminar de la lista de cuarentena para realizar otro intento. Se elimina automáticamente al cabo de 30 días.

   Para que la dirección se elimine de forma automática de la lista de direcciones en cuarentena, debe iniciarse el flujo de trabajo técnico **[!UICONTROL Database cleanup]**.

* **[!UICONTROL Refused]** (Tipo suave/duro): La dirección se ha colocado en cuarentena debido a los comentarios de seguridad como un informe no deseado. Según el error devuelto por el proveedor, la dirección se enviará a cuarentena directamente o la entrega se volverá a probar hasta que Campaign reciba un error que justifique el estado de Cuarentena o hasta que el número de errores alcance 5.
* **[!UICONTROL Duplicate]**: la dirección ya se detectó en la segmentación.
* **[!UICONTROL Not defined]** (Tipo suave): la dirección está calificada porque todavía no se han incrementado los errores.

   Este tipo de error se produce cuando el servidor envía un nuevo mensaje de error: Puede ser un error aislado, pero si se vuelve a producir, el contador de errores aumenta, lo que avisará a los equipos técnicos.

* **[!UICONTROL Error ignored]**: la dirección se encuentra en la lista de direcciones permitidas y se le enviará un correo electrónico en cualquier caso.
* **[!UICONTROL Blacklisted address]**: la dirección estaba bloqueada en el momento del envío.
* **[!UICONTROL Account disabled]** (Tipo suave/duro): Cuando el proveedor de acceso a Internet (IAP) detecta un período largo de inactividad, puede cerrar la cuenta del usuario: los envíos a la dirección del usuario serán imposibles. The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. Si el error recibido indica que la cuenta está desactivada permanentemente, se enviará directamente a Cuarentena.
* **[!UICONTROL Not connected]**: el teléfono móvil del perfil se desactiva o no a la red cuando se envía el mensaje.
* **[!UICONTROL Invalid domain]** (Tipo suave): el dominio de la dirección de correo electrónico es incorrecto o ya no existe. Este perfil volverá a ser dirigido hasta que el recuento de errores alcance 5. Después de esto, el registro estará establecido en estado de Cuarentena y no se realizará ningún reintento.
* **[!UICONTROL Text too long]**: el número de caracteres del mensaje SMS excede el límite. For more on this, see [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: El mensaje SMS contiene uno o varios caracteres que la codificación no admite. &amp;For more on this, see [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Retries after a delivery temporary failure {#retries-after-a-delivery-temporary-failure}

If a message fails due to a temporary error of the **Ignored** type, retries will be performed during the delivery duration. For more on the types of errors, see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).

Para modificar la duración de una entrega, vaya a los parámetros avanzados del envío o plantilla de entrega y especifique la duración deseada en el campo correspondiente. The advanced delivery properties are presented in [this section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configuración predeterminada permite cinco reintentos en intervalos de una hora, seguido de un reintento por día durante cuatro días. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Synchronous and asynchronous errors {#synchronous-and-asynchronous-errors}

Una entrega puede fallar inmediatamente (error sincrónico), o posterior, después de enviarse (error asincrónico).

* **Error sincrónico**: El servidor remoto del servidor de entrega de Adobe Campaign devolvía inmediatamente un mensaje de error, el envío no se permite al servidor del perfil.
* **Error asincrónico**: el servidor receptor volvió a enviar un correo de devoluciones o SR. Los errores asincrónicos se pueden producir hasta una semana después de enviar una entrega.

## Bounce mail qualification {#bounce-mail-qualification}

La plataforma Adobe Campaign detecta los mensajes de error de entrega (o «devoluciones») y los reúne el proceso de inmail para enriquecer la lista de reglas de administración de correo electrónico.

Esta lista solo está disponible para los administradores y contiene todas las reglas utilizadas por Adobe Campaign para cumplir los fallos de entrega.

To access it, click the **[!UICONTROL Adobe Campaign]** logo, at the top left, then select **[!UICONTROL Administration > Channels > Email > Email processing rules]**.

For more on this, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

Las devoluciones pueden tener los siguientes estados de cualificación:

* **[!UICONTROL To qualify]**: el correo de devolución debe ser calificado. La cualificación debe realizarla el equipo de Suministro para asegurarse de que las funciones de la plataforma funcionan correctamente. Siempre que no esté cualificado, el correo de salida hacia otro sitio no se utiliza para enriquecer la lista de reglas de procesamiento por correo electrónico.
* **[!UICONTROL Keep]**: El correo de devolución se cualificará y la **actualización para el** flujo de trabajo de entrega se comparará con las reglas de procesamiento de correo electrónico existentes y enriquecerá la lista.
* **[!UICONTROL Ignore]**: El correo de devolución se cualificó pero la **actualización para el** flujo de trabajo de entrega no se usará. Por lo tanto, no se enviará a las instancias de cliente.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)

## Optimizing mail deliverability with double opt-in mechanism {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

El mecanismo de selección doble es una práctica recomendada al enviar correos electrónicos. Protege a la plataforma de direcciones de correo electrónico incorrectas o no válidas, bots de spam y evita posibles quejas no deseadas.

El principio es enviar un mensaje de correo electrónico para confirmar el acuerdo del visitante antes de almacenarlo como'perfiles'en la base de datos de campaña: El visitante completa una página de aterrizaje en línea, luego recibe un correo electrónico y tiene que hacer clic en el vínculo de confirmación para finalizar su suscripción.

For more on this, refer to [this section](../../channels/using/setting-up-a-double-opt-in-process.md).
