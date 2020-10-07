---
title: Consulta incremental de los suscriptores a un servicio
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---


# Consulta incremental de los suscriptores a un servicio {#example--incremental-query-on-subscribers-to-a-service}

En el siguiente ejemplo se muestra la configuración de una actividad de **[!UICONTROL Incremental query]** que filtra los perfiles de la base de datos de Adobe Campaign suscritos al servicio de **newsletter en ejecución**, para enviarles un correo electrónico de bienvenida que contenga un código de promoción.

El flujo de trabajo se compone de los siguientes elementos:

![](assets/incremental_query_example1.png)

* A [Scheduler](../../automating/using/scheduler.md) activity, to execute the workflow every Monday at 6 am.

   ![](assets/incremental_query_example2.png)

* An [Incremental query](../../automating/using/incremental-query.md) activity, which targets all of the current subscribers during the first execution, then only the new subscribers of that week during the following executions.

   ![](assets/incremental_query_example3.png)

* Una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico. El flujo de trabajo se ejecuta una vez por semana, pero puede acumular los correos electrónicos enviados y los resultados por mes, por ejemplo para generar informes a lo largo de un periodo de un mes entero y no solo una semana.

   Para ello, elija crear un **[!UICONTROL Recurring email]** aquí que reagrupe los correos electrónicos y los resultados **[!UICONTROL By month]**.

   Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida. Para obtener más información sobre esto, consulte [Definición de secciones de contenido](../../designing/using/personalization.md) de correo electrónico.

A continuación, ejecute el flujo de trabajo. Cada semana los nuevos suscriptores reciben el correo electrónico de bienvenida con el código de promoción.
