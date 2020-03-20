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
source-git-commit: a7c2d444b7d971124b676fa2392b51aab40e5629

---


# Uso de trampas {#using-traps}

Al utilizar trampas, el mensaje se envía al perfil [de](../../audiences/using/managing-test-profiles.md) prueba tal como se envía al destino principal, como medio para identificar si el archivo cliente se está utilizando de forma fraudulenta.

Las trampas se diseñaron originalmente para entregas por correo directo. Permiten:

* Compruebe que su proveedor de correo directo esté enviando realmente la comunicación.
* Reciba el correo al mismo tiempo y en las mismas condiciones que sus clientes.
* Guarde una copia exacta del correo enviado.
* Compruebe que su proveedor de correo directo no utiliza incorrectamente la lista de clientes. De hecho, si se envía cualquier otra comunicación a la dirección de su perfil de prueba, es posible que el archivo de cliente se haya utilizado sin su conocimiento. Por este motivo, la dirección del perfil de prueba solo debe utilizarse para este fin.

Para obtener más información sobre la adición de trampas a la audiencia de un correo directo, consulte [Adición de perfiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de prueba y captura.

Para los demás canales de comunicación, puede agregar perfiles de prueba de reventado al destino principal para:

* Compruebe que el mensaje se haya enviado correctamente.
* Obtenga y mantenga una copia exacta de su mensaje.
* Rastree cuándo se envió y recibió.

Para usar un perfil de prueba como reventado, debe incluirse en la audiencia del mensaje.

>[!NOTE]
>
>A diferencia de los perfiles de prueba utilizados para [pruebas](../../sending/using/sending-proofs.md) o procesamiento [por](../../sending/using/email-rendering.md)correo electrónico, el mensaje se envía al mismo tiempo al destino principal y a los perfiles de prueba utilizados como trampas.

Al definir la audiencia de un mensaje:

1. En la **[!UICONTROL Test profiles]** ficha, seleccione un perfil de prueba. Asegúrese de que tiene **[!UICONTROL Trap]** el uso previsto.

   ![](assets/trap_select.png)

1. Una vez que el contenido del mensaje esté listo, haga clic en el **[!UICONTROL Prepare]** botón. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Asegúrese de seleccionar un objetivo principal. De lo contrario, no se puede enviar el mensaje.

1. Haga clic en el botón **[!UICONTROL Confirm]**. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

El mensaje se envía al destino principal y al perfil de prueba.

Puede utilizar trampas al enviar mensajes transaccionales. En este caso, el perfil de prueba recibirá un mensaje por configuración de evento. Para obtener más información sobre la mensajería transaccional, consulte esta [sección](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Cuando se utiliza un perfil de prueba como reventado, para cualquier campo enriquecido de un mensaje, los datos adicionales correspondientes se seleccionan aleatoriamente de un perfil objetivo real y se asignan al perfil de prueba de reventado. Para obtener más información sobre el enriquecimiento, consulte [este ejemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
