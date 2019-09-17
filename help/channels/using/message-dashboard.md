---
title: Tablero de mensajes
seo-title: Tablero de mensajes
description: Tablero de mensajes
seo-description: Descubra en qué consiste el tablero de mensajes, incluida la barra de acciones y los distintos bloques funcionales.
page-status-flag: nunca activado
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: about-Communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: entrega,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aa52fcca887c9423476a1bc0160d340f255b9ac8

---


# Tablero de mensajes{#message-dashboard}

El tablero de mensajes es un espacio de trabajo compuesto por diferentes iconos - reagrupados en una barra de acciones - y varios bloques funcionales que le permiten establecer los parámetros del mensaje y enviarlo. Estos elementos se presentan a continuación.

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

Según los parámetros configurados y el progreso realizado, es posible que algunos iconos no estén disponibles.

* **[!UICONTROL Show proofs]**:: muestra u oculta la lista de pruebas que se han enviado, si existen. Este botón solo se activa una vez que se han enviado pruebas.

   Para obtener más información sobre las pruebas, consulte [Administración de perfiles de prueba y envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**:: permite seleccionar el modo de aprobación para utilizar: **[!UICONTROL Email rendering]**, **[!UICONTROL Proof]** o ambos, para un correo electrónico. Para obtener más información sobre los perfiles de prueba, consulte [Envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   Este botón sólo se activa una vez que se hayan establecido los perfiles de prueba.

   >[!NOTE]
   >
   >Para un mensaje SMS no hay otra opción: es automáticamente un **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**:: comienza a preparar el envío. El **[!UICONTROL Deployment]** bloque aparece y muestra el resultado de la preparación. Este botón solo aparece una vez introducido el destino. Puede detener la preparación en cualquier momento utilizando el botón correspondiente.

   Para obtener más información sobre la preparación de mensajes, [Preparación del envío](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**:: confirma el envío del mensaje. Las estadísticas de envío aparecen en el **[!UICONTROL Deployment]** bloque. Este botón solo aparece después de que se haya preparado el envío. Puede detener o pausar el envío en cualquier momento mediante los botones **Detener envío** y **[!UICONTROL Pause]** .

   Para obtener más información sobre cómo confirmar el envío, consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

## Bloques {#blocks}

La pantalla principal está formada por diferentes bloques. Haga clic dentro de un bloque para acceder a la pantalla de parámetros correspondiente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**:: le permite realizar un seguimiento del progreso de la preparación o el envío de mensajes. Haga clic en el botón que se encuentra en la sección inferior derecha de este bloque para acceder a los registros de envío y análisis. Este bloque solo aparece una vez que se ha preparado el envío. Para más información sobre esto. Consulte [Confirmación de envío](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**:: permite establecer el objetivo principal del mensaje, así como los perfiles de prueba. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**:: permite especificar la fecha en la que se enviará el mensaje. Consulte [Programación](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**:: permite definir el contenido del mensaje y obtener una vista previa. Consulte Pasos [clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md).

