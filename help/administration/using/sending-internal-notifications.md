---
solution: Campaign Standard
product: campaign
title: Envío de notificaciones internas
description: Obtenga información sobre cómo enviar notificaciones del sistema en tiempo real a los usuarios de Adobe Campaign.
audience: administration
content-type: reference
topic-tags: application-settings
feature: Configuración de instancia
role: Admin
level: Experienced
exl-id: 7e04275a-5413-4f03-b18c-b64ab482d7d5
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 2%

---

# Envío de notificaciones internas{#sending-internal-notifications}

Adobe Campaign le ofrece la posibilidad de recibir notificaciones sobre actividades importantes del sistema directamente dentro de la aplicación. Las notificaciones en tiempo real mantienen informadas a las partes interesadas y permiten a los usuarios actuar de forma inmediata y directa sobre las notificaciones de actividades desde la aplicación. El resultado para los equipos es agilidad avanzada, eficiencia y una ejecución más fluida de las campañas.

![](assets/pulse_3.png)

Puede configurar las notificaciones para los siguientes objetos:

* **[!UICONTROL A/B Test emails]**: se notifica al creador de correo electrónico y a los modificadores que se ha elegido una variante (modo automático) o que se debe elegir una variante (modo manual). Al hacer clic en la notificación, se muestra el correo electrónico correspondiente. Las notificaciones se activan de forma predeterminada en la plantilla predeterminada Prueba A/B . Si desea desactivarlos, edite las propiedades del correo electrónico o de la plantilla de correo electrónico y desmarque la casilla ubicada en **General > Notifications**. Para obtener más información sobre los correos electrónicos de prueba A/B, consulte [Creación de una prueba A/B](../../channels/using/designing-an-a-b-test-email.md). Para obtener más información sobre las propiedades de correo electrónico, consulte [Lista de propiedades de correo electrónico](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/pulse_2.png)

* **[!UICONTROL Workflows]**: cada miembro del grupo de seguridad seleccionado recibe una notificación (correo electrónico y notificación en la aplicación) siempre que un flujo de trabajo esté en error. Al hacer clic en la notificación o en el vínculo de correo electrónico, se muestra el flujo de trabajo correspondiente. Las notificaciones se desactivan de forma predeterminada en la plantilla de flujo de trabajo predeterminada. Si desea activarlos, edite las propiedades del flujo de trabajo o la plantilla de flujo de trabajo y añada un grupo de seguridad en **General > Execution > Error management > Supervisors**. Para obtener más información sobre los grupos de seguridad, consulte [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md). Para obtener más información sobre las propiedades del flujo de trabajo, consulte [Propiedades del flujo de trabajo](../../automating/using/managing-execution-options.md).

   ![](assets/pulse_1.png)
