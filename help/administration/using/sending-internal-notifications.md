---
title: Envío de notificaciones internas
description: Descubra cómo enviar notificaciones del sistema en tiempo real a los usuarios de Adobe Campaign.
page-status-flag: nunca activado
uuid: f196f025-dbb9-4268-9d7d-ff626994b447
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: application-settings
discoiquuid: 4d51229a-745a-4f24-b1c2-22fa203b499c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Envío de notificaciones internas{#sending-internal-notifications}

Adobe Campaign le ofrece la posibilidad de recibir notificaciones sobre actividades importantes del sistema directamente dentro de la aplicación.  Las notificaciones en tiempo real mantienen informados a los interesados pertinentes y proporcionan a los usuarios la capacidad de actuar de forma inmediata y directa en las notificaciones de actividades desde la aplicación. El resultado para los equipos es agilidad avanzada, eficiencia y ejecución más fluida de las campañas.

![](assets/pulse_3.png)

Puede configurar las notificaciones para los siguientes objetos:

* **[!UICONTROL A/B Test emails]**:: se notifica al creador y a los modificadores de correo electrónico que se ha elegido una variante (modo automático) o que es necesario elegir una variante (modo manual). Al hacer clic en la notificación se muestra el correo electrónico correspondiente. Las notificaciones se activan de forma predeterminada en la plantilla predeterminada Prueba A/B. Si desea desactivarlos, edite las propiedades del correo electrónico o la plantilla de correo electrónico y desmarque la casilla ubicada en **General &gt; Notificaciones**. Para obtener más información sobre los correos electrónicos de la prueba A/B, consulte [Creación de una prueba](../../channels/using/designing-an-a-b-test-email.md)A/B. Para obtener más información sobre las propiedades de correo electrónico, consulte [Lista de propiedades](../../administration/using/configuring-email-channel.md#list-of-email-properties)de correo electrónico.

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**:: cada miembro del grupo de seguridad seleccionado recibe una notificación (por correo electrónico y en la aplicación) cuando se produce un error en un flujo de trabajo. Al hacer clic en la notificación o en el vínculo de correo electrónico se muestra el flujo de trabajo correspondiente. Las notificaciones se desactivan de forma predeterminada en la plantilla de flujo de trabajo lista para usar. Si desea activarlos, edite las propiedades de la plantilla de flujo de trabajo o flujo de trabajo y agregue un grupo de seguridad en **General &gt; Ejecución &gt; Administración de errores &gt; Supervisores**. Para obtener más información sobre los grupos de seguridad, consulte [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md). Para obtener más información sobre las propiedades del flujo de trabajo, consulte Propiedades [del flujo de trabajo](../../automating/using/executing-a-workflow.md#workflow-properties).

   ![](assets/pulse_1.png)

