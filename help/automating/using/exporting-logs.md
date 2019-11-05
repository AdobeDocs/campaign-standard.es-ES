---
title: Exportación de registros
description: Los datos de registro, tanto si están relacionados con entregas como con suscripciones, se pueden exportar mediante un flujo de trabajo sencillo.
page-status-flag: nunca activado
uuid: 954e919c-0a33-47c3-9a3c-63c7a2a4edc4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: importar y exportar datos
discoiquuid: ca8a95d8-523f-4085-a2fc-e1d8262cfbae
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Exportación de registros{#exporting-logs}

Los datos de registro, tanto si están relacionados con entregas como con suscripciones, se pueden exportar mediante un flujo de trabajo sencillo. Permite analizar los resultados de las campañas en su propia herramienta de generación de informes o BI.

Si utiliza un **[!UICONTROL Incremental query]** que solo recupera nuevos registros cada vez que se ejecuta el flujo de trabajo y una **[!UICONTROL Extract file]** actividad simple para definir las columnas de salida, puede obtener un archivo con el formato y todos los datos que necesita. A continuación, utilice una **[!UICONTROL Transfer file]** actividad para recuperar el archivo final. Cada ejecución del flujo de trabajo está planificada por un **[!UICONTROL Scheduler]**.

Los usuarios estándar pueden realizar la operación de registros de exportación. Recursos privados como: los logs de banda ancha, los registros de seguimiento, los registros de suscripción de registros de registros de exclusión y los registros del historial de suscripción en **Perfiles** sólo pueden ser administrados por un administrador funcional.

1. Cree un nuevo flujo de trabajo como se detalla en [esta sección](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Agregue una **[!UICONTROL Scheduler]** actividad y configúrela según sus necesidades. A continuación se muestra un ejemplo de ejecución mensual.

   ![](assets/export_logs_scheduler.png)

1. Agregue una **[!UICONTROL Incremental query]** actividad y configúrela para que seleccione los registros que necesita. Por ejemplo, para seleccionar todos los logs de difusión nuevos o actualizados (registros de entrega de perfiles):

   * En la **[!UICONTROL Properties]** ficha, cambie el recurso de destino a Registros **de** envío (wideLogRcp).

      ![](assets/export_logs_query_properties.png)

   * En la **[!UICONTROL Target]** ficha, establezca una condición para recuperar todos los registros de entrega que correspondan a envíos enviados en 2016 o después. For more information, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

      ![](assets/export_logs_query_target.png)

   * En la **[!UICONTROL Processed data]** ficha, seleccione **[!UICONTROL Use a date field]** y elija el campo **lastModified** . En las próximas ejecuciones del flujo de trabajo, solo se recuperarán los registros que se hayan modificado o creado después de la última ejecución.

      ![](assets/export_logs_query_processeddata.png)

      Después de la primera ejecución del flujo de trabajo, puede ver en esta ficha la última fecha de ejecución que se utilizará para la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

1. Agregue una **[!UICONTROL Extract file]** actividad que exportará los datos consultados en un archivo:

   * En la **[!UICONTROL Extraction]** ficha, especifique el nombre del archivo. Este nombre se completará automáticamente con la fecha de exportación para garantizar que todos los archivos extraídos sean únicos.

      Seleccione las columnas que desee exportar en el archivo. Puede seleccionar aquí los datos procedentes de recursos relacionados como, por ejemplo, información de perfil o de entrega. Para organizar el archivo final, puede aplicar una ordenación. Por ejemplo, en la fecha de registro, como se muestra en el ejemplo siguiente.

      ![](assets/export_logs_extractfile_extraction.png)

      >[!NOTE]
      >
      >No es posible exportar identificadores únicos (claves principales) de los recursos de registro.

   * En la **[!UICONTROL File structure]** ficha, defina el formato del archivo de salida para que coincida con sus necesidades.

      Marque la **[!UICONTROL Export labels instead of internal values of enumerations]** opción en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas que son fáciles de entender en lugar de identificadores.

1. Agregue una **[!UICONTROL Transfer file]** actividad y configúrela para transferir el archivo recién creado del servidor de Adobe Campaign a otra ubicación a la que pueda acceder, como un servidor SFTP.

   * En la **[!UICONTROL General]** ficha, seleccione **[!UICONTROL File upload]** como objetivo enviar el archivo de Adobe Campaign a otro servidor.
   * En la **[!UICONTROL Protocol]** ficha, especifique los parámetros de transferencia y seleccione la cuenta [](../../administration/using/external-accounts.md#creating-an-external-account) externa que desee utilizar.

1. Agregue una **[!UICONTROL End]** actividad para asegurarse de que termina correctamente y guarde el flujo de trabajo.

   ![](assets/export_logs_example_workflow.png)

Ahora puede ejecutar el flujo de trabajo y recuperar el archivo de salida en el servidor externo.

**Tema relacionado:**

[Flujos de trabajo](../../automating/using/discovering-workflows.md)
