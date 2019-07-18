---
title: Información sobre la administración de cuarentena
seo-title: Información sobre la administración de cuarentena
description: Información sobre la administración de cuarentena
seo-description: Aprenda a optimizar su capacidad de entrega con administración de cuarentena.
page-status-flag: no activado nunca
uuid: 3 c 287865-1 ada -4351-b 205-51807 ff 9 f 7 ed
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: monitoreo de mensajes
discoiquuid: de 3 a 50 b 6-ea 8 f -4521-996 b-c 49 cc 1 f 3 c 946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5b3ea982f08e1198e8c88f78a5faf8a80b935db4

---


# Understanding quarantine management{#understanding-quarantine-management}

## About quarantines {#about-quarantines}

Una dirección de correo electrónico o un número de teléfono pueden colocarse en cuarentena, por ejemplo, cuando el buzón de correo está lleno o si la dirección no existe.

In any case, the quarantine procedure complies with specific rules described in this [section](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).

### Optimizing your delivery through quarantines {#optimizing-your-delivery-through-quarantines}

The profiles whose email addresses or phone number are in quarantine are automatically excluded during message preparation (see [Identifying quarantined addresses for a delivery](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-a-delivery)). Esto acelera las entregas, ya que la tasa de errores tiene un efecto significativo en la velocidad de entrega.

Algunos proveedores de acceso a Internet consideran automáticamente que los correos electrónicos son no deseados si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, el cuarentena permite evitar la lista negra por parte de estos proveedores.

Además, las ubicaciones ayudan a reducir los costes de envío SMS excluyendo los números de teléfono erróneos de los envíos.

For more on best practices to secure and optimize your deliveries, refer to [this page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Quarantine vs blacklisting {#quarantine-vs-blacklisting}

**El cuarentena** solo se aplica a una dirección, no al propio perfil. Significa que, si dos perfiles tienen la misma dirección de correo electrónico, ambos se verán afectados si la dirección está en cuarentena.

Del mismo modo, un perfil cuya dirección de correo electrónico esté en cuarentena podría actualizar su perfil, escribir una nueva dirección y luego ser objetivo de nuevo mediante acciones de envío.

**Por otro** lado, la lista negra dará como resultado que el perfil ya no se dirija a ninguna entrega, por ejemplo tras una cancelación de suscripción (opción de exclusión). For more on the blacklisting process, refer to [Managing blacklisting in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Cuando un usuario responde a un mensaje SMS con una palabra clave como "STOP" para optar por la exclusión de envíos SMS, su perfil no está bloqueado como en el proceso de exclusión de correo electrónico. The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. Este estado solo se refiere al número de teléfono, el perfil no está bloqueado para que el usuario siga recibiendo mensajes de correo electrónico. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifying quarantined addresses {#identifying-quarantined-addresses}

Las direcciones en cuarentena se pueden enumerar para una entrega específica o para toda la plataforma.

>[!NOTE]
>
>Si necesita eliminar una dirección de cuarentena, póngase en contacto con su administrador técnico.

### Identifying quarantined addresses for a delivery {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). For more on delivery preparation, refer to [this section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifying quarantined addresses for the entire platform {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>This menu lists quarantined elements for **email**, **SMS** and **Push notification** channels.

![](assets/quarantines1.png)

>[!NOTE]
>
>El aumento en el número de ubicaciones es un efecto normal, relacionado con el «wear and broken» de la base de datos. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la tabla del destinatario aumenta un 50% cada año, el aumento en las ubicaciones se puede calcular de la siguiente manera: Final del año 1: (1 * 0.33)/(1+0,5) = 22%. Final del año 2: ((1,22 * 0,33) +0.33)/(1,5+0,75) = 32,5%.

## Conditions for sending an address to quarantine {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign manages quarantine according to the delivery failure type and the reason assigned during error messages qualification (see [Delivery failure types and reasons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) and [Bounce mail qualification](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Error al omitir**: los errores ignorados no envían una dirección a la cuarentena.
* **Error grave**: la dirección de correo electrónico correspondiente se envía inmediatamente a la cuarentena.
* **Error suave**: los errores de color no envían inmediatamente una dirección a cuarentena, pero incrementan un contador de errores. Cuando el contador de errores alcanza el umbral límite, la dirección pasa a la cuarentena. En la configuración predeterminada, el umbral se establece en cinco errores, donde dos errores son significativos si se producen al menos 24 horas. La dirección se coloca en cuarentena en el sexto error. Se puede modificar el umbral de contador de errores. For more on this, refer to this [page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Cuando una entrega se realiza correctamente después de un reintento, se reinicializa el contador de errores de la dirección anterior a esa colocación en cuarentena. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

If a user qualifies an email as a spam (**Feedback loop**), the message is automatically redirected towards a technical mailbox managed by Campaign. The user's email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. Este estado hace referencia únicamente a la dirección, el perfil no está bloqueado, de modo que el usuario continúa recibiendo mensajes SMS y notificaciones Push.

>[!NOTE]
El cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar direcciones de correo electrónico en minúsculas para que no se vuelvan a asignar más adelante.

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

