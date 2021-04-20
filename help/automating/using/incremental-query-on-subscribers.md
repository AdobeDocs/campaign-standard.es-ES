---
solution: Campaign Standard
product: campaign
title: Consulta incremental de los suscriptores a un servicio
description: El siguiente ejemplo presenta cómo configurar una actividad de consulta incremental para filtrar los suscriptores a un servicio.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 66%

---


# Consulta incremental de los suscriptores a un servicio {#example--incremental-query-on-subscribers-to-a-service}

En el siguiente ejemplo se muestra la configuración de una actividad de **[!UICONTROL Incremental query]** que filtra los perfiles de la base de datos de Adobe Campaign suscritos al servicio de **newsletter en ejecución**, para enviarles un correo electrónico de bienvenida que contenga un código de promoción.

El flujo de trabajo se compone de los siguientes elementos:

![](assets/incremental_query_example1.png)

* Una actividad [Scheduler](../../automating/using/scheduler.md) para ejecutar el flujo de trabajo todos los lunes a las 6 de la mañana.

   ![](assets/incremental_query_example2.png)

* Una actividad [Incremental query](../../automating/using/incremental-query.md) , que se dirige a todos los suscriptores actuales durante la primera ejecución y luego solo a los nuevos suscriptores de esa semana durante las siguientes ejecuciones.

   ![](assets/incremental_query_example3.png)

* Una actividad [Email delivery](../../automating/using/email-delivery.md). El flujo de trabajo se ejecuta una vez por semana, pero puede acumular los correos electrónicos enviados y los resultados por mes, por ejemplo para generar informes a lo largo de un periodo de un mes entero y no solo una semana.

   Para ello, elija crear un **[!UICONTROL Recurring email]** aquí que reagrupe los correos electrónicos y los resultados **[!UICONTROL By month]**.

   Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida. Para obtener más información, consulte las secciones [Definición del contenido del correo electrónico](../../designing/using/personalization.md) .

A continuación, ejecute el flujo de trabajo. Cada semana los nuevos suscriptores reciben el correo electrónico de bienvenida con el código de promoción.
