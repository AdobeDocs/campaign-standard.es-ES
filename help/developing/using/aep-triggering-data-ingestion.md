---
solution: Campaign Standard
product: campaign
title: Activación de la ingesta de datos mediante API
description: Obtenga información sobre cómo déclencheur la ingesta de datos a través de las API.
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 5%

---


# Activación de la ingesta de datos mediante API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.

Adobe Campaign Standard le permite realizar el déclencheur de la ingestión inmediata de asignaciones de datos mediante API y recuperar el estado de sus solicitudes de inserción.

En esta página se describe cómo realizar el déclencheur y recuperar el estado de inserción de las asignaciones de datos. Para obtener información global sobre las API de Campaign Standard, consulte [esta sección](../../api/using/get-started-apis.md).

## Requisitos previos {#prerequisites}

Antes de utilizar las API, la asignación de datos debe haberse configurado y publicado primero en la interfaz de Campaign Standard. Para obtener más información, consulte estas secciones:

* [Definición de la asignación](../../developing/using/aep-mapping-definition.md)
* [Activación de la asignación](../../developing/using/aep-mapping-activation.md)

Una vez creada la asignación de datos, debe evitar que se ejecute para que pueda realizar el déclencheur desde las API cuando lo desee. Para ello, siga estos pasos:

1. En Campaign Standard, vaya al menú **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]**.

1. Haga clic con el botón doble en la asignación de datos para abrirla y, a continuación, haga clic en el botón **[!UICONTROL Stop]**.

   ![](assets/aep_datamapping_stop.png)

1. Guarde los cambios

La ejecución de la asignación de datos se ha detenido. Puede utilizar las API de Campaign Standard para déclencheur manual.

## Inicio de la ingestión inmediata de la asignación de datos {#starting-immediate-ingestion}

La ingestión inmediata de una asignación XDM en Adobe Experience Platform se activa con una operación de POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Para ejecutar la llamada de API de POST de ingesta, el usuario debe tener una función **de ejecución de la función SQL**, que puede proporcionar un administrador Campaign Standard mediante la ejecución de JS Script:
>
>
```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```

La operación POST devuelve información sobre el estado de la solicitud creada:

* La solicitud se envió correctamente para la asignación XDM:

```
{
"requestId": <value>,
"info": "Ingestion request submitted successfully for the Mapping ID: <value>",
"status":"Success"
}
```

* Solicitud ya en curso para la asignación XDM:

```
{
"requestId": <value>,
"info": "Ingestion request already in progress for the Mapping ID: <value>",
"status":"In Progress"
}
```

* Error en la solicitud porque la asignación XDM no está publicada o se ha detenido:

```
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not stopped",
"status": "Failed"
}
{
"info": "Unable to submit data ingestion request, XDM Mapping ID: <value> is not published",
"status": "Failed"
}
```

## Recuperando el estado de una solicitud de ingestión {#retrieving-status}

El estado de una solicitud de inserción se puede recuperar con una operación de GET y el ID de solicitud deseado en los parámetros:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Encontrará información detallada sobre el estado de la solicitud de asignación XDM y sus trabajos relacionados en la interfaz de Campaign Standard, en el menú **[!UICONTROL Status of data export to platform]** (consulte [activación de asignación](../../developing/using/aep-mapping-activation.md)).

La operación de GET devuelve la información siguiente:

* **batchId**: este campo solo se rellena si se ha producido un error tras la preparación y carga del lote,
* **información**: el ID de asignación XDM,
* **numRecords**: el número de registros que se han ingestado (solo en el estado de éxito),
* **estado**: estado de la solicitud de ingesta (correcto/fallido/en curso)

Las respuestas posibles a la operación de GET son:

* Solicitud de entrada correcta:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ",
   "numRecords": 15,
   "requestId": 3520,
   "status": "Success"
   }
   ```

* Error en la solicitud de entrada con el registro 0 ingerido:

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
   "numRecords": 0,
   "requestId": 3520,
   "status": "Failed"
   }
   ```

* Error en la solicitud de entrada; algunos registros se han cargado en un lote:

   ```
   {
   "batchId": "<value>",
   "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Failed"
   }
   ```

* Se anuló la solicitud de ingesta después de ingerir algunos registros (esto puede ocurrir en casos de bloqueo):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
   "numRecords": 0,
   "requestId": <value>,
   "status": "Aborted"
   }
   ```

* Solicitud de ingesta en curso (cuando la solicitud carga los datos en un lote o cuando el lote se está preparando para la solicitud):

   ```
   {
   "batchId": "",
   "info": "Mapping Id: <value>.",
   "numRecords": 0,
   "requestId": <value>,
   "status": "In Progress"
   }
   ```
