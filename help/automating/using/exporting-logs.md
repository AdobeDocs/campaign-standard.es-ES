---
title: Exportación de registros
seo-title: Exportación de registros
description: Exportación de registros
seo-description: Los datos de registro, tanto si están relacionados con entregas como con suscripciones, pueden exportarse a través de un simple flujo de trabajo.
page-status-flag: no activado nunca
uuid: 954 e 919 c -0 a 33-47 c 3-9 a 3 c -63 c 7 a 2 a 4 edc 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: importar y exportar datos
discoiquuid: ca 8 a 95 d 8-523 f -4085-a 2 fc-e 1 d 8262 cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting logs{#exporting-logs}

Los datos de registro, tanto si están relacionados con entregas como con suscripciones, pueden exportarse a través de un simple flujo de trabajo. Permite analizar los resultados de las campañas en su propia herramienta de informes o BI.

By using an **[!UICONTROL Incremental query]** that only retrieves new logs every time the workflow is executed and a simple **[!UICONTROL Extract file]** activity to define the output columns, you can get a file with the format and all the data you need. Then use a **[!UICONTROL Transfer file]** activity to retrieve the final file. Each workflow execution is planned by a **[!UICONTROL Scheduler]**.

Los usuarios estándar pueden llevar a cabo la operación de registros de exportación. Private resources such as: broadlogs, tracking logs, exclusion logs subscription logs and subscription history logs on **Profiles** can only be managed by functional administrator.

1. Create a new workflow as detailed in [this section](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Add a **[!UICONTROL Scheduler]** activity and set it according to your needs. A continuación se muestra un ejemplo de ejecución mensual.

   ![](assets/export_logs_scheduler.png)

1. Add an **[!UICONTROL Incremental query]** activity and configure it so that it selects the logs you need. Por ejemplo, para seleccionar todos los gráficos Broadlogs nuevos o actualizados (registros de entrega de perfil):

   * In the **[!UICONTROL Properties]** tab, change the target resource to **Delivery logs** (broadLogRcp).

      ![](assets/export_logs_query_properties.png)

   * In the **[!UICONTROL Target]** tab, set a condition to retrieve all delivery logs that correspond to deliveries sent in 2016 or after. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * In the **[!UICONTROL Processed data]** tab, select **[!UICONTROL Use a date field]** and choose the **lastModified** field. En las siguientes ejecuciones del flujo de trabajo, solo los registros que se hayan modificado o creado después de la última ejecución se recuperarán.

      ![](assets/export_logs_query_processeddata.png)

      Después de la primera ejecución del flujo de trabajo, puede ver en esta ficha la última fecha de ejecución que se utilizará para la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Aún tiene la posibilidad de omitir este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

1. Add an **[!UICONTROL Extract file]** activity that will export the queried data in a file:

   * In the **[!UICONTROL Extraction]** tab, specify the name of the file. Este nombre se completará automáticamente con la fecha de la exportación para garantizar que todos los archivos extraídos sean únicos.

      Seleccione las columnas que desee exportar en el archivo. Aquí puede seleccionar datos procedentes de recursos relacionados como la entrega o la información de perfil. Para organizar el archivo final, puede aplicar una clasificación. Por ejemplo, en la fecha de registro, como se muestra en el ejemplo siguiente.

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >No es posible exportar identificadores únicos (claves principales) de los recursos de registro.

   * In the **[!UICONTROL File structure]** tab, define the format of the output file to match your needs.

      Check the **[!UICONTROL Export labels instead of internal values of enumerations]** option in case you export enumeration values. Esta opción permite recuperar etiquetas más cortas fáciles de entender en lugar de ID.

1. Add a **[!UICONTROL Transfer file]** activity and configure it to transfer the newly created file from the Adobe Campaign server to another location where you can access it, such as a SFTP server.

   * In the **[!UICONTROL General]** tab, select **[!UICONTROL File upload]** as the purpose is to send the file from Adobe Campaign to another server.
   * In the **[!UICONTROL Protocol]** tab, specify the transfer parameters and select the [external account](../../administration/using/external-accounts.md#creating-an-external-account) to use.

1. Add an **[!UICONTROL End]** activity to make sure it properly ends and save your workflow.

   ![](assets/export_logs_example_workflow.png)

Ahora puede ejecutar el flujo de trabajo y recuperar el archivo de salida en su servidor externo.

**Tema relacionado:**

[Flujos de trabajo](../../automating/using/discovering-workflows.md)
