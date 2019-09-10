---
title: Administración de perfiles de prueba y envío de pruebas
seo-title: Administración de perfiles de prueba y envío de pruebas
description: Administración de perfiles de prueba y envío de pruebas
seo-description: Descubra cómo administrar perfiles y pruebas de prueba.
page-status-flag: no activado nunca
uuid: eb 4 d 893 b -3724-4 b 15-9312-1 ec 74784368 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320 ec 5-196 c -4260-8156-98932 da 3 e 4 a 5
context-tags: Seedmember, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 27447db9ee0dd387c39976c7bd4e157a4b7899b8

---


# Administración de perfiles de prueba y envío de pruebas{#managing-test-profiles-and-sending-proofs}

## Acerca de los perfiles de prueba {#about-test-profiles}

Los perfiles de prueba le permiten dirigirse a destinatarios adicionales que no coinciden con los criterios de objetivo definidos. Se agregan a la audiencia de un mensaje para detectar cualquier uso fraudulento de la base de datos de destinatarios o para garantizar que los mensajes de correo electrónico lleguen a las bandejas de entrada.

Puede administrar los perfiles de prueba desde el menú **[!UICONTROL Profiles & audiences > Test profiles]** avanzado.

Un perfil de prueba contiene información de contacto ficticia o información de contacto controlada por el remitente, que luego se puede utilizar en un mensaje en los siguientes contextos:

* Para enviar **pruebas**: La prueba es un mensaje específico que se utiliza para comprobar el mensaje antes de enviar la entrega terminada a los destinatarios. El perfil de prueba de prueba se encarga de comprobar la entrega con respecto a su contenido y formato. Consulte [Envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* Para **procesamiento por correo electrónico**: El perfil de prueba de procesamiento de correo electrónico se utiliza para comprobar la forma en que se muestra un mensaje según la bandeja de entrada del mensaje que la reciba. Por ejemplo, correo web, servicio de mensajes, móvil, etc. Consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).

   El **uso de procesamiento** de correo electrónico es de solo lectura. Los perfiles de prueba con este uso solo están disponibles en Adobe Campaign.

* **Como reventado**: El mensaje se envía al perfil de prueba al igual que se envía al objetivo principal. Consulte [Uso de trampas](../../sending/using/managing-test-profiles-and-sending-proofs.md#using-traps).
* Para **previsualizar** mensajes: se puede seleccionar un perfil de prueba al obtener una vista previa de un mensaje para probar los elementos de personalización. Consulte [Vista previa de mensajes](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Administración de perfiles de prueba {#managing-test-profiles}

### Creación de perfiles de prueba {#creating-test-profiles}

1. Desde el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Perfiles y audiencias &gt; Perfiles de prueba** para acceder a la lista de perfiles de prueba.

   ![](assets/test_profile_creation_1.png)

1. En el **[!UICONTROL Test profiles]** tablero, haga clic **en Crear**.

   ![](assets/test_profile_creation_2.png)

1. Introduzca los datos de este perfil.

   ![](assets/test_profile_creation_3.png)

1. Seleccione el uso que desee para su perfil de prueba.

   ![](assets/test_profile_creation_4.png)

1. Introduzca los canales **[!UICONTROL Email, Telephone, Mobile, Mobile app]** de contacto, así como la dirección de perfil de prueba, si es necesario.

   >[!NOTE]
   >
   >Puede definir un formato de correo electrónico preferido: **[!UICONTROL Text]** o **[!UICONTROL HTML]**.

1. Especifique un tipo de evento y los datos de este evento si desea utilizar este perfil de prueba para probar la personalización de un mensaje transaccional.
1. Haga clic en **[!UICONTROL Create]** para guardar el perfil de prueba.

El perfil de prueba se agregará a la lista de perfiles.

**Tema relacionado:**

[Creación de un vídeo de perfil](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) de prueba

### Edición de perfiles de prueba {#editing-test-profiles}

Para editar un perfil de prueba y consultar los datos vinculados a él, o para modificarlos:

1. Seleccione el perfil de prueba que desee editar haciendo clic en su imagen.
1. Consulte o modifique los campos.

   ![](assets/test_profile_edit.png)

1. Haga clic **[!UICONTROL Save]** en si ha introducido los cambios o en el nombre del perfil de prueba, en **[!UICONTROL Test profiles]** la sección situada en la parte superior de la pantalla, para regresar al tablero de perfiles de prueba.

## Envío de pruebas {#sending-proofs}

Una prueba es un mensaje específico que permite probar un mensaje antes de enviarlo al objetivo principal.

Los destinatarios de la prueba se encargan de aprobar el mensaje (su contenido y formulario). Se definen en los perfiles **de prueba**. Para obtener más información sobre esto, consulte [Administración de perfiles de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

Para enviar una prueba, los perfiles de la prueba deben incluirse en la audiencia del mensaje.

En un mensaje:

1. Haga clic en **[!UICONTROL Send a test]** el botón.

   ![](assets/bat_select.png)

1. Seleccione el tipo de prueba que desee utilizar:

   * **[!UICONTROL Email rendering]**: Seleccione esta opción para comprobar la forma en que se recibe el mensaje según las bandejas de entrada dirigidas. Para obtener más información, consulte Procesamiento [por correo electrónico](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: seleccione esta opción para probar el mensaje antes de enviarlo al objetivo principal. Los destinatarios de la prueba se encargan de aprobar la entrega, comprobando tanto su contenido como su formato.
   * **[!UICONTROL Proof + Email rendering]**: esta opción combina las dos opciones anteriores.
   ![](assets/bat_select1.png)

1. Confirme su elección.

   Las pruebas se envían a los perfiles de prueba.

   ![](assets/bat_select2.png)

1. Puede ver las pruebas mediante la lista **[!UICONTROL Proofs]** desplegable.

   ![](assets/bat_view.png)

1. Seleccione una prueba para acceder a su resumen. Para un correo electrónico, si ha seleccionado **la opción de procesamiento** Correo electrónico como tipo de prueba, el **[!UICONTROL Access email rendering]** icono se muestra a la derecha de la etiqueta de prueba. Consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Según los comentarios de las personas que reciban la prueba, es posible que se le pida que modifique el contenido de la entrega. Una vez realizadas las modificaciones, tendrá que reiniciar la preparación de correo electrónico y volver a enviar una prueba. Se puede acceder a cada nueva prueba mediante **[!UICONTROL Show proofs]** el botón.

Debe enviar tantas pruebas como sea necesario hasta que haya finalizado el contenido de la entrega. Una vez finalizado esto, puede enviar la entrega al destino principal y cerrar el ciclo de aprobación.

**Tema relacionado:**

[Envío de una prueba, preparación y envío de](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) un vídeo de correo electrónico

## Uso de reventados {#using-traps}

Cuando se usan reventados, el mensaje se envía al perfil de prueba al igual que se envía al destino principal, como un medio para identificar si el archivo cliente se está usando de forma fraudulenta.

Las trampas originalmente se diseñaron para envíos directos de correo electrónico. Permiten:
* Verifique que el proveedor de correo directo esté enviando la comunicación.
* Reciba el correo al mismo tiempo y en las mismas condiciones que sus clientes.
* Mantenga una copia exacta del correo enviado.
* Compruebe que su proveedor de correo directo no utiliza la lista de clientes. En realidad, si se envía alguna otra comunicación a la dirección del perfil de prueba, es posible que el archivo de cliente se haya utilizado sin su conocimiento. Por este motivo, la dirección del perfil de prueba debe utilizarse únicamente para este fin.

Para obtener más información sobre cómo agregar a una audiencia de correo directo, consulte [Adición de perfiles de prueba y de captura](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles).

Para los demás canales de comunicación, puede agregar perfiles de prueba de reventado al objetivo principal para:
* Compruebe que el mensaje se envió correctamente.
* Obtenga y mantenga una copia exacta del mensaje.
* Rastrear cuándo se envió y recibió.

Para utilizar un perfil de prueba como reventado, debe incluirse en la audiencia del mensaje.

>[!NOTE]
>
>A diferencia de los perfiles de prueba utilizados para [las pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) o [el procesamiento de correo electrónico](../../sending/using/email-rendering.md), el mensaje se envía al mismo tiempo al destino principal y a los perfiles de prueba utilizados como trampas.

Al definir la audiencia de un mensaje:

1. En la **[!UICONTROL Test profiles]** ficha, seleccione un perfil de prueba. Asegúrese de que tiene **[!UICONTROL Trap]** el uso previsto.

   ![](assets/trap_select.png)

1. Cuando el contenido del mensaje esté listo, haga clic en **[!UICONTROL Prepare]** el botón. Consulte [Preparación del envío](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Asegúrese de seleccionar un objetivo principal. De lo contrario, no se puede enviar el mensaje.

1. Haga clic en **[!UICONTROL Confirm]** el botón. Consulte [Confirmación del envío](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

El mensaje se envía al objetivo principal y al perfil de prueba.

>[!NOTE]
>
>Cuando se utiliza un perfil de prueba como reventado, para cualquier campo enriquecido de un mensaje, los datos adicionales correspondientes se seleccionan aleatoriamente desde un perfil de destino real y se asignan al perfil de prueba de reventado. Para obtener más información sobre el enriquecimiento, consulte [este ejemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
