---
title: Compresión de la gestión de la cuarentena
seo-title: Compresión de la gestión de la cuarentena
description: Compresión de la gestión de la cuarentena
seo-description: Aprenda a optimizar la capacidad de entrega con la administración de cuarentena.
page-status-flag: nunca activado
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: monitoreo-mensajes
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Compresión de la gestión de la cuarentena{#understanding-quarantine-management}

## Acerca de la cuarentena {#about-quarantines}

Se puede poner en cuarentena una dirección de correo electrónico o un número de teléfono, por ejemplo, cuando el buzón está lleno o si la dirección no existe.

In any case, the quarantine procedure complies with specific rules described in this [section](#conditions-for-sending-an-address-to-quarantine).

### Optimización del envío mediante cuarentenas {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](#identifying-quarantined-addresses-for-a-delivery)). Esto acelera los envíos, ya que la tasa de error afecta significativamente a la velocidad de envío.

Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como no deseados si la tasa de direcciones no válidas es demasiado alta. En consecuencia, la cuarentena le permite evitar que estos proveedores lo incluyan en sus listas negras.

Además, la cuarentena reduce el coste de envío de los SMS mediante la exclusión en los envíos de los números de teléfono incorrectos.

Para obtener más información sobre las prácticas recomendadas para proteger y optimizar los envíos, consulte [esta página](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Cuarentena o lista negra {#quarantine-vs-blacklisting}

La **cuarentena** solo se aplica a una dirección, no al propio perfil. Esto significa que, si dos perfiles tienen la misma dirección de correo electrónico, ambos se ven afectados si la dirección está en cuarentena.

Del mismo modo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva dirección, y luego puede volver a recibir envíos.

Por otro lado, las **listas negras** tienen como resultado que el perfil ya no se tiene en cuenta para los envíos, por ejemplo, tras una baja (exclusión). Para obtener más información sobre el proceso de la lista negra, consulte [Administración de la lista negra en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Cuando un usuario responde a un mensaje SMS con una palabra clave como “STOP” para impedir la exclusión de envíos SMS, su perfil no se incluye en la lista negra como en el proceso de exclusión de correo electrónico. El número de teléfono del perfil se envía a la cuarentena con el **[!UICONTROL Blacklisted]** estado. Este estado hace referencia únicamente al número de teléfono, el perfil no está bloqueado para que el usuario siga recibiendo mensajes de correo electrónico. Para obtener más información, consulte [esta sección](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificación de direcciones en cuarentena {#identifying-quarantined-addresses}

Las direcciones en cuarentena pueden enumerarse para un envío específico o para toda la plataforma.

>[!NOTE]
>
>Si necesita quitar una dirección de la cuarentena, póngase en contacto con el administrador técnico.

### Identificación de direcciones en cuarentena para un envío {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificación de direcciones en cuarentena para toda la plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Los administradores pueden enumerar las direcciones en cuarentena de toda la plataforma desde el **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menú.

>[!NOTE]
>
>En este menú se muestran los elementos en cuarentena para los canales de **correo electrónico**, **SMS** y **notificaciones push**.

![](assets/quarantines1.png)

>[!NOTE]
>
>El aumento del número de cuarentenas es un efecto normal, relacionado con el "desgaste" de la base de datos. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la tabla del destinatario aumenta un 50 % cada año, el aumento de cuarentena se puede calcular de la siguiente manera: Fin de año 1: (1*0.33)/(1+0.5)=22%. Fin de año 2: ((1.22*0.33)+0.33)/(1.5+0.75)=32,5%.

## Condiciones para enviar una dirección a cuarentena {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign administra la cuarentena según el tipo de error de entrega y el motivo asignado durante la calificación de mensajes de error (consulte Tipos y motivos [de error de](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) entrega y [Calificación](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)de devolución de correo).

* **Error ignorado**: los errores ignorados no envían una dirección a la cuarentena.
* **Error grave:** la dirección de correo electrónico correspondiente se envía inmediatamente a la cuarentena.
* **Error leve**: los errores leves no envían inmediatamente una dirección a la cuarentena, sino que se suman a un contador de errores. Cuando el contador de errores alcanza el umbral de límite, la dirección se pone en cuarentena. En la configuración predeterminada, el umbral se establece en cinco errores, de los cuales dos errores son importantes si se producen al menos con una diferencia de 24 horas. La dirección se envía a cuarentena en el sexto error. El umbral del contador de errores puede modificarse. Para obtener más información, consulte [esta página](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Cuando un envío se realiza correctamente tras un reintento, el contador de errores de la dirección se reinicia al estado anterior a la cuarentena. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. La dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el **[!UICONTROL Blacklisted]** estado. Este estado hace referencia únicamente a la dirección, el perfil no está bloqueado, por lo que el usuario sigue recibiendo mensajes SMS y notificaciones push.

>[!NOTE]
La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

En la lista de direcciones en cuarentena (consulte [Identificación de direcciones en cuarentena para toda la plataforma](#identifying-quarantined-addresses-for-the-entire-platform)), el **[!UICONTROL Error reason]** campo indica por qué la dirección seleccionada se colocó en cuarentena.

![](assets/quarantines2.png)

