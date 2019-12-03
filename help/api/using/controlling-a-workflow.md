---
title: Control de un flujo de trabajo
description: Aprenda a controlar un flujo de trabajo con las API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Control de un flujo de trabajo {#controlling-a-workflow}

Puede controlar un flujo de trabajo directamente desde la API de REST, mediante una solicitud POST que contenga el ID de flujo de trabajo y el comando de ejecución requerido:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>/commands`

>[!CAUTION]
>
>Si se cambia el ID de flujo de trabajo en Adobe Campaign, la solicitud de API ya no funcionará.

Hay cuatro comandos de ejecución disponibles para controlar un flujo de trabajo:

* Inicio
* Pausar
* Reanudar
* Detener

Para obtener más información sobre los comandos de ejecución, consulte la documentación [de](https://helpx.adobe.com/campaign/standard/automating/using/executing-a-workflow.html)Campaña.

<br/>

***Solicitudes de muestra***

* Inicie un flujo de trabajo.

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
