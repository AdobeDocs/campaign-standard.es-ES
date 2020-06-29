---
title: Consulta incremental sobre los suscriptores de un servicio
description: En el siguiente ejemplo se muestra cómo configurar una actividad de Consulta incremental para filtrar los suscriptores a un servicio.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 0%

---


# Consulta incremental sobre los suscriptores de un servicio {#example--incremental-query-on-subscribers-to-a-service}

En el siguiente ejemplo se muestra la configuración de una **[!UICONTROL Incremental query]** actividad que filtros los perfiles de la base de datos de Adobe Campaign suscritos al servicio **de newsletter** en ejecución, para enviarles un correo electrónico de bienvenida que contenga un código de promoción.

El flujo de trabajo se compone de los siguientes elementos:

![](assets/incremental_query_example1.png)

* actividad [Planificador](../../automating/using/scheduler.md) para ejecutar el flujo de trabajo todos los lunes a las 6 de la mañana.

   ![](assets/incremental_query_example2.png)

* Una actividad de [Consulta incremental](../../automating/using/incremental-query.md) , que destinatario a todos los suscriptores actuales durante la primera ejecución, y sólo a los nuevos suscriptores de esa semana durante las siguientes ejecuciones.

   ![](assets/incremental_query_example3.png)

* Una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico. El flujo de trabajo se ejecuta una vez por semana, pero puede acumulado los correos electrónicos enviados y los resultados por mes, por ejemplo para generar informes a lo largo de un período de un mes entero y no solo una semana.

   Para ello, elija crear un **[!UICONTROL Recurring email]** aquí que reagrupe los correos electrónicos y los resultados **[!UICONTROL By month]**.

   Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida. Para obtener más información sobre esto, consulte [Definición de secciones de contenido](../../designing/using/personalization.md) de correo electrónico.

A continuación, inicio la ejecución del flujo de trabajo. Cada semana los nuevos suscriptores recibirán el correo electrónico de bienvenida con el código de promoción.
