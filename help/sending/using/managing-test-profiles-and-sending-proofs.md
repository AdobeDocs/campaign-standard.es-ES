---
title: Administración de perfiles de prueba y envío de pruebas
description: Aprenda a administrar perfiles y pruebas de prueba.
page-status-flag: nunca activado
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: preparar y probar mensajes
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: startingMember,información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Administración de perfiles de prueba y envío de pruebas{#managing-test-profiles-and-sending-proofs}

## Acerca de los perfiles de prueba {#about-test-profiles}

Los perfiles de prueba le permiten dirigirse a destinatarios adicionales que no coincidan con los criterios de objetivo definidos. Se agregan a la audiencia de un mensaje para detectar cualquier uso fraudulento de la base de datos de destinatarios o para garantizar que los correos electrónicos llegan a las bandejas de entrada.

Puede administrar los perfiles de prueba desde el menú avanzado **[!UICONTROL Profiles & audiences > Test profiles]**.

Un perfil de prueba contiene información ficticia de contacto, o información de contacto controlada por el remitente, que se puede utilizar en un mensaje en los siguientes contextos:

* Para enviar **pruebas**: la prueba es un mensaje específico que se utiliza para comprobar el mensaje antes de enviar la entrega finalizada a los destinatarios. Un perfil de prueba se encarga de comprobar la entrega, en relación con su contenido y formato. Consulte [Envío de pruebas](#sending-proofs).
* Para el procesamiento **de** correo electrónico: el perfil de prueba de procesamiento de correo electrónico se utiliza para comprobar la forma en que se muestra un mensaje según la bandeja de entrada del mensaje que lo recibe. Por ejemplo: webmail, servicio de mensajes, móvil, etc. Consulte Representación [por correo electrónico](../../sending/using/email-rendering.md).

   El uso de procesamiento **de** correo electrónico es de sólo lectura. Los perfiles de prueba con este uso solo están disponibles de forma predeterminada en Adobe Campaign.

* Como **trampa**: el mensaje se envía al perfil de prueba tal como se envía al destino principal. Consulte [Uso de trampas](#using-traps).
* Para **previsualizar** mensajes: se puede seleccionar un perfil de prueba al obtener una vista previa de un mensaje para probar los elementos de personalización. Consulte [Vista previa de mensajes](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Administración de perfiles de prueba {#managing-test-profiles}

### Creación de perfiles de prueba {#creating-test-profiles}

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Perfiles y audiencias &gt; Probar perfiles** para acceder a la lista de perfiles de prueba.

   ![](assets/test_profile_creation_1.png)

1. En el **[!UICONTROL Test profiles]** tablero, haga clic en **Crear**.

   ![](assets/test_profile_creation_2.png)

1. Introduzca los datos de este perfil.

   ![](assets/test_profile_creation_3.png)

1. Seleccione el uso que desee para el perfil de prueba.

   ![](assets/test_profile_creation_4.png)

1. Introduzca los canales de contacto **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, así como la dirección del perfil de prueba si es necesario.

   >[!NOTE]
   >
   >Puede definir un formato de correo electrónico preferido: **[!UICONTROL Text]** o **[!UICONTROL HTML]**.

1. Especifique un tipo de evento y los datos de este evento si desea utilizar este perfil de prueba para probar la personalización de un mensaje transaccional.
1. Haga clic en **[!UICONTROL Create]** para guardar el perfil de prueba.

El perfil de prueba se agregará a continuación a la lista de perfiles.

**Tema relacionado:**

[Creación de un vídeo de perfil](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) de prueba

### Edición de perfiles de prueba {#editing-test-profiles}

Para editar un perfil de prueba y consultar los datos vinculados a él, o para modificarlo:

1. Seleccione el perfil de prueba que desee editar haciendo clic en su imagen.
1. Consulte o modifique los campos.

   ![](assets/test_profile_edit.png)

1. Haga clic **[!UICONTROL Save]** si ha introducido los cambios o seleccione el nombre del perfil de prueba y, a continuación, **[!UICONTROL Test profiles]** en la sección de la parte superior de la pantalla para volver al tablero de perfiles de prueba.

## Envío de pruebas {#sending-proofs}

Una prueba es un mensaje específico que le permite probar un mensaje antes de enviarlo al destino principal.

Los destinatarios de la prueba se encargan de aprobar el mensaje (su contenido y forma). Se definen en los perfiles **de prueba**. Para obtener más información sobre esto, consulte [Administración de perfiles](#managing-test-profiles)de prueba.

Para enviar una prueba, los perfiles de prueba deben incluirse en la audiencia del mensaje.

En un mensaje:

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. Seleccione el tipo de prueba que desee utilizar:

   * **[!UICONTROL Email rendering]**:: seleccione esta opción para probar la forma en que se recibe el mensaje según las bandejas de entrada objetivo. Para obtener más información, consulte Representación [por](../../sending/using/email-rendering.md)correo electrónico.
   * **[!UICONTROL Proof]**:: seleccione esta opción para probar el mensaje antes de enviarlo al destino principal. Los destinatarios de la prueba se encargan de aprobar la entrega comprobando tanto su contenido como su formato.
   * **[!UICONTROL Proof + Email rendering]**:: esta opción combina las dos opciones anteriores.
   ![](assets/bat_select1.png)

1. Confirme su elección.

   Las pruebas se envían a los perfiles de prueba.

   ![](assets/bat_select2.png)

1. Puede ver las pruebas mediante la lista **[!UICONTROL Proofs]** desplegable.

   ![](assets/bat_view.png)

1. Seleccione una prueba para acceder a su resumen. En un mensaje de correo electrónico, si ha seleccionado la opción Representación **por** correo electrónico como tipo de prueba, el **[!UICONTROL Access email rendering]** icono se muestra a la derecha de la etiqueta de prueba. Consulte Representación [por correo electrónico](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Según los comentarios de las personas que reciban la prueba, se le puede solicitar que modifique el contenido de la entrega. Una vez realizadas las modificaciones, debe reiniciar la preparación del correo electrónico y volver a enviar una prueba. Se puede acceder a cada nueva prueba mediante el **[!UICONTROL Show proofs]** botón .

Debe enviar tantas pruebas como sea necesario hasta que haya finalizado el contenido de la entrega. Una vez finalizado, puede enviar el envío al objetivo principal y cerrar el ciclo de aprobación.

**Tema relacionado:**

[Envío de una prueba, preparación y envío de un vídeo por correo electrónico](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html)

## Uso de trampas {#using-traps}

Al utilizar trampas, el mensaje se envía al perfil de prueba tal como se envía al destino principal, como medio para identificar si el archivo cliente se está utilizando de forma fraudulenta.

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
>A diferencia de los perfiles de prueba utilizados para [pruebas](#sending-proofs) o procesamiento [por](../../sending/using/email-rendering.md)correo electrónico, el mensaje se envía al mismo tiempo al destino principal y a los perfiles de prueba utilizados como trampas.

Al definir la audiencia de un mensaje:

1. En la **[!UICONTROL Test profiles]** ficha, seleccione un perfil de prueba. Asegúrese de que tiene **[!UICONTROL Trap]** el uso previsto.

   ![](assets/trap_select.png)

1. Una vez que el contenido del mensaje esté listo, haga clic en el **[!UICONTROL Prepare]** botón. See [Preparing the send](../../sending/using/preparing-the-send.md).
   >[!NOTE]
   >
   >Asegúrese de seleccionar un objetivo principal. De lo contrario, no se puede enviar el mensaje.

1. Click the **[!UICONTROL Confirm]** button. See [Confirming the send](../../sending/using/confirming-the-send.md).

   ![](assets/trap_confirm.png)

El mensaje se envía al destino principal y al perfil de prueba.

>[!NOTE]
>
>Cuando se utiliza un perfil de prueba como reventado, para cualquier campo enriquecido de un mensaje, los datos adicionales correspondientes se seleccionan aleatoriamente de un perfil objetivo real y se asignan al perfil de prueba de reventado. Para obtener más información sobre enriquecimiento, consulte [este ejemplo](../../automating/using/enrichment.md#example--enriching-profile-data-with-data-contained-in-a-file).
