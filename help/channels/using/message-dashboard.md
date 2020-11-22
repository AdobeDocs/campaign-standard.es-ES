---
solution: Campaign Standard
product: campaign
title: Panel de mensajes
description: Descubra en qué consiste el panel del mensaje, incluida la barra de acciones y los distintos bloques funcionales.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 6%

---


# Panel de mensajes{#message-dashboard}

El panel de mensajes es un espacio de trabajo compuesto por diferentes iconos - reagrupados en una barra de acciones - y varios bloques funcionales que le permiten establecer los parámetros del mensaje y enviarlo. Estos elementos se presentan a continuación.

![](assets/delivery_dashboard_2.png)

## Barra gris {#gray-bar}

La barra gris reagrupa varios iconos vinculados al mensaje.

* **[!UICONTROL Summary]**:: muestra u oculta la información principal relativa al mensaje.
* **[!UICONTROL Edit properties]**:: permite editar los parámetros [](../../administration/using/configuring-email-channel.md#list-of-email-properties)avanzados del mensaje.
* **[!UICONTROL Reports]**:: le permite acceder a los informes relacionados con el mensaje.

**Temas relacionados:**

* [Configuración de canales](../../administration/using/about-channel-configuration.md)
* [Acceso a informes](../../reporting/using/about-dynamic-reports.md)

## Barra de acciones {#action-bar}

La barra de acciones tiene diferentes iconos que le permiten interactuar con el mensaje.

![](assets/delivery_dashboard_4.png)

Según los parámetros que se hayan configurado y el progreso realizado, es posible que algunos iconos no estén disponibles.

* **[!UICONTROL Show proofs]**:: muestra u oculta la lista de pruebas que se han enviado, si existen. Este botón solo se activa una vez que se han enviado pruebas.

   Para obtener más información sobre pruebas, consulte [Envío de pruebas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**:: permite seleccionar el modo de aprobación para utilizar: **[!UICONTROL Email rendering]** (solo correo electrónico) **[!UICONTROL Proof]** o ambos. Para obtener más información sobre los perfiles de prueba, consulte [Envío de pruebas](../../sending/using/sending-proofs.md). Este botón solo se activa una vez que haya creado perfiles de prueba.

* **[!UICONTROL Prepare send]**:: inicios para preparar el envío. El **[!UICONTROL Deployment]** bloque aparece y muestra el resultado de la preparación. Este botón solo aparece una vez que se ha introducido el destinatario. Puede detener la preparación en cualquier momento utilizando el botón correspondiente. For more on message preparation, refer to [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**:: confirma el envío del mensaje. Las estadísticas de envío aparecen en el **[!UICONTROL Deployment]** bloque. Este botón solo aparece después de que se haya preparado el envío. Puede detener o pausar el envío en cualquier momento mediante los botones **Detener envío** y **[!UICONTROL Pause]** . Para obtener más información sobre cómo confirmar el envío, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

## Bloques {#blocks}

La pantalla principal está formada por diferentes bloques. Haga clic dentro de un bloque para acceder a la pantalla de parámetros correspondiente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:: le permite realizar un seguimiento del progreso de la preparación o el envío de mensajes. Haga clic en el botón que se encuentra en la sección inferior derecha de este bloque para acceder a los registros de envío y análisis. Este bloque solo aparece una vez que se ha preparado el envío. Para obtener más información, consulte. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**:: le permite establecer el destinatario principal del mensaje, así como los perfiles de prueba. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**:: le permite especificar la fecha en la que se enviará el mensaje. Consulte [Programación](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**:: permite definir el contenido del mensaje y su previsualización. See [Key steps to send a message](../../channels/using/key-steps-to-send-a-message.md).

## Advertencias {#warnings}

En algunos casos, puede aparecer una advertencia en un letrero amarillo encima del panel del mensaje.

![](assets/delivery_dashboard_warnings.png)

A continuación se muestra una lista de los mensajes que se pueden mostrar:

* *&quot;La opción de modo de prueba SMTP está habilitada para este correo electrónico: no se enviará ningún mensaje&quot;.*

   Para obtener más información, consulte [esta sección](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;Se ha deshabilitado la cuenta externa de Enrutamiento.&quot;*

   Para obtener más información sobre esto, consulte [Cuentas externas](../../administration/using/external-accounts.md).

* *&quot;No se pueden enviar mensajes porque ningún proceso de envío gestiona la afinidad IP actual.&quot;*

   Si ve este mensaje, hay un problema en el nivel de definición de afinidad IP o en el nivel de proceso de envío. Póngase en contacto con el administrador de Adobe 

* *&quot;Esta es una Plantilla de mensaje transaccional lista para usar. Si desea modificarla, debe duplicado y trabajar en su copia&quot;.*

   Algunas de estas Plantillas de mensaje transaccional integradas son plantillas de página de aterrizaje integradas. Para obtener más información, consulte [esta sección](../../channels/using/landing-page-templates.md).

* *&quot;Este mensaje es una Plantilla de mensaje transaccional técnica. No puede modificarlo ni publicarlo.&quot;*

   Esta advertencia se muestra en Plantillas de mensaje transaccional vacías que no son editables. For more on transactional messages, see [this section](../../channels/using/getting-started-with-transactional-msg.md).
