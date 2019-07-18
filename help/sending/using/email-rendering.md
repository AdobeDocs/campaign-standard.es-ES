---
title: Procesamiento por correo electrónico
seo-title: Procesamiento por correo electrónico
description: Procesamiento por correo electrónico
seo-description: Descubrir la función de procesamiento de correo electrónico.
page-status-flag: no activado nunca
uuid: c 423 e 237-ad 39-4797-ac 3 a -4320894 a 8 f 99
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: enviar
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2 b 5 b 13 c 8-2 e 51-4985-a 161-c 1 d 7 f 0 fc 32 b 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Email rendering{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

Para ello, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto permite obtener una vista previa del mensaje enviado en los distintos contextos en los que se pueda recibir.

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## Checking the Email rendering report {#checking-the-email-rendering-report}

Una vez que haya creado la entrega de correo electrónico y haya definido su contenido como así también la población objetivo, siga los pasos a continuación.

1. Click **Audience** to access the **[!UICONTROL Test profiles]** tab.

   ![](assets/email_rendering_05.png)

1. Use the query editor to define the test profiles that you want to use, including the test profiles that are for **Email rendering** use. See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   ![](assets/email_rendering_06.png)

1. Compruebe y confirme la consulta y, a continuación, guarde los cambios.
1. Click the **[!UICONTROL Test]** button in the action bar.

   ![](assets/email_rendering_07.png)

1. Select the **[!UICONTROL Email rendering]** option then click **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Proof + Email rendering]** option enables you to send a proof and use the email rendering feature simultaneously. Los destinatarios de pruebas pueden aprobar su mensaje y, al mismo tiempo, probar la forma en que se recibirá el mensaje según las bandejas de entrada dirigidas. En este caso, también debe seleccionar Perfiles de prueba de prueba. See [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

   Se envía la entrega de la prueba.

1. Las miniaturas de procesamiento están disponibles unos minutos después de enviar los mensajes. To access them, select **[!UICONTROL Proofs]** in the **[!UICONTROL Summary]** drop-down list.

   ![](assets/email_rendering_03.png)

1. From the **[!UICONTROL Proofs]** list, click the **[!UICONTROL Access email rendering]** icon.

   ![](assets/email_rendering_04.png)

Se muestra el informe de procesamiento de correo electrónico dedicado. See [Email rendering report description](../../sending/using/email-rendering.md#email-rendering-report-description).

**Temas relacionados**:

* [Creación de un mensaje de correo electrónico](../../channels/using/creating-an-email.md)
* [Administración de perfiles de prueba y envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Editor de consultas](../../automating/using/editing-queries.md#about-query-editor)

## Email rendering report description {#email-rendering-report-description}

Este informe presenta los procesamientos de correo electrónico tal como se muestran al destinatario. Las representaciones de correo electrónico pueden diferir según cómo abre el destinatario la entrega de correo electrónico: en un navegador, en un dispositivo móvil o mediante una aplicación de correo electrónico.

>[!NOTE]
>
>El número de representaciones disponibles aparece en su contrato de licencia. Each delivery with **Email rendering** enabled decreases your available renderings (known as tokens) by one. Si es cliente de Litmus, puede utilizar su cuenta de Litmus para suministrar y utilizar el procesamiento por correo electrónico en Adobe Campaign. Para obtener más información, póngase en contacto con su ejecutivo de cuentas de Adobe.

El resumen del informe muestra la cantidad de mensajes recibidos, no deseado (correo no deseado), no recibido o recepción pendiente.

![](assets/inbox_rendering_report.png)

The report is divided into three parts: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, and **[!UICONTROL Webmails]**. Desplácese hacia abajo por el informe para mostrar todas las representaciones agrupadas en estas tres categorías.

![](assets/inbox_rendering_report_3.png)

Para obtener los detalles de cada informe, haga clic en la tarjeta correspondiente. La representación se muestra para el método de recepción seleccionado.

![](assets/inbox_rendering_report_2.png)

The **[!UICONTROL Technical data]** tab allows you to get more information, such as the receiving and capture dates, and the complete headers of emails.
