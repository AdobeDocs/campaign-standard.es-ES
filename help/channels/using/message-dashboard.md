---
title: Panel de mensajes
seo-title: Panel de mensajes
description: Panel de mensajes
seo-description: Descubra cómo se compone el panel de mensajes, incluso la barra de acciones y los distintos bloques funcionales.
page-status-flag: no activado nunca
uuid: 9 bb 44 ee 8-2 cf 6-43 ce -94 a 4-367 f 4 e 469713
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90 a 78742-697 f -46 da -8 c 54-108048 e 57 b 67
context-tags: entrega, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Message dashboard{#message-dashboard}

El panel de mensajes es un espacio de trabajo compuesto por distintos iconos, regroupados a una barra de acciones, y varios bloques funcionales que permiten establecer los parámetros del mensaje y enviarlos. Estos elementos se presentan aquí.

![](assets/delivery_dashboard_2.png)

## Gray bar {#gray-bar}

La barra gris recompone varios iconos vinculados al mensaje.

* **[!UICONTROL Summary]**: muestra u oculta la información principal relacionada con el mensaje.
* **[!UICONTROL Edit properties]**: permite editar los parámetros avanzados del mensaje.
* **[!UICONTROL Reports]**: le permite acceder a los informes relacionados con el mensaje.

**Temas relacionados:**

* [Configuración de canales](../../administration/using/about-channel-configuration.md)
* [Acceso a informes](../../reporting/using/about-dynamic-reports.md)

## Action bar {#action-bar}

La barra de acciones tiene iconos diferentes que permiten interactuar con el mensaje.

![](assets/delivery_dashboard_4.png)

Según los parámetros que se han configurado y el progreso realizado, es posible que algunos iconos no estén disponibles.

* **[!UICONTROL Show proofs]**: muestra u oculta la lista de pruebas que se han enviado, si existen. Este botón solo se activa una vez que haya enviado las pruebas.

   For more on proofs, see [Managing test profiles and sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md).

* **[!UICONTROL Send a test]**: permite seleccionar el modo de aprobación que se utilizará: **[!UICONTROL Email rendering]**, **[!UICONTROL Proof]** o ambos para un correo electrónico. For more on test profiles, see [Sending proofs](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs).

   Este botón solo se habilita una vez que haya establecido perfiles de prueba.

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: comienza a preparar el envío. The **[!UICONTROL Deployment]** block appears and displays the result of the preparation. Este botón sólo aparece una vez ingresado el objetivo. Puede detener la preparación en cualquier momento utilizando el botón correspondiente.

   For more on message preparation, [Preparing the send](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirma el envío del mensaje. The sending statistics appear in the **[!UICONTROL Deployment]** block. Este botón solo aparece después de preparar el envío. You can stop or pause the send at any time using the **Stop send** and **[!UICONTROL Pause]** buttons.

   For more on confirming sending, see [Sending messages](../../sending/using/confirming-the-send.md).

## Blocks {#blocks}

La pantalla principal se compone de diferentes bloques. Haga clic dentro de un bloque para acceder a la pantalla de parámetro correspondiente:

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: le permite realizar un seguimiento del progreso de la preparación o envío de mensajes. Haga clic en el botón que se encuentra en la sección inferior derecha de este bloque para acceder a los registros de envío y análisis. Este bloque solo aparece una vez preparado el envío. Para obtener más información sobre esto. See [Confirming send](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: le permite establecer el objetivo principal del mensaje como así también los perfiles de prueba. See [Creating audiences](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: permite especificar la fecha en la que se enviará el mensaje. See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: permite definir el contenido del mensaje y previsualizarlo. See [Defining content](../../designing/using/designing-content-in-adobe-campaign.md).

