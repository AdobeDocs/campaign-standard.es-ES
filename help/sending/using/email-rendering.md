---
title: Procesamiento de correo electrónico
seo-title: Procesamiento de correo electrónico
description: Procesamiento de correo electrónico
seo-description: Descubrir la función de procesamiento de correo electrónico.
page-status-flag: nunca activado
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: preparar y probar mensajes
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51d80fc9c683e39b9d08ba7d36b76b71a9dd1e8c

---


# Procesamiento de correo electrónico{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

Para permitir esto, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite obtener una vista previa del mensaje enviado en los diferentes contextos en los que se puede recibir.

The mobile, messaging and webmail clients available for **Email rendering** in Adobe Campaign are listed on the Litmus [website](https://litmus.com/email-testing) (click **View all email clients**).

## Comprobación del informe de procesamiento de correo electrónico {#checking-the-email-rendering-report}

Una vez que haya creado su envío de correo electrónico y definido su contenido, así como la población de destino, siga los pasos a continuación.

1. Haga clic en **Audiencia** para acceder a la **[!UICONTROL Test profiles]** ficha.

   ![](assets/email_rendering_05.png)

1. Utilice el editor de consultas para definir los perfiles de prueba que desea utilizar, incluidos los perfiles de prueba que se utilizan para el procesamiento **por correo** electrónico. Consulte [Acerca de los perfiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)de prueba.

   ![](assets/email_rendering_06.png)

1. Compruebe y confirme la consulta, luego guarde los cambios.
1. Haga clic en el **[!UICONTROL Test]** botón de la barra de acciones.

   ![](assets/email_rendering_07.png)

1. Seleccione la **[!UICONTROL Email rendering]** opción y haga clic en **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >La **[!UICONTROL Proof + Email rendering]** opción le permite enviar una prueba y utilizar simultáneamente la función de procesamiento por correo electrónico. Puede solicitar la aprobación del mensaje por parte de los destinatarios de la prueba y, al mismo tiempo, puede probar la forma en que se recibirá el mensaje según las bandejas de entrada objetivo. En este caso, también debe seleccionar Perfiles de prueba. Consulte [Acerca de los perfiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)de prueba.

   Se envía la entrega de la prueba.

1. Las miniaturas de procesamiento están disponibles unos minutos después de enviar los mensajes. Para acceder a ellos, seleccione **[!UICONTROL Proofs]** en la lista **[!UICONTROL Summary]** desplegable.

   ![](assets/email_rendering_03.png)

1. En la **[!UICONTROL Proofs]** lista, haga clic en el **[!UICONTROL Access email rendering]** icono .

   ![](assets/email_rendering_04.png)

Se muestra el informe de procesamiento de correo electrónico dedicado. Consulte Descripción del informe [de procesamiento por correo electrónico](#email-rendering-report-description).

**Temas relacionados**:

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Administración de perfiles de prueba y envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md)
* [Editor de consultas](../../automating/using/editing-queries.md#about-query-editor)

## Descripción del informe de procesamiento por correo electrónico {#email-rendering-report-description}

Este informe presenta las representaciones de correo electrónico tal como aparecen en el destinatario. Las representaciones de correo electrónico pueden variar en función de cómo el destinatario abre la entrega de correo electrónico: en un navegador, en un dispositivo móvil o mediante una aplicación de correo electrónico.

>[!NOTE]
>
>El número de representaciones disponibles aparece en el contrato de licencia. Cada entrega con procesamiento **por correo** electrónico habilitado disminuye las representaciones disponibles (conocidas como tokens) en uno. Si es cliente de Litmus, puede utilizar su propia cuenta de Litmus para aprovisionar y utilizar el procesamiento por correo electrónico en Adobe Campaign. Para obtener más información, póngase en contacto con el administrador de cuentas de Adobe.

El resumen del informe muestra el número de mensajes recibidos, no deseados (spam), no recibidos o pendientes de recepción.

![](assets/inbox_rendering_report.png)

El informe se divide en tres partes: **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]**, y **[!UICONTROL Webmails]**. Desplácese hacia abajo por el informe para mostrar todas las representaciones agrupadas en estas tres categorías.

![](assets/inbox_rendering_report_3.png)

Para obtener los detalles de cada informe, haga clic en la tarjeta correspondiente. Se muestra la renderización del método de recepción seleccionado.

![](assets/inbox_rendering_report_2.png)

La **[!UICONTROL Technical data]** ficha le permite obtener más información, como las fechas de recepción y captura, y los encabezados completos de los correos electrónicos.
