---
title: Exportación de datos de Campaign a Adobe Experience Platform
description: Obtenga información sobre cómo exportar datos de Campaign Standard a Adobe Experience Platform.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
TQID: https://experienceleague.adobe.com/wevJB72xRacTndQ1-VOyKHOtRak0UKJT2V-pzUd6d-Q
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
subfeature_v2:
  - id: b70f632b-2cfd-43d0-9266-284281100d70
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 537
ht-degree: 67%

---

# Exportación de datos de Campaign a Adobe Experience Platform {#sources}

Para exportar datos de Campaign Standard a la plataforma de datos del cliente en tiempo real de Adobe (RTCDP), primero debe crear un flujo de trabajo en Campaign Standard para exportar los datos que desee compartir a su servicio de almacenamiento de Amazon (S3) o a la ubicación de almacenamiento del blob de Azure.

Una vez configurado el flujo de trabajo y enviado los datos a su ubicación de almacenamiento, debe conectar su ubicación de S3 o Azure Blob Storage como **fuente** en Adobe Experience Platform.

>[!NOTE]
>
>Tenga en cuenta que se recomienda exportar solo los datos generados por Campaign (por ejemplo, envíos, aperturas, clics, etc.) a Adobe Experience Platform. Los datos que se incorporan desde una fuente de terceros (como su CRM) deben importarse directamente en Adobe Experience Platform.

## Creación de un flujo de trabajo de exportación en Campaign Standard

Para exportar datos de Campaign Standard a la ubicación de S3 o Azure Blob Storage, debe crear un flujo de trabajo para dirigir los datos que desea exportar y enviarlos a su ubicación de almacenamiento.

Para ello, añada y configure lo siguiente:

* Una actividad **[!UICONTROL Extract file]** para extraer los datos de destino en un archivo CSV. Para obtener más información sobre cómo configurar esta actividad, consulte[esta sección](../../automating/using/extract-file.md).

  ![](assets/rtcdp-extract-file.png)

* Una actividad **[!UICONTROL Transfer file]** para transferir el archivo CSV a su ubicación de almacenamiento. Para obtener más información sobre cómo configurar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

  ![](assets/rtcdp-transfer-file.png)

Por ejemplo, el flujo de trabajo siguiente extrae registros de forma regular en un archivo CSV y, a continuación, transfiere el archivo a una ubicación de almacenamiento.

![](assets/aep-export.png)

Hay ejemplos de flujos de trabajo de administración de datos disponibles en la sección [casos de uso de flujos de trabajo](../../automating/using/about-workflow-use-cases.md#management).

Temas relacionados:

* [Actividades de administración de datos](../../automating/using/about-data-management-activities.md)
* [Acerca de la importación y exportación de datos](../../automating/using/about-data-import-and-export.md)


## Conecte la ubicación de almacenamiento como origen

A continuación, se enumeran los pasos principales para conectar el servicio de almacenamiento de Amazon (S3) o la ubicación de almacenamiento Azure Blob como **Source** en Adobe Experience Platform. Encontrará información detallada sobre cada uno de estos pasos en la [Documentación de conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es).

1. En el menú **[!UICONTROL Sources]** de Adobe Experience Platform, cree una conexión con su ubicación de almacenamiento:

   * [Crear una conexión de origen de Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=es)
   * [Conector de Azure Blob](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/cloud-storage/blob.html?lang=es)

   >[!NOTE]
   >
   >La ubicación de almacenamiento puede ser Amazon S3, SFTP con contraseña, SFTP con clave SSH o conexiones Azure Blob. El método preferido para enviar datos a Adobe Campaign es mediante Amazon S3 o Azure Blob:

   ![](assets/rtcdp-connector.png)

1. Configure un flujo de datos para una conexión por lotes de almacenamiento en la nube. Un flujo de datos es una tarea programada que recupera e ingiere datos de la ubicación de almacenamiento en un conjunto de datos de Adobe Experience Platform. Estos pasos le permiten configurar la ingesta de datos desde su ubicación de almacenamiento, incluida la selección de datos y la asignación de los campos CSV a un esquema XDM.

   Esta información está disponible en [esta página](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html?lang=es).

   ![](assets/rtcdp-map-xdm.png)

1. Una vez configurado el origen, Adobe Experience Platform importará el archivo desde la ubicación de almacenamiento proporcionada.

   Esta operación se puede programar según sus necesidades. Se recomienda realizar la exportación hasta 6 veces al día, en función de la carga ya presente en la instancia.
