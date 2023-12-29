---
title: Exportación de registros
description: Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar a través de un flujo de trabajo sencillo.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 14%

---

# Exportación de registros{#exporting-logs}

Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar a través de un flujo de trabajo sencillo. Permite analizar los resultados de las campañas en su propia herramienta de creación de informes o inteligencia de negocios.

>[!CAUTION]
>
>Solo funcional [administradores](../../administration/using/users-management.md#functional-administrators), con **[!UICONTROL Administration]** función y acceso a **Todo** las unidades pueden acceder a los registros de envío, los registros de mensajes, los registros de seguimiento y los registros de exclusión o suscripción. Un usuario no administrador puede dirigirse a estos registros empezando por una tabla vinculada (perfiles, envío).

Mediante un **[!UICONTROL Incremental query]** que solo recupera nuevos registros cada vez que se ejecuta el flujo de trabajo y una **[!UICONTROL Extract file]** actividad para definir las columnas de salida, puede obtener un archivo con el formato y todos los datos que necesite. A continuación, utilice un **[!UICONTROL Transfer file]** actividad para recuperar el archivo final. Cada ejecución del flujo de trabajo está planificada por un **[!UICONTROL Scheduler]**.

La operación de exportación de registros la pueden realizar los usuarios estándar. Recursos privados como: broadlogs, registros de seguimiento, registros de exclusión, registros de suscripción e registros de historial de suscripción **Perfiles** solo lo puede administrar un administrador funcional.

1. Cree un nuevo flujo de trabajo como se detalla en [esta sección](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Añadir un **[!UICONTROL Scheduler]** y configúrela según sus necesidades. A continuación se muestra un ejemplo de una ejecución mensual.

   ![](assets/export_logs_scheduler.png)

1. Añadir un **[!UICONTROL Incremental query]** actividad y configúrela para que seleccione los registros que necesite. Por ejemplo, para seleccionar todos los broadlogs nuevos o actualizados (registros de envío de perfil):

   * En el **[!UICONTROL Properties]** pestaña, cambie el recurso de destino a **Registros de envío** (broadLogRcp).

     ![](assets/export_logs_query_properties.png)

   * En el **[!UICONTROL Target]** , establezca una condición para recuperar todos los &quot;logs&quot; de entrega que correspondan a las entregas realizadas en 2016 o posteriormente. Para obtener más información, consulte la [Edición de consultas](../../automating/using/editing-queries.md#creating-queries) sección.

     ![](assets/export_logs_query_target.png)

   * En el **[!UICONTROL Processed data]** pestaña, seleccione **[!UICONTROL Use a date field]** y elija la **lastModified** field. En las siguientes ejecuciones del flujo de trabajo, solo se recuperan los registros que se hayan modificado o creado después de la última ejecución.

     ![](assets/export_logs_query_processeddata.png)

     Después de la primera ejecución del flujo de trabajo, puede ver en esta pestaña la última fecha de ejecución que se utiliza en la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

1. Añadir un **[!UICONTROL Extract file]** actividad que exportará los datos consultados en un archivo:

   * En el **[!UICONTROL Extraction]** , especifique el nombre del archivo.

     Si selecciona la opción **[!UICONTROL Add date and time to the file name]** , este nombre se completará automáticamente con la fecha de la exportación para garantizar que todos los archivos extraídos sean únicos. Seleccione las columnas que desea exportar en el archivo. Puede seleccionar aquí datos procedentes de recursos relacionados, como información de envío o de perfil.

     >[!NOTE]
     >
     >Para exportar un identificador único para cada registro, seleccione **[!UICONTROL Delivery log ID]** Elemento.

     Para organizar el archivo final, puede aplicar una ordenación. Por ejemplo, en la fecha de registro, como se muestra en el ejemplo siguiente.

     ![](assets/export_logs_extractfile_extraction.png)

   * En el **[!UICONTROL File structure]** pestaña, defina el formato del archivo de salida para que coincida con sus necesidades.

     Marque la opción **[!UICONTROL Export labels instead of internal values of enumerations]** en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas, que son fáciles de entender, en lugar de identificadores.

1. Añadir un **[!UICONTROL Transfer file]** y configúrelo para transferir el archivo recién creado desde el servidor de Adobe Campaign a otra ubicación desde la que pueda acceder, como un servidor SFTP.

   * En el **[!UICONTROL General]** pestaña, seleccione **[!UICONTROL File upload]** ya que el propósito es enviar el archivo de Adobe Campaign a otro servidor.
   * En el **[!UICONTROL Protocol]** pestaña, especifique los parámetros de transferencia y seleccione [cuenta externa](../../administration/using/external-accounts.md#creating-an-external-account) para usar.

1. Añadir un **[!UICONTROL End]** para asegurarse de que finaliza correctamente y guarde el flujo de trabajo.

   ![](assets/export_logs_example_workflow.png)

Ahora puede ejecutar el flujo de trabajo y recuperar el archivo de salida en el servidor externo.

**Temas relacionados:**

[Flujos de trabajo](../../automating/using/get-started-workflows.md)
