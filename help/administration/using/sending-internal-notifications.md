---
title: Envío de notificaciones internas
seo-title: Envío de notificaciones internas
description: Envío de notificaciones internas
seo-description: Obtenga información sobre cómo enviar notificaciones del sistema en tiempo real a los usuarios de Adobe Campaign.
page-status-flag: no activado nunca
uuid: f 196 f 025-dbb 9-4268-9 d 7 d-ff 626994 b 447
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: app-settings
discoiquuid: 4 d 51229 a -745 a -4 f 24-b 1 c 2-22 fa 203 b 499 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Sending internal notifications{#sending-internal-notifications}

Adobe Campaign le brinda la posibilidad de recibir notificaciones sobre actividades importantes del sistema directamente dentro de la aplicación. Las notificaciones en tiempo real mantienen informados a las partes interesadas y proporcionan a los usuarios la capacidad de actuar inmediatamente y directamente con respecto a las notificaciones de la actividad desde la aplicación. El resultado para los equipos es la agilidad, eficiencia y ejecución más fluida de las campañas.

![](assets/pulse_3.png)

Puede configurar notificaciones para los siguientes objetos:

* **[!UICONTROL A/B Test emails]**: el creador de correo electrónico y los modificadores reciben notificaciones de que se ha elegido una variante (modo automático) o que se debe elegir una variante (modo manual). Al hacer clic en la notificación se muestra el correo electrónico correspondiente. Las notificaciones se activan de forma predeterminada en la plantilla de prueba A/B predeterminada. If you want to deactivate them, edit the properties of the email or the email template and uncheck the box located under **General &gt; Notifications**. For more information on A/B Test emails, refer to [Creating an AB Test](../../channels/using/designing-an-a-b-test-email.md). For more on email properties, refer to [List of email properties](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada miembro del grupo de seguridad seleccionado recibe notificaciones (correo electrónico y notificación en la aplicación) siempre que se produzca un error de flujo de trabajo. Al hacer clic en la notificación o en el vínculo de correo electrónico, se muestra el flujo de trabajo correspondiente. Las notificaciones se desactivan de forma predeterminada en la plantilla de flujo de trabajo predeterminado. If you want to activate them, edit the properties of the workflow or workflow template and add a security group under **General &gt; Execution &gt; Error management &gt; Supervisors**. For more information on security groups, refer to [Managing groups and users](../../administration/using/managing-groups-and-users.md). For more on workflow properties, refer to [Workflow properties](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

