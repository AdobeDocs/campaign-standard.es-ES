---
title: Envío de notificaciones internas
description: Aprenda a enviar notificaciones del sistema en tiempo real a los usuarios de Adobe Campaign
audience: administration
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Envío de notificaciones internas{#sending-internal-notifications}

Adobe Campaign le permite recibir notificaciones sobre actividades importantes del sistema directamente dentro de la aplicación. Las notificaciones en tiempo real mantienen informadas a las partes interesadas relevantes y proporcionan a los usuarios la capacidad de actuar de forma inmediata y directa en las notificaciones de actividades desde la aplicación. El resultado para los equipos es una agilidad avanzada, eficiencia y una ejecución más fluida de las campañas.

![](assets/pulse_3.png)

Puede configurar notificaciones para los siguientes objetos:

* **[!UICONTROL A/B Test emails]**: se notifica al creador de correo electrónico y a los modificadores que se ha elegido una variante (modo automático) o que es necesario elegir una variante (modo manual). Al hacer clic en la notificación, se muestra el correo electrónico correspondiente. Las notificaciones se activan de forma predeterminada en la plantilla de prueba A/B predeterminada. Si desea desactivarlas, edite las propiedades del correo electrónico o la plantilla de correo electrónico y desmarque la casilla situada debajo de **General > Notificaciones**. Para obtener más información sobre los correos electrónicos de prueba A/B, consulte [Creación de una prueba AB](../../channels/using/designing-an-a-b-test-email.md). Para obtener más información sobre las propiedades de correo electrónico, consulte [Lista de propiedades de correo electrónico](../../administration/using/configuring-email-channel.md#list-of-email-properties).

  ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: se notifica a cada miembro del grupo de seguridad seleccionado (correo electrónico y notificación en la aplicación) cada vez que un flujo de trabajo presenta un error. Al hacer clic en la notificación o en el vínculo de correo electrónico, se muestra el flujo de trabajo correspondiente. Las notificaciones están desactivadas de forma predeterminada en la plantilla de flujo de trabajo predeterminada. Si desea activarlas, edite las propiedades del flujo de trabajo o la plantilla de flujo de trabajo y añada un grupo de seguridad en **General > Ejecución > Gestión de errores > Supervisores**. Para obtener más información sobre los grupos de seguridad, consulte [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md). Para obtener más información sobre las propiedades del flujo de trabajo, consulte [Propiedades de flujo de trabajo](../../automating/using/managing-execution-options.md).

  ![](assets/pulse_1.png)
