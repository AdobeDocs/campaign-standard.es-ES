---
title: Uso de datos de flujo de trabajo
description: Conozca las diferentes posibilidades de utilizar los datos importados o dirigidos.
page-status-flag: nunca activado
uuid: 3dd66aeb-3a26-4214-b6a0-242c2b7fbc49
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: workflow-general-operation
discoiquuid: 90b250f1-f32d-4256-83ea-4c0627628610
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Uso de datos de flujo de trabajo{#using-workflow-data}

Una vez identificados y preparados los datos, se pueden utilizar en los siguientes contextos:

* La **[!UICONTROL Update data]** actividad permite realizar una actualización masiva de los campos de la base de datos.
* La **[!UICONTROL Save audience]** actividad le permite actualizar una audiencia existente o crear una nueva a partir de la población calculada en sentido ascendente en un flujo de trabajo. Las audiencias creadas o actualizadas a partir de esta actividad son audiencias de **lista** o **archivo** . Esta actividad también le permite exportar perfiles como audiencias o segmentos de Adobe Experience Cloud.
* La **[!UICONTROL Subscription Services]** actividad le permite tomar perfiles en masa y suscribirlos a un servicio o cancelarlos de un servicio.
* La **[!UICONTROL Extract file]** actividad le permite exportar datos de Adobe Campaign en forma de archivo externo.

Después de definir un objetivo de perfil, puede utilizar varias actividades para crear y enviar envíos:

* La **[!UICONTROL Email delivery]** actividad le permite configurar el envío de un correo electrónico en un flujo de trabajo. Puede ser un **único correo electrónico de envío** y enviarlo una sola vez, o puede ser un correo electrónico **recurrente** .
* La **[!UICONTROL SMS delivery]** actividad le permite configurar el envío de un SMS en un flujo de trabajo. Puede ser un **único mensaje** de SMS y enviado una sola vez, o puede ser un mensaje de texto **recurrente** .
* La **[!UICONTROL Mobile app delivery]** actividad permite configurar el envío de una notificación push en un flujo de trabajo. Puede ser una **sola notificación de envío** y enviarse una sola vez, o puede ser una notificación **recurrente** .

