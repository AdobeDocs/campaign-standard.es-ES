---
title: Uso de trampas
description: Aprenda a utilizar las trampas en los mensajes.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 2%

---


# Uso de trampas {#using-traps}

Al utilizar las trampas, el mensaje se envía al perfil [de](../../audiences/using/managing-test-profiles.md) prueba tal como se envía al destinatario principal, como medio para identificar si el archivo cliente se está utilizando de forma fraudulenta.

Las trampas se diseñaron originalmente para envíos de correo directo. Permiten:

* Compruebe que su proveedor de correo directo esté enviando realmente la comunicación.
* Reciba el correo al mismo tiempo y en las mismas condiciones que sus clientes.
* Guarde una copia exacta del correo enviado.
* Compruebe que su proveedor de correo directo no utiliza incorrectamente la lista del cliente. De hecho, si se envía cualquier otra comunicación a la dirección del perfil de prueba, es posible que el archivo de cliente se haya utilizado sin su conocimiento. Por este motivo, la dirección del perfil de ensayo solo debe utilizarse para este fin.

Para obtener más información sobre cómo agregar trampas a la audiencia de un correo directo, consulte [Añadir perfiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de prueba y captura.

Para los demás canales de comunicación, puede agregar perfiles de prueba de reventado al destinatario principal para:

* Compruebe que el mensaje se haya enviado correctamente.
* Obtenga y mantenga una copia exacta de su mensaje.
* Rastree cuándo se envió y recibió.

Para utilizar un perfil de prueba como reventado, debe incluirse en la audiencia del mensaje.

>[!NOTE]
>
>A diferencia de los perfiles de prueba utilizados para la representación [de](../../sending/using/sending-proofs.md) pruebas [o](../../sending/using/email-rendering.md)correos electrónicos, el mensaje se envía al mismo tiempo al destinatario principal y a los perfiles de prueba utilizados como trampas.

Al definir la audiencia de un mensaje:

1. En la **[!UICONTROL Test profiles]** ficha, seleccione un perfil de prueba. Asegúrese de que tiene **[!UICONTROL Trap]** el uso previsto.

   ![](assets/trap_select.png)

1. Una vez que el contenido del mensaje esté listo, haga clic en el **[!UICONTROL Prepare]** botón. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Asegúrese de seleccionar un destinatario principal. De lo contrario, no se puede enviar el mensaje.

1. Haga clic en el botón **[!UICONTROL Confirm]**. Consulte [Confirmando el envío ](../../sending/using/confirming-the-send.md) .

   ![](assets/trap_confirm.png)

El mensaje se envía al destinatario principal y al perfil de prueba.

Puede utilizar las trampas al enviar mensajes transaccionales. En este caso, el perfil de prueba recibirá un mensaje por configuración de evento. For more on transactional messaging, see this [section](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Cuando se utiliza un perfil de prueba como reventado, para cualquier campo enriquecido de un mensaje, los datos adicionales correspondientes se seleccionan aleatoriamente de un perfil objetivo real y se asignan al perfil de prueba de reventado. Para obtener más información sobre enriquecimiento, consulte [este ejemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
