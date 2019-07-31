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
source-git-commit: 3cb698bc5025a59771128a8df493e7e126f00cab

---


# Managing test profiles and sending proofs{#managing-test-profiles-and-sending-proofs}

## About test profiles {#about-test-profiles}

Los perfiles de prueba le permiten dirigirse a destinatarios adicionales que no coinciden con los criterios de objetivo definidos. Se agregan a la audiencia de un mensaje para detectar cualquier uso fraudulento de la base de datos de destinatarios o para garantizar que los mensajes de correo electrónico lleguen a las bandejas de entrada.

You can manage your test profiles from the advanced menu **[!UICONTROL Profiles & audiences > Test profiles]**.

Un perfil de prueba contiene información de contacto ficticia o información de contacto controlada por el remitente, que luego se puede utilizar en un mensaje en los siguientes contextos:

* For sending **Proofs**: the Proof is a specific message used to check the message before sending the finalized delivery to recipients. El perfil de prueba de prueba se encarga de comprobar la entrega con respecto a su contenido y formato. See [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).
* For **Email rendering**: the Email rendering test profile is used to check the way in which a message is displayed according to the message inbox that receives it. Por ejemplo, correo web, servicio de mensajes, móvil, etc. See [Email rendering](../../sending/using/email-rendering.md).

   The **Email rendering** use is read-only. Los perfiles de prueba con este uso solo están disponibles en Adobe Campaign.

* **Como reventado**: El mensaje se envía al perfil de prueba al igual que se envía al objetivo principal, como un medio para identificar si el archivo cliente se está usando de forma fraudulenta.
* To **Preview** messages: a test profile can be selected when previewing a message to test the personalization elements.

![](assets/test_profile.png)

## Managing test profiles {#managing-test-profiles}

### Creating test profiles {#creating-test-profiles}

1. From the advanced menu, via the Adobe Campaign logo, select **Profiles &amp; audiences &gt; Test profiles** to access the list of test profiles.

   ![](assets/test_profile_creation_1.png)

1. From the **[!UICONTROL Test profiles]** dashboard, click **Create**.

   ![](assets/test_profile_creation_2.png)

1. Introduzca los datos de este perfil.

   ![](assets/test_profile_creation_3.png)

1. Seleccione el uso que desee para su perfil de prueba.

   ![](assets/test_profile_creation_4.png)

1. Enter the contact channels **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, as well as the test profile address if necessary.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. Especifique un tipo de evento y los datos de este evento si desea utilizar este perfil de prueba para probar la personalización de un mensaje transaccional.
1. Click **[!UICONTROL Create]** to save the test profile.

El perfil de prueba se agregará a la lista de perfiles.

**Tema relacionado:**

[Creación de un vídeo de perfil](https://helpx.adobe.com/campaign/kt/acs/using/acs-test-profiles-feature-video-use.html) de prueba

### Editing test profiles {#editing-test-profiles}

Para editar un perfil de prueba y consultar los datos vinculados a él, o para modificarlos:

1. Seleccione el perfil de prueba que desee editar haciendo clic en su imagen.
1. Consulte o modifique los campos.

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.

## Sending proofs {#sending-proofs}

Una prueba es un mensaje específico que permite probar un mensaje antes de enviarlo al objetivo principal.

Los destinatarios de la prueba se encargan de aprobar el mensaje (su contenido y formulario). They are defined in the **Test profiles**. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

Para enviar una prueba, los perfiles de la prueba deben incluirse en la audiencia del mensaje.

En un mensaje:

1. Click the **[!UICONTROL Send a test]** button.

   ![](assets/bat_select.png)

1. Seleccione el tipo de prueba que desee utilizar:

   * **[!UICONTROL Email rendering]**: Seleccione esta opción para comprobar la forma en que se recibe el mensaje según las bandejas de entrada dirigidas. For more information, refer to [Email rendering](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: seleccione esta opción para probar el mensaje antes de enviarlo al objetivo principal. Los destinatarios de la prueba se encargan de aprobar la entrega, comprobando tanto su contenido como su formato.
   * **[!UICONTROL Proof + Email rendering]**: esta opción combina las dos opciones anteriores.
   ![](assets/bat_select1.png)

1. Confirme su elección.

   Las pruebas se envían a los perfiles de prueba.

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. Seleccione una prueba para acceder a su resumen. For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. See [Email rendering](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Según los comentarios de las personas que reciban la prueba, es posible que se le pida que modifique el contenido de la entrega. Una vez realizadas las modificaciones, tendrá que reiniciar la preparación de correo electrónico y volver a enviar una prueba. Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

Debe enviar tantas pruebas como sea necesario hasta que haya finalizado el contenido de la entrega. Una vez finalizado esto, puede enviar la entrega al destino principal y cerrar el ciclo de aprobación.

**Tema relacionado:**

[Envío de una prueba, preparación y envío de](https://helpx.adobe.com/campaign/kt/acs/using/acs-sending-test-preparing-sending-email-feature-video-use.html) un vídeo de correo electrónico

<!-- ## Sending proofs using additional data {#sending-proofs-using-additional-data}

This section describes how to send proofs using real customer data accessible via a workflow, as opposed to using fake test profile data. This allows you to check that the variables used in the workflow are accurate and to get a view of the message that your recipients will receive.

1. Create a test profile and enable **[!UICONTROL Proof]** and **[!UICONTROL Trap]** as the intended usage. For more on this, see [Managing test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles).

    This test profile becomes part of the targeted audience.

   >[!NOTE]
   >
   >When using a test profile as a trap, for any enriched fields in a message, the corresponding additional data is randomly picked from a real targeted profile and assigned to the trap test profile.

1. Access the marketing activity list and create a test workflow.

   See [Creating a workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Drag and drop a **[!UICONTROL Query]** activity into your workflow and open it.

   The Query activity is presented in the [Query](../../automating/using/query.md) section.

1. Add additional data from a linked table. For more on this, see [Enriching data](../../automating/using/query.md#enriching-data).

1. Drag and drop an **Email delivery** activity into your workflow and open it.

   The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.

1. From the email message dashboard, select the test profile with trap usage that you created.

1. Add to your email content personalization fields using the additional data that you defined in the Query activity.

1. Save the email and start the workflow.

During message preparation, the target count includes the test profile that you selected.
Once the message is sent, additional data is replaced by data from a real profile.

>[!NOTE]
   >
   >Only additional data are replaced. No real profile data such as first name or last name will be used for the test profile. -->
