---
title: Consulta incremental de los suscriptores a un servicio
description: El siguiente ejemplo presenta cómo configurar una actividad de consulta incremental para filtrar los suscriptores a un servicio.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 67%

---

# Consulta incremental de los suscriptores a un servicio {#example--incremental-query-on-subscribers-to-a-service}

En el siguiente ejemplo se muestra la configuración de una actividad de **[!UICONTROL Incremental query]** que filtra los perfiles de la base de datos de Adobe Campaign suscritos al servicio de **newsletter en ejecución**, para enviarles un correo electrónico de bienvenida que contenga un código de promoción.

El flujo de trabajo se compone de los siguientes elementos:

![](assets/incremental_query_example1.png)

* A [Planificador](../../automating/using/scheduler.md) para ejecutar el flujo de trabajo todos los lunes a las 6 de la mañana.

  ![](assets/incremental_query_example2.png)

* Un [Consulta incremental](../../automating/using/incremental-query.md) actividad de, que identifica a todos los suscriptores actuales durante la primera ejecución y luego solo a los nuevos suscriptores de esa semana durante las siguientes ejecuciones.

  ![](assets/incremental_query_example3.png)

* Un [Envío de correo electrónico](../../automating/using/email-delivery.md) actividad. El flujo de trabajo se ejecuta una vez por semana, pero puede acumular los correos electrónicos enviados y los resultados por mes, por ejemplo para generar informes a lo largo de un periodo de un mes entero y no solo una semana.

  Para ello, elija crear un **[!UICONTROL Recurring email]** aquí que reagrupe los correos electrónicos y los resultados **[!UICONTROL By month]**.

  Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida. Para obtener más información, consulte [Definición del contenido de correo electrónico](../../designing/using/personalization.md) secciones.

A continuación, ejecute el flujo de trabajo. Cada semana los nuevos suscriptores reciben el correo electrónico de bienvenida con el código de promoción.
