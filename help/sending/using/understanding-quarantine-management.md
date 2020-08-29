---
title: Comprensión de la gestión de la cuarentena
description: Aprenda a optimizar la capacidad de entrega con la gestión de la cuarentena.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 121ec37cef6193d3a7085b6d0296b6a2e7cafa06
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 81%

---


# Comprensión de la gestión de la cuarentena{#understanding-quarantine-management}

## Acerca de la cuarentena {#about-quarantines}

Se puede poner en cuarentena una dirección de correo electrónico o un número de teléfono, por ejemplo, cuando el buzón está lleno o si la dirección no existe.

En cualquier caso, el procedimiento de cuarentena satisface las reglas específicas que se describen en esta [sección](#conditions-for-sending-an-address-to-quarantine).

### Optimización de la entrega mediante cuarentenas {#optimizing-your-delivery-through-quarantines}

Los perfiles cuyas direcciones de correo electrónico o número de teléfono están en cuarentena se excluyen automáticamente durante la preparación del mensaje (consulte [Identificación de direcciones en cuarentena para una entrega](#identifying-quarantined-addresses-for-a-delivery)). Esto acelera las entregas, ya que la tasa de error afecta significativamente a la velocidad de entrega.

Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como no deseados si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser agregado a una lista de bloqueados por estos proveedores.

Además, la cuarentena reduce el coste de entrega de los SMS mediante la exclusión en las entregas de los números de teléfono incorrectos.

Para obtener más información sobre las prácticas recomendadas para proteger y optimizar las entregas, consulte [esta página](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Cuarentena vs lista de bloqueados {#quarantine-vs-block-list}

La **cuarentena** solo se aplica a una dirección, no al propio perfil. Esto significa que, si dos perfiles tienen la misma dirección de correo electrónico, ambos se ven afectados si la dirección está en cuarentena.

Del mismo modo, un perfil cuya dirección de correo electrónico se haya puesto en cuarentena puede actualizar su perfil e introducir una nueva dirección, y luego puede volver a recibir entregas.

Being on the **block list**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). Para obtener más información sobre el proceso de lista de bloqueados, consulte [Acerca de la inclusión y la exclusión en la Campaña](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Cuando un usuario responde a un mensaje SMS con una palabra clave como &quot;STOP&quot; para optar por la exclusión de los envíos SMS, su perfil no se agrega a la lista de bloqueados como en el proceso de desactivación de correo electrónico. El número de teléfono del perfil se envía a la cuarentena con el estado **[!UICONTROL On block list]**. Este estado hace referencia únicamente al número de teléfono, el perfil no está en la lista de bloqueados, por lo que el usuario sigue recibiendo mensajes de correo electrónico. Para obtener más información, consulte [esta sección](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identificación de direcciones en cuarentena {#identifying-quarantined-addresses}

Las direcciones en cuarentena pueden enumerarse para una entrega específico o para toda la plataforma.

>[!NOTE]
>
>Si necesita quitar una dirección de la cuarentena, póngase en contacto con su administrador técnico.

### Identificación de direcciones en cuarentena para una entrega {#identifying-quarantined-addresses-for-a-delivery}

Las direcciones en cuarentena para una entrega específica se enumeran durante la fase de preparación de la entrega, en la pestaña **[!UICONTROL Exclusion logs]** del panel de entrega (consulte [esta sección](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Para obtener más información sobre preparación de entregas, consulte [esta sección](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identificación de direcciones en cuarentena para toda la plataforma {#identifying-quarantined-addresses-for-the-entire-platform}

Los administradores pueden enumerar las direcciones en cuarentena para toda la plataforma desde el menú **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.

>[!NOTE]
>
>En este menú se muestran los elementos en cuarentena para los canales de **correo electrónico**, **SMS** y **notificaciones push**.

![](assets/quarantines1.png)

>[!NOTE]
>
>El aumento del número de cuarentenas es un efecto normal, relacionado con el “desgaste” de la base de datos. Por ejemplo, si se considera que la duración de una dirección de correo electrónico es de tres años y la lista de distribución aumenta en un 50 % cada año, el aumento de la cuarentena se puede calcular de la siguiente manera: Fin de año 1: (1*0,33)/(1+0,5) = 22 %. Fin de año 2: ((1,22*0,33)+0,33)/(1,5+0,75) = 32,5 %.

## Condiciones para enviar una dirección a cuarentena {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign administra la cuarentena según el tipo de error de entrega y el motivo asignado durante la calificación de mensajes de error (consulte [Tipos y motivos de error de entrega](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) y [Clasificación del correo rechazado](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Error ignorado**: los errores ignorados no envían una dirección a la cuarentena.
* **Error grave:** la dirección de correo electrónico correspondiente se envía inmediatamente a la cuarentena.
* **Error leve**: los errores leves no envían inmediatamente una dirección a la cuarentena, sino que se suman a un contador de errores. Cuando el contador de errores alcanza el umbral de límite, la dirección se pone en cuarentena. En la configuración predeterminada, el umbral se establece en cinco errores, de los cuales dos errores son importantes si se producen al menos con una diferencia de 24 horas. La dirección se envía a cuarentena en el quinto error. El umbral del contador de errores puede modificarse. Para obtener más información, consulte [esta página](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Cuando una entrega se realiza correctamente tras un reintento, el contador de errores de la dirección se reinicia al estado anterior a la cuarentena. El estado de la dirección cambia a **[!UICONTROL Valid]** y se elimina de la lista de cuarentena después de dos días mediante el flujo de trabajo **[!UICONTROL Database cleanup]**.

Si un usuario clasifica un correo electrónico como correo no deseado (**bucle de comentarios**), el mensaje se redirige automáticamente a un buzón de correo técnico administrado por Campaign. A continuación, la dirección de correo electrónico del usuario se envía automáticamente a la cuarentena con el estado **[!UICONTROL On block list]**. Este estado hace referencia únicamente a la dirección, el perfil no está en la lista de bloqueados, por lo que el usuario sigue recibiendo mensajes SMS y notificaciones push.

>[!NOTE]
La cuarentena en Adobe Campaign distingue entre mayúsculas y minúsculas. Asegúrese de importar las direcciones de correo electrónico en minúsculas para que no se redireccionen más adelante.

En la lista de direcciones en cuarentena (consulte [Identificación de direcciones en cuarentena para toda la plataforma](#identifying-quarantined-addresses-for-the-entire-platform)), el campo **[!UICONTROL Error reason]** indica por qué la dirección seleccionada se colocó en cuarentena.

![](assets/quarantines2.png)

