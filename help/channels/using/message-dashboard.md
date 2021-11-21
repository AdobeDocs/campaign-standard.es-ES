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
ht-degree: 6%

---

# Tablero de mensajes{#message-dashboard}

El panel de mensajes es un espacio de trabajo compuesto por diferentes iconos (reagrupados en una barra de acciones) y varios bloques funcionales que le permiten establecer los parámetros del mensaje y enviarlo. Estos elementos se presentan a continuación.

![](assets/delivery_dashboard_2.png)

## Barra gris {#gray-bar}

La barra gris reagrupa varios iconos vinculados al mensaje.

* **[!UICONTROL Summary]**: muestra u oculta la información principal relativa al mensaje.
* **[!UICONTROL Edit properties]**: permite editar el informe [parámetros avanzados](../../administration/using/configuring-email-channel.md#list-of-email-properties).
* **[!UICONTROL Reports]**: le permite acceder a los informes relacionados con el mensaje.

**Temas relacionados:**

* [Configuración de canales](../../administration/using/about-channel-configuration.md)
* [Acceso a informes](../../reporting/using/about-dynamic-reports.md)

## Barra de acciones {#action-bar}

La barra de acciones tiene diferentes iconos que le permiten interactuar con el mensaje.

![](assets/delivery_dashboard_4.png)

Según los parámetros que se hayan configurado y el progreso realizado, es posible que algunos iconos no estén disponibles.

* **[!UICONTROL Show proofs]**: muestra u oculta la lista de pruebas que se han enviado, si existen. Este botón solo se activa una vez que se han enviado pruebas.

   Para obtener más información sobre las pruebas, consulte [Envío de pruebas](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: permite seleccionar el modo de aprobación para utilizar: **[!UICONTROL Email rendering]** (solo correo electrónico), **[!UICONTROL Proof]** o ambas. Para obtener más información sobre los perfiles de prueba, consulte [Envío de pruebas](../../sending/using/sending-proofs.md). Este botón solo se activa una vez que se hayan creado los perfiles de prueba.

* **[!UICONTROL Prepare send]**: comienza a preparar el envío. La variable **[!UICONTROL Deployment]** aparece y muestra el resultado de la preparación. Este botón solo aparece una vez introducido el objetivo. Puede detener la preparación en cualquier momento utilizando el botón correspondiente. Para obtener más información sobre la preparación de mensajes, consulte [Preparación del envío](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma el envío del mensaje. Las estadísticas de envío aparecen en la sección **[!UICONTROL Deployment]** bloque. Este botón solo aparece después de preparar el envío. Puede detener o pausar el envío en cualquier momento usando la variable **Detener envío** y **[!UICONTROL Pause]** botones. Para obtener más información sobre la confirmación de envíos, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

## Bloques {#blocks}

La pantalla principal está formada por diferentes bloques. Haga clic dentro de un bloque para acceder a la pantalla del parámetro correspondiente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: permite realizar un seguimiento del progreso de la preparación o el envío de mensajes. Haga clic en el botón que se encuentra en la sección inferior derecha de este bloque para acceder a los registros de envío y análisis. Este bloque solo aparece una vez preparado el envío. Para obtener más información, consulte. Consulte [Confirmación del envío](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: permite establecer el destinatario principal del mensaje, así como los perfiles de prueba. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar la fecha en la que se enviará el mensaje. Consulte [Programación](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite definir el contenido del mensaje y previsualizarlo. Consulte [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md).

## Advertencias {#warnings}

En algunos casos, puede aparecer una advertencia en un banner amarillo sobre el panel de mensajes.

![](assets/delivery_dashboard_warnings.png)

A continuación se muestra una lista de los mensajes que se pueden mostrar:

* *&quot;La opción del modo de prueba SMTP está habilitada para este correo electrónico: no se enviará ningún mensaje&quot;.*

   Para obtener más información, consulte [esta sección](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;Se ha deshabilitado el enrutamiento de cuenta externa.&quot;*

   Para obtener más información, consulte [Cuentas externas](../../administration/using/external-accounts.md).

* *&quot;Los mensajes no se pueden enviar porque la afinidad de IP actual no se gestiona mediante ningún proceso de envío.&quot;*

   Si ve este mensaje, hay un problema en el nivel de definición de afinidad de IP o en el nivel de proceso de envío. Póngase en contacto con el administrador de Adobe 

* *&quot;Es una plantilla de mensaje transaccional lista para usar. Si desea modificarla, debe duplicarla y trabajar en su copia&quot;.*

   Algunas de estas plantillas de mensajes transaccionales integradas son plantillas de página de aterrizaje integradas. Para obtener más información, consulte [esta sección](../../channels/using/landing-page-templates.md).

* *&quot;Este mensaje es una plantilla de mensaje transaccional técnica. No puede modificarla ni publicarla&quot;.*

   Esta advertencia se muestra en plantillas de mensaje transaccional vacías que no se pueden editar. Para obtener más información sobre los mensajes transaccionales, consulte [esta sección](../../channels/using/getting-started-with-transactional-msg.md).
