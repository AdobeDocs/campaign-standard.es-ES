---
title: Creación de audiencias
description: Obtenga información sobre cómo crear audiencias en Adobe Campaign.
page-status-flag: nunca activado
uuid: fe99b31b-a949-4832-b0e6-2b36d1c8be80
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar-audiencias
discoiquuid: df8bdcfb-be5e-4044-bc26-aa3466accbbe
context-tags: readAudience,main;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación de audiencias{#creating-audiences}

## Creación de audiencias de consulta {#creating-query-audiences}

En esta sección se describe cómo crear una audiencia **de consulta** . También puede crear audiencias a partir de la importación de un archivo o la segmentación en un [flujo de trabajo](../../automating/using/discovering-workflows.md).

En la lista de audiencias, puede crear audiencias realizando consultas en los perfiles de Adobe Campaign o importando una audiencia de Adobe Experience Cloud.

1. Vaya a la lista de audiencias mediante la **[!UICONTROL Audiences]** ficha o la tarjeta.

   ![](assets/audiences_query_1.png)

1. Seleccione **[!UICONTROL Create]** para acceder a la pantalla y crear una audiencia nueva.

   ![](assets/audiences_query.png)

1. Asigne un nombre a la audiencia. La etiqueta de audiencia se utiliza en la lista de audiencias y en la paleta de la herramienta de consulta.
1. Elija un tipo **[!UICONTROL Query]** de audiencia: las audiencias definidas por una consulta se vuelven a calcular en cada uso posterior.

   ![](assets/audience_type_selection.png)

1. A continuación, seleccione el **[!UICONTROL Targeting dimension]** que desee utilizar para filtrar a sus clientes. Cada audiencia está formada por una sola dimensión de objetivo. Por ejemplo, no puede crear una audiencia compuesta por perfiles, perfiles de prueba y suscriptores. For more on targeting dimensions, refer to [this page](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Cree la consulta para definir la población de audiencias. Consulte la sección sobre [edición de consultas](../../automating/using/editing-queries.md).
1. Haga clic en el **[!UICONTROL Create]** botón para guardar la audiencia.

>[!NOTE]
>
>Puede agregar una descripción a esta audiencia y definir las autorizaciones de acceso mediante el **[!UICONTROL Edit properties]** icono .

## Creación de audiencias de lista {#creating-list-audiences}

En esta sección se describe cómo crear una audiencia de **lista** después de segmentar en un flujo de trabajo. También puede crear audiencias importando un archivo en un [flujo de trabajo](../../automating/using/discovering-workflows.md) o mediante una consulta desde el **[!UICONTROL Audiences]** menú.

To create a **List** audience, the steps are as follows:

1. En la ficha Actividades **** de marketing, haga clic en **Crear** y, a continuación, seleccione **Flujo de trabajo**.

   ![](assets/audiences_list_1.png)

1. Arrastre y suelte y, a continuación, configure las actividades de segmentación que le permitirán seleccionar una población que tenga una dimensión **conocida** . La lista de actividades disponibles y su configuración se detallan en la sección Actividades [de](../../automating/using/about-targeting-activities.md) establecimiento de objetivos.

   Puede utilizar una **[!UICONTROL Query]** actividad o importar datos mediante una **[!UICONTROL Load file]** actividad antes de utilizar una **[!UICONTROL Reconciliation]** actividad para identificar la dimensión de los datos importados. Aquí, queremos dirigirse a los destinatarios que se suscribieron al boletín deportivo con una **[!UICONTROL Query]** actividad.

   ![](assets/audiences_list_2.png)

1. Después de definir el objetivo, arrastre y suelte una **[!UICONTROL Save audience]** actividad en el flujo de trabajo. Por ejemplo, puede elegir **[!UICONTROL Create or update an audience]**, lo que le permite crear y actualizar automáticamente su audiencia con nuevos datos. En este caso, agregue una **[!UICONTROL Scheduler]** actividad al principio del flujo de trabajo.

   Para obtener más información sobre la configuración de esta actividad, consulte la sección [Guardar audiencia](../../automating/using/save-audience.md) .

   ![](assets/audiences_list_3.png)

1. Guarde e inicie el flujo de trabajo.

   Como el **[!UICONTROL Save audience]** se coloca después de un objetivo con una dimensión conocida, las audiencias creadas mediante esta actividad son audiencias de **lista** .

   El contenido de la audiencia guardada está disponible en la vista detallada de la audiencia a la que se puede acceder mediante la lista de audiencias. Las columnas disponibles en esta vista corresponden a las columnas de la transición de entrada de la actividad de guardado del flujo de trabajo.  Por ejemplo: las columnas del archivo importado, los datos adicionales agregados a partir de una consulta.

   ![](assets/audiences_list_4.png)

## Creación de audiencias de archivos {#creating-file-audiences}

En esta sección se explica cómo crear una audiencia de **archivos** mediante la importación de un archivo en un flujo de trabajo. También puede crear audiencias a partir de una actividad de segmentación en un [flujo de trabajo](../../automating/using/discovering-workflows.md) o mediante una consulta desde el **[!UICONTROL Audiences]** menú.

To create a **File** audience, the steps are as follows:

1. En la ficha Actividades **** de marketing, haga clic en **Crear** y, a continuación, seleccione **Flujo de trabajo**.
1. Arrastre y suelte y, a continuación, configure una **[!UICONTROL Load file]** actividad que le permitirá importar una población que tenga una dimensión **desconocida** cuando se ejecute el flujo de trabajo. Para obtener más información sobre la configuración de esta actividad, consulte la sección [Cargar archivo](../../automating/using/load-file.md) .

   ![](assets/audience_files_1.png)

1. Arrastre y suelte una **[!UICONTROL Save audience]** actividad después de la **[!UICONTROL Load file]** actividad. Para obtener más información sobre la configuración de esta actividad, consulte la sección [Guardar audiencia](../../automating/using/save-audience.md) .
1. Guarde e inicie el flujo de trabajo.

   ![](assets/audience_files_2.png)

   Dado que el **[!UICONTROL Save audience]** se coloca después de una importación, la dimensión de datos es desconocida y las audiencias creadas mediante esta actividad son audiencias de **archivo** .

   El contenido de la audiencia guardada está disponible en la vista detallada de la audiencia a la que se puede acceder mediante la lista de audiencias. Las columnas disponibles en esta vista corresponden a las columnas de la transición de entrada de la actividad de guardado del flujo de trabajo.  Por ejemplo: las columnas del archivo importado, los datos adicionales agregados a partir de una consulta.

   ![](assets/audience_files_3.png)

## Creación de audiencias de Experience Cloud {#creating-experience-cloud-audiences}

Adobe Campaign permite compartir e intercambiar audiencias con Adobe Experience Cloud. Una audiencia de tipo **Experience Cloud** se importa directamente del servicio principal Personas a Adobe Campaign con el flujo de trabajo **[!UICONTROL Import shared audience]** técnico.

A diferencia de la audiencia de tipo **Consulta** que consultará perfiles de Adobe Campaign, la audiencia de **Experience Cloud** está compuesta por una lista de ID de visitante.

Para que esta integración funcione, primero debe configurarla. Para obtener más información sobre la configuración y cómo importar o exportar audiencias con el servicio principal Personas, consulte la siguiente [sección](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Edición de audiencias {#editing-audiences}

Existen diferentes formas de editar una audiencia en función del tipo de audiencia:

* Para editar una audiencia de **consulta** , vaya a la lista de audiencias mediante el **[!UICONTROL Audiences]** menú o la **[!UICONTROL Audiences]** tarjeta de la página principal de Adobe Campaign.

   Abra la audiencia relevante. Se pueden editar todos los elementos de una audiencia creada previamente.

   >[!CAUTION]
   >
   >Si cambia el **[!UICONTROL Filtering dimension]** en la consulta, se perderán las reglas que se hayan definido previamente.

* Para editar una audiencia de **lista** o **archivo** , edite el flujo de trabajo desde el que se creó y modifique la **[!UICONTROL Save audience]** actividad. Inicie el flujo de trabajo para modificar la audiencia.
* Para editar una audiencia de **Experience Cloud** , consulte la sección del servicio [](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md) principal Personas que importa o exporta audiencias.

## Eliminación de audiencias {#deleting-audiences}

Existen dos formas de eliminar una o varias audiencias. Primero puede agregar una fecha de caducidad a la audiencia

Para ello:

1. Acceda a una audiencia.
1. Haga clic en el ![](assets/edit_darkgrey-24px.png) botón para acceder a la configuración de la audiencia.

   ![](assets/audience_delete_2.png)

1. En el **[!UICONTROL Expires on]** campo, agregue una fecha de caducidad a la audiencia.

   ![](assets/audience_delete_3.png)

1. Haga clic en **[!UICONTROL Confirm]** luego **[!UICONTROL Save]**.

La fecha de caducidad ya está configurada. Tan pronto como se llegue a esta fecha, la audiencia se eliminará automáticamente.

O bien, si necesita eliminar una audiencia, puede simplemente seleccionar una o varias audiencias y luego hacer clic en el **[!UICONTROL Delete element]** botón.

![](assets/audience_delete_1.png)

