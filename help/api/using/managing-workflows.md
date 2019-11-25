---
title: Administración de flujos de trabajo
description: Obtenga información sobre cómo administrar flujos de trabajo con API.
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
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Administración de flujos de trabajo {#managing-workflows}

## Control de un flujo de trabajo

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

## Activación de una actividad de señal

En un flujo de trabajo de Adobe Campaign Standard, puede haber una o varias actividades de señal **** externa. Estas actividades son "oyentes" que esperan activarse.

Las API de Campaign Standard permiten activar una actividad de señal **** externa para llamar a un flujo de trabajo. La llamada de API puede incluir parámetros que se van a ingerir en las variables de eventos del flujo de trabajo (un nombre de audiencia para el destino, un nombre de archivo para importar, una parte del contenido del mensaje, etc.). De este modo, puede integrar fácilmente las automatizaciones de su campaña con su sistema externo.

>[!NOTE]
>
>Las actividades de señal externa no se pueden activar con más frecuencia que cada 10 minutos y el flujo de trabajo de destino debe estar ya en ejecución.

Para activar un flujo de trabajo, siga los pasos a continuación:

1. Realice una solicitud **GET** en el flujo de trabajo para recuperar la dirección URL del activador de actividad de señal externa.

   `GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID>`

1. Realice una solicitud **POST** en la dirección URL devuelta para activar la actividad de señal, con el parámetro **"source"** en la carga útil. Este atributo es obligatorio, le permite indicar el origen de la solicitud de activación.

Si desea llamar al flujo de trabajo con parámetros, agréguelos a la carga útil con el atributo **"parameters"** . La sintaxis consiste en el nombre del parámetro seguido de su valor (se admiten los siguientes tipos: **cadena**, **número**, **booleano** y **fecha/hora**).

```
  -X POST <TRIGGER_URL>
  -H 'Authorization: Bearer <ACCESS_TOKEN>' \
  -H 'Cache-Control: no-cache' \
  -H 'X-Api-Key: <API_KEY>' \
  -H 'Content-Type: application/json;charset=utf-8' \
  -H 'Content-Length:79' \
  -i
  -d {
  -d    "source":"<SOURCE>",
  -d    "parameters":{
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>",  
  -d      "<PARAMETER_NAME":"<PARAMETER_VALUE>"
  -d    }
  -d }
```

>[!NOTE]
>
>Al agregar un parámetro a la carga útil, asegúrese de que sus valores de **nombre** y **tipo** sean coherentes con la información declarada en la actividad de señal externa. Además, el tamaño de la carga útil no debe superar los 64 Ko.

<br/>

***Solicitud de muestra***

Realice una solicitud GET en el flujo de trabajo.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<workflowID> \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

Devuelve la actividad de señal de flujo de trabajo y la dirección URL de activación asociada.

```
{
"PKey": "<PKEY>",
"activities": {
  "activity": {
    "signal1": {
      ...
      "trigger": {
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger/"
        },
        ...
      }
    }
  }
}
```

Para desencadenar una actividad de señal, realice una solicitud POST en la dirección URL de activación con el "origen". Agregue los atributos "parameters" si desea llamar al flujo de trabajo con parámetros.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/workflow/execution/<PKEY>/activities/activity/<PKEY>/trigger \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-i
-d '{
-d "source":"API",
-d "parameters":{
-d    "audience":"audience",
-d    "email":"anna.varney@mail.com",
-d    "template":"05",
-d    "contentURL":"http://www.adobe.com",
-d    "test":"true",
-d    "segmentCode":"my segment",
-d    "attribute":"2019-04-03 08:17:19.100Z"}
-d  }'
```

<!-- + réponse -->

Si uno de los parámetros no está declarado en la actividad de señal externa, la solicitud POST devuelve el error siguiente, indicando qué parámetro falta.

```
RST-360011 An error has occurred - please contact your administrator.
'contentURL' parameter isn't defined in signal activity.
XTK-170006 Unable to parse expression 'HandleTrigger(@name, $(source), $({parameters}))'.
RST-360000 Error while assessing 'HandleTrigger(@name, $(source), $({parameters}))' expression ('xtk:workflow:execution/activities/signal/trigger' resource)
```
