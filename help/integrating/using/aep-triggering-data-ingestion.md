---
title: Activación de la ingesta de datos mediante API
description: Obtenga información sobre cómo almacenar en déclencheur la ingesta de datos mediante API.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d67a796a-0730-4502-802c-d0b3583dd1dc
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 6%

---

# Activación de la ingesta de datos mediante API {#triggering-data-ingestion-apis}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra en la versión beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en fase beta solo para Norteamérica) para acceder a estas funciones. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea acceder.

Adobe Campaign Standard le permite almacenar en déclencheur la ingesta inmediata de asignaciones de datos a través de API y recuperar el estado de las solicitudes de ingesta.

En esta página se describe cómo almacenar en déclencheur y recuperar el estado de ingesta de las asignaciones de datos. Para obtener información global sobre las API de Campaign Standard, consulte [esta sección](../../api/using/get-started-apis.md).

## Requisitos previos {#prerequisites}

Antes de usar las API, la asignación de datos debe haberse configurado y publicado primero en la interfaz de Campaign Standard. Para obtener más información, consulte estas secciones:

* [Definición de la asignación](../../integrating/using/aep-mapping-definition.md)
* [Activación de la asignación](../../integrating/using/aep-mapping-activation.md)

Una vez creada la asignación de datos, debe detener la ejecución para que pueda almacenarla en déclencheur desde las API siempre que lo desee. Para ello, siga estos pasos:

1. En Campaign Standard, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** menú.

1. Haga doble clic en la asignación de datos para abrirla y luego haga clic en **[!UICONTROL Stop]** botón.

   ![](assets/aep_datamapping_stop.png)

1. Guarde los cambios

La ejecución de la asignación de datos está detenida. Puede utilizar las API de Campaign Standard para almacenarlo en déclencheur manualmente.

## Inicio de la ingesta inmediata de asignación de datos {#starting-immediate-ingestion}

La ingesta inmediata de una asignación XDM en Adobe Experience Platform se activa con una operación de POST:

`POST https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest`

>[!NOTE]
>
>Para ejecutar la llamada de API del POST de ingesta, el usuario debe tener un **Ejecución de función SQL** función, que puede proporcionar un administrador de Campaign Standards ejecutando el siguiente JS Script:
>
>```
>var sqlRoleObj = REST.head.roleBase.sql.get();
>REST.head.securityGroup.Administrators.roles.post(sqlRoleObj);
>```
>

La operación del POST devuelve información sobre el estado de la solicitud creada:

* Solicitud enviada correctamente para la asignación XDM:

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

* Error de solicitud porque la asignación XDM no se ha publicado o está detenida:

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

## Recuperación del estado de una solicitud de ingesta {#retrieving-status}

El estado de una solicitud de ingesta se puede recuperar con una operación de GET y el ID de solicitud deseado en los parámetros:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/dataIngestion/xdmIngestion/<XDM Mapping ID>/ingest
{"requestId"="<value>"}
```

>[!NOTE]
>
>Encontrará información detallada sobre el estado de la solicitud de asignación XDM y sus trabajos relacionados en la interfaz de Campaign Standard, en **[!UICONTROL Status of data export to platform]** menú (consulte [Activación de asignación](../../integrating/using/aep-mapping-activation.md)).

La operación de GET devuelve la siguiente información:

* **batchId**: este campo se rellena solo si se ha producido un error después de la preparación y carga del lote,
* **información**: ID de asignación de XDM,
* **numRecords**: el número de registros que se han introducido (solo estado de éxito),
* **status**: el estado de la solicitud de ingesta (correcta/fallida/en curso)

Las posibles respuestas a la operación de GET son:

* Solicitud de ingesta correcta:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ",
  "numRecords": 15,
  "requestId": 3520,
  "status": "Success"
  }
  ```

* Error en la solicitud de ingesta con registro 0 introducido:

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. ACP-880056 Failed to fetch the record from the database.",
  "numRecords": 0,
  "requestId": 3520,
  "status": "Failed"
  }
  ```

* Error en la solicitud de ingesta, con algún registro cargado en un lote:

  ```
  {
  "batchId": "<value>",
  "info": "Mapping Id: <value>. ACP-880096 Sync Job failed to upload. Please check the error in the Platform UI.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Failed"
  }
  ```

* Solicitud de ingesta anulada después de ingerir algunos registros (esto puede ocurrir en situaciones de bloqueo):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>. Ingestion request aborted due to some issue with data ingestion service. Please submit a new request",
  "numRecords": 0,
  "requestId": <value>,
  "status": "Aborted"
  }
  ```

* Solicitud de ingesta en curso (cuando la solicitud cargó los datos en un lote o cuando el lote se está preparando para la solicitud):

  ```
  {
  "batchId": "",
  "info": "Mapping Id: <value>.",
  "numRecords": 0,
  "requestId": <value>,
  "status": "In Progress"
  }
  ```
