---
title: Exportación de datos de Campaign a Adobe Experience Platform
description: Obtenga información sobre cómo exportar datos de Campaign Standard a Adobe Experience Platform.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: eccd2922-0e75-4525-9b60-b48f628deeae
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 72%

---

# Exportación de datos de Campaign a Adobe Experience Platform {#sources}

Para exportar datos de Campaign Standard a Adobe Real-time Customer Data Platform (RTCDP), primero debe crear un flujo de trabajo en Campaign Standard para exportar los datos que desee compartir a su servicio de almacenamiento de Amazon (S3) o ubicación de almacenamiento de Azure Blob.

Una vez configurado el flujo de trabajo y enviado los datos a su ubicación de almacenamiento, debe conectar su ubicación de S3 o Azure Blob Storage como **fuente** en Adobe Experience Platform.

>[!NOTE]
>
>Tenga en cuenta que se recomienda exportar solo los datos generados por Campaign (por ejemplo, envíos, aperturas, clics, etc.) a Adobe Experience Platform. Los datos que se incorporan desde una fuente de terceros (como su CRM) deben importarse directamente en Adobe Experience Platform.

## Creación de un flujo de trabajo de exportación en Campaign Standard

Para exportar datos de Campaign Standard a la ubicación de S3 o Azure Blob Storage, debe crear un flujo de trabajo para dirigir los datos que desea exportar y enviarlos a su ubicación de almacenamiento.

Para ello, añada y configure lo siguiente:

* A **[!UICONTROL Extract file]** actividad para extraer los datos de destino en un archivo CSV. Para obtener más información sobre cómo configurar esta actividad, consulte[esta sección](../../automating/using/extract-file.md).

   ![](assets/rtcdp-extract-file.png)

* Una actividad **[!UICONTROL Transfer file]** para transferir el archivo CSV a su ubicación de almacenamiento. Para obtener más información sobre cómo configurar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

   ![](assets/rtcdp-transfer-file.png)

Por ejemplo, el flujo de trabajo siguiente extrae registros de forma regular en un archivo CSV y, a continuación, transfiere el archivo a una ubicación de almacenamiento.

![](assets/aep-export.png)

Hay ejemplos de flujos de trabajo de gestión de datos disponibles en la [casos de uso de flujos de trabajo](../../automating/using/about-workflow-use-cases.md#management) sección.

Temas relacionados:

* [Actividades de administración de datos](../../automating/using/about-data-management-activities.md)
* [Acerca de la importación y exportación de datos](../../automating/using/about-data-import-and-export.md)


## Conecte la ubicación de almacenamiento como origen

Pasos principales para conectar su ubicación de almacenamiento de Amazon Storage Service (S3) o Azure Blob como **Origen** en Adobe experience Platform se enumeran a continuación. Encontrará información detallada sobre cada uno de estos pasos en la [Documentación de conectores de origen](https://experienceleague.adobe.com/docs/experience-platform/sources/home.html?lang=es).

1. En el menú **[!UICONTROL Sources]** de Adobe Experience Platform, cree una conexión con su ubicación de almacenamiento:

   * [Creación de una conexión de origen de Amazon S3](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/s3.html?lang=es)
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
