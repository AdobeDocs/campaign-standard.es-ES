---
solution: Campaign Standard
product: campaign
title: Exportación de registros
description: Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar mediante un flujo de trabajo sencillo.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 14%

---


# Exportación de registros{#exporting-logs}

Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar mediante un flujo de trabajo sencillo. Le permite analizar los resultados de sus campañas en su propia herramienta de sistema de informes o BI.

>[!CAUTION]
>
>Sólo los [administradores funcionales](../../administration/using/users-management.md#functional-administrators), con **[!UICONTROL Administration]** rol y acceso a **Todas** unidades pueden acceder al envío de registros, registros de mensajes, registros de seguimiento, registros de exclusión o de suscripciones. Un usuario no administrador puede destinatario estos registros, pero puede comenzar en una tabla vinculada (perfiles, envío).

Al utilizar **[!UICONTROL Incremental query]** que sólo recupera nuevos registros cada vez que se ejecuta el flujo de trabajo y una actividad **[!UICONTROL Extract file]** simple para definir las columnas de salida, puede obtener un archivo con el formato y todos los datos que necesita. A continuación, utilice una actividad **[!UICONTROL Transfer file]** para recuperar el archivo final. Cada ejecución del flujo de trabajo está planificada por un **[!UICONTROL Scheduler]**.

Los usuarios estándar pueden realizar la operación de registros de exportación. Recursos privados como: los logs de banda ancha, registros de seguimiento, registros de exclusión y los registros de suscripción del historial de suscripciones en **Perfiles** sólo pueden ser administrados por el administrador funcional.

1. Cree un nuevo flujo de trabajo como se detalla en [esta sección](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Añada una actividad **[!UICONTROL Scheduler]** y configúrela según sus necesidades. A continuación se muestra un ejemplo de ejecución mensual.

   ![](assets/export_logs_scheduler.png)

1. Añada una actividad **[!UICONTROL Incremental query]** y configúrela para que seleccione los registros que necesita. Por ejemplo, para seleccionar todos los logs nuevos o actualizados (registros de envío de perfil):

   * En la ficha **[!UICONTROL Properties]**, cambie el recurso de destinatario a **Registros de envío** (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * En la ficha **[!UICONTROL Target]**, establezca una condición para recuperar todos los registros de envío que correspondan a envíos enviados en 2016 o después. Para obtener más información, consulte la sección [Edición de consultas](../../automating/using/editing-queries.md#creating-queries).

      ![](assets/export_logs_query_target.png)

   * En la ficha **[!UICONTROL Processed data]**, seleccione **[!UICONTROL Use a date field]** y elija el campo **lastModified**. En las próximas ejecuciones del flujo de trabajo, solo se recuperarán los registros que se hayan modificado o creado después de la última ejecución.

      ![](assets/export_logs_query_processeddata.png)

      Después de la primera ejecución del flujo de trabajo, puede ver en esta pestaña la última fecha de ejecución que se utiliza en la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

1. Añada una actividad **[!UICONTROL Extract file]** que exportará los datos consultados en un archivo:

   * En la ficha **[!UICONTROL Extraction]**, especifique el nombre del archivo.

      Si selecciona la opción **[!UICONTROL Add date and time to the file name]**, este nombre se completará automáticamente con la fecha de exportación para garantizar que todos los archivos extraídos sean únicos. Seleccione las columnas que desee exportar en el archivo. Puede seleccionar aquí los datos procedentes de recursos relacionados, como información de envíos o perfiles.

      >[!NOTE]
      >
      >Para exportar un identificador único para cada registro, seleccione el elemento **[!UICONTROL Delivery log ID]**.

      Para organizar el archivo final, puede aplicar una ordenación. Por ejemplo, en la fecha de registro, como se muestra en el ejemplo siguiente.

      ![](assets/export_logs_extractfile_extraction.png)

   * En la ficha **[!UICONTROL File structure]**, defina el formato del archivo de salida para que coincida con sus necesidades.

      Marque la opción **[!UICONTROL Export labels instead of internal values of enumerations]** en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas, que son fáciles de entender, en lugar de identificadores.

1. Añada una actividad **[!UICONTROL Transfer file]** y configúrela para transferir el archivo recién creado del servidor Adobe Campaign a otra ubicación a la que pueda acceder, como un servidor SFTP.

   * En la ficha **[!UICONTROL General]**, seleccione **[!UICONTROL File upload]** ya que el propósito es enviar el archivo de Adobe Campaign a otro servidor.
   * En la ficha **[!UICONTROL Protocol]**, especifique los parámetros de transferencia y seleccione la [cuenta externa](../../administration/using/external-accounts.md#creating-an-external-account) que desee utilizar.

1. Añada una actividad **[!UICONTROL End]** para asegurarse de que termina correctamente y guarde el flujo de trabajo.

   ![](assets/export_logs_example_workflow.png)

Ahora puede ejecutar el flujo de trabajo y recuperar el archivo de salida en el servidor externo.

**Temas relacionados:**

[Flujos de trabajo](../../automating/using/get-started-workflows.md)
