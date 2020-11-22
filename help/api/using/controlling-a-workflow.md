---
solution: Campaign Standard
product: campaign
title: Control de un flujo de trabajo
description: Aprenda a controlar un flujo de trabajo con las API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '96'
ht-degree: 9%

---


# Control de un flujo de trabajo {#controlling-a-workflow}

Puede controlar un flujo de trabajo directamente desde la API de REST, mediante una solicitud de POST que contenga el ID de flujo de trabajo y el comando de ejecución requerido:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si se cambia el ID de flujo de trabajo en Adobe Campaign, la solicitud de API ya no funcionará.

Hay cuatro comandos de ejecución disponibles para controlar un flujo de trabajo:

* Start
* Pause
* Reanudar
* Stop

Para obtener más información sobre los comandos de ejecución, consulte la documentación [de la](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/executing-a-workflow/about-workflow-execution.html)Campaña.

<br/>

***Solicitudes de muestra***

* Inicio de un flujo de trabajo.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"start"}'
   ```

   <!-- + réponse -->

* Detenga un flujo de trabajo.

   ```
   -X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands \
   -H 'Content-Type: application/json' \
   -H 'Authorization: Bearer <ACCESS_TOKEN>' \
   -H 'Cache-Control: no-cache' \
   -H 'X-Api-Key: <API_KEY>' \
   -i
   -d '{"method":"stop"}'
   ```

   <!-- + réponse -->
