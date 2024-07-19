---
title: Tablero de mensajes
description: Descubra de qué se compone el panel de mensajes, incluida la barra de acciones y los distintos bloques funcionales.
audience: channels
content-type: reference
topic-tags: about-communication-channels
context-tags: delivery,main
feature: Overview
role: User
level: Beginner
exl-id: 886aae39-2029-471c-b4d1-c6ca57d0e568
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 4%

---

# Tablero de mensajes{#message-dashboard}

El panel de mensajes es un espacio de trabajo compuesto por diferentes iconos (reagrupados en una barra de acciones) y varios bloques funcionales que permiten establecer los parámetros del mensaje y enviarlo. Estos elementos se presentan a continuación.

![](assets/delivery_dashboard_2.png)

## Barra gris {#gray-bar}

La barra gris reagrupa varios iconos vinculados al mensaje.

* **[!UICONTROL Summary]**: muestra u oculta la información principal relacionada con el mensaje.
* **[!UICONTROL Edit properties]**: permite editar los [parámetros avanzados](../../administration/using/configuring-email-channel.md#list-of-email-properties) del mensaje.
* **[!UICONTROL Reports]**: le proporciona acceso a los informes relacionados con el mensaje.

**Temas relacionados:**

* [Configuración de canales](../../administration/using/about-channel-configuration.md)
* [Acceso a informes](../../reporting/using/about-dynamic-reports.md)

## Barra de acciones {#action-bar}

La barra de acciones tiene diferentes iconos que le permiten interactuar con el mensaje.

![](assets/delivery_dashboard_4.png)

Según los parámetros configurados y el progreso realizado, es posible que algunos iconos no estén disponibles.

* **[!UICONTROL Show proofs]**: muestra u oculta la lista de pruebas que se han enviado, si existen. Este botón solo se activa una vez que se han enviado las pruebas.

  Para obtener más información sobre las pruebas, consulte [Envío de pruebas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite seleccionar el modo de aprobación que se va a utilizar: **[!UICONTROL Email rendering]** (solo correo electrónico), **[!UICONTROL Proof]** o ambos. Para obtener más información sobre los perfiles de prueba, consulte [Envío de pruebas](../../sending/using/sending-proofs.md). Este botón solo se activa una vez que se han creado perfiles de prueba.

* **[!UICONTROL Prepare send]**: comienza a preparar el envío. Aparecerá el bloque **[!UICONTROL Deployment]** y se mostrará el resultado de la preparación. Este botón solo aparece una vez introducido el objetivo. Puede detener la preparación en cualquier momento utilizando el botón correspondiente. Para obtener más información sobre la preparación del mensaje, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma el envío del mensaje. Las estadísticas de envío aparecen en el bloque **[!UICONTROL Deployment]**. Este botón solo aparece después de preparar el envío. Puede detener o pausar el envío en cualquier momento mediante los botones **Detener envío** y **[!UICONTROL Pause]**. Para obtener más información sobre cómo confirmar el envío, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

## Bloques {#blocks}

La pantalla principal está formada por diferentes bloques. Haga clic dentro de un bloque para acceder a la pantalla de parámetros correspondiente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite realizar un seguimiento del progreso de la preparación o envío del mensaje. Haga clic en el botón situado en la sección inferior derecha de este bloque para acceder a los registros de envío y análisis. Este bloque solo aparece una vez preparado el envío. Para más información. Ver [Confirmación del envío](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite establecer el destinatario principal del mensaje, así como los perfiles de prueba. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar la fecha en que se enviará el mensaje. Consulte [Programación](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite definir el contenido del mensaje y previsualizarlo. Ver [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md).

## Advertencias {#warnings}

En algunos casos, puede aparecer una advertencia en un aviso amarillo en la parte superior del panel de mensajes.

![](assets/delivery_dashboard_warnings.png)

A continuación se muestra una lista de los mensajes que se pueden mostrar:

* *&quot;La opción de modo de prueba SMTP está habilitada para este correo electrónico: no se enviarán mensajes.&quot;*

  Para obtener más información, consulte [esta sección](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;Se deshabilitó la cuenta externa de enrutamiento.&quot;*

  Para obtener más información, consulte [Cuentas externas](../../administration/using/external-accounts.md).

* *&quot;No se pueden enviar mensajes porque ningún proceso de envío administra la afinidad IP actual.&quot;*

  Si ve este mensaje, hay un problema en el nivel de definición de afinidad de IP o en el nivel de proceso de envío. Póngase en contacto con el administrador del Adobe.

* *&quot;Se trata de una plantilla de mensaje transaccional lista para usar. Si desea modificarla, debe duplicarla y trabajar en la copia.&quot;*

  Algunas de estas plantillas de mensaje transaccional listas para usar son plantillas de página de aterrizaje integradas. Para obtener más información, consulte [esta sección](../../channels/using/landing-page-templates.md).

* *&quot;Este mensaje es una plantilla técnica de mensaje transaccional. No puede modificarlo ni publicarlo.&quot;*

  Esta advertencia se muestra en plantillas de mensaje transaccional vacías que no se pueden editar. Para obtener más información sobre los mensajes transaccionales, consulte [esta sección](../../channels/using/getting-started-with-transactional-msg.md).
