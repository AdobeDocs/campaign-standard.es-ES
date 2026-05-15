---
title: Exportación de registros
description: Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar a través de un flujo de trabajo sencillo.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: d74e2a2c-3ce1-44d6-a058-67b0600360ca
TQID: https://experienceleague.adobe.com/Xu174CF9RsD4nhFs6KBm0TzsHFnuiBJgnHgK6-r5cI0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080bid: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 599
ht-degree: 14%

---

# Exportación de registros{#exporting-logs}

Los datos de registro, tanto si están relacionados con envíos como con suscripciones, se pueden exportar a través de un flujo de trabajo sencillo. Permite analizar los resultados de las campañas en su propia herramienta de creación de informes o inteligencia de negocios.

>[!CAUTION]
>
>Solo los [administradores](../../administration/using/users-management.md#functional-administrators) funcionales con el rol **[!UICONTROL Administration]** y acceso a las unidades **All** pueden acceder a los registros de envío, los registros de mensajes, los registros de seguimiento y los registros de exclusión o suscripción. Un usuario no administrador puede dirigirse a estos registros empezando por una tabla vinculada (perfiles, envío).

Utilizando un(a) **[!UICONTROL Incremental query]** que solo recupera nuevos registros cada vez que se ejecuta el flujo de trabajo y una simple actividad **[!UICONTROL Extract file]** para definir las columnas de salida, puede obtener un archivo con el formato y todos los datos que necesite. A continuación, utilice una actividad **[!UICONTROL Transfer file]** para recuperar el archivo final. Cada ejecución de flujo de trabajo está planificada por un **[!UICONTROL Scheduler]**.

La operación de exportación de registros la pueden realizar los usuarios estándar. Solo un administrador funcional puede administrar recursos privados como: broadlogs, registros de seguimiento, registros de exclusión, registros de suscripción y registros de historial de suscripción en **Perfiles**.

1. Cree un nuevo flujo de trabajo como se detalla en [esta sección](../../automating/using/building-a-workflow.md#creating-a-workflow).
1. Agregue una actividad **[!UICONTROL Scheduler]** y configúrela según sus necesidades. A continuación se muestra un ejemplo de una ejecución mensual.

   ![](assets/export_logs_scheduler.png)

1. Agregue una actividad **[!UICONTROL Incremental query]** y configúrela para que seleccione los registros que necesite. Por ejemplo, para seleccionar todos los broadlogs nuevos o actualizados (registros de envío de perfil):

   * En la ficha **[!UICONTROL Properties]**, cambie el recurso de destino a **Registros de envío** (broadLogRcp).

     ![](assets/export_logs_query_properties.png)

   * En la pestaña **[!UICONTROL Target]**, establezca una condición para recuperar todos los registros de envío que correspondan a envíos realizados en 2016 o posterior. Para obtener más información, consulte la sección [Edición de consultas](../../automating/using/editing-queries.md#creating-queries).

     ![](assets/export_logs_query_target.png)

   * En la ficha **[!UICONTROL Processed data]**, seleccione **[!UICONTROL Use a date field]** y elija el campo **lastModified**. En las siguientes ejecuciones del flujo de trabajo, solo se recuperan los registros que se hayan modificado o creado después de la última ejecución.

     ![](assets/export_logs_query_processeddata.png)

     Después de la primera ejecución del flujo de trabajo, puede ver en esta pestaña la última fecha de ejecución que se utiliza en la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.

1. Agregue una actividad **[!UICONTROL Extract file]** que exportará los datos consultados en un archivo:

   * En la ficha **[!UICONTROL Extraction]**, especifique el nombre del archivo.

     Si selecciona la opción **[!UICONTROL Add date and time to the file name]**, este nombre se completará automáticamente con la fecha de la exportación para garantizar que todos los archivos extraídos sean únicos. Seleccione las columnas que desea exportar en el archivo. Puede seleccionar aquí datos procedentes de recursos relacionados, como información de envío o de perfil.

     >[!NOTE]
     >
     >Para exportar un identificador único para cada registro, seleccione el elemento **[!UICONTROL Delivery log ID]**.

     Para organizar el archivo final, puede aplicar una ordenación. Por ejemplo, en la fecha de registro, como se muestra en el ejemplo siguiente.

     ![](assets/export_logs_extractfile_extraction.png)

   * En la ficha **[!UICONTROL File structure]**, defina el formato del archivo de salida para que coincida con sus necesidades.

     Marque la opción **[!UICONTROL Export labels instead of internal values of enumerations]** en caso de exportar valores de enumeración. Esta opción permite recuperar etiquetas más cortas, que son fáciles de entender, en lugar de identificadores.

1. Agregue una actividad **[!UICONTROL Transfer file]** y configúrela para transferir el archivo recién creado del servidor de Adobe Campaign a otra ubicación donde pueda acceder, como un servidor SFTP.

   * En la ficha **[!UICONTROL General]**, seleccione **[!UICONTROL File upload]**, ya que el propósito es enviar el archivo de Adobe Campaign a otro servidor.
   * En la ficha **[!UICONTROL Protocol]**, especifique los parámetros de transferencia y seleccione la [cuenta externa](../../administration/using/external-accounts.md#creating-an-external-account) que desea utilizar.

1. Agregue una actividad **[!UICONTROL End]** para asegurarse de que finaliza correctamente y guarde el flujo de trabajo.

   ![](assets/export_logs_example_workflow.png)

Ahora puede ejecutar el flujo de trabajo y recuperar el archivo de salida en el servidor externo.

**Temas relacionados:**

[Flujos de trabajo](../../automating/using/get-started-workflows.md)
