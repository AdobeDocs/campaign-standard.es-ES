---
title: Creación de audiencias
description: Aprenda a crear audiencias en Adobe Campaign.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: readAudience,main;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: b40e4f6f-34bb-40f9-80e8-e9f1bce5548c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 98%

---

# Creación de audiencias{#creating-audiences}

## Creación de audiencias de consulta {#creating-query-audiences}

En esta sección se describe cómo crear una audiencia de **Consulta** . También puede crear audiencias importando un archivo o segmentando en un [flujo de trabajo](../../automating/using/get-started-workflows.md).

Desde la lista de audiencia, puede crear audiencias realizando consultas en perfiles de Adobe Campaign o importando una audiencia de Adobe Experience Cloud.

1. Vaya a la lista de audiencia mediante la tarjeta o pestaña **[!UICONTROL Audiences]**.

   ![](assets/audiences_query_1.png)

1. Seleccione **[!UICONTROL Create]** para acceder a la pantalla y crear una nueva audiencia.

   ![](assets/audiences_query.png)

1. Asigne un nombre a la audiencia. La etiqueta de audiencia se utiliza en la lista de audiencias y en la paleta de la herramienta consulta.
1. Elija un tipo de audiencia de **[!UICONTROL Query]**: las audiencias definidas por una consulta se recomiendan para cada uso posterior.

   ![](assets/audience_type_selection.png)

1. A continuación, seleccione la **[!UICONTROL Targeting dimension]** que desee utilizar para filtrar a sus clientes. Cada audiencia está formada por una sola dimensión de segmentación. Por ejemplo, no se puede crear una audiencia compuesta por perfiles, perfiles de prueba y suscriptores. Para obtener más información sobre las dimensiones de segmentación, consulte [esta página](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Cree la consulta para definir la población de audiencias. Consulte la sección sobre [edición de consultas](../../automating/using/editing-queries.md).
1. Haga clic en el botón **[!UICONTROL Create]** para guardar la audiencia.

>[!NOTE]
>
>Puede agregar una descripción a esta audiencia y definir las autorizaciones de acceso mediante el icono **[!UICONTROL Edit properties]**.

## Creación de audiencias de lista {#creating-list-audiences}

En esta sección se describe cómo crear una audiencia de **Lista** después de segmentar en un flujo de trabajo. También puede crear audiencias importando un archivo en un [flujo de trabajo](../../automating/using/get-started-workflows.md) o mediante una consulta desde el menú **[!UICONTROL Audiences]**.

Para crear una audiencia de **Lista**, los pasos son los siguientes:

1. En la pestaña **Marketing activities**, haga clic en **Create** y seleccione **Workflow**.

   ![](assets/audiences_list_1.png)

1. Arrastre y suelte y, a continuación, configure las actividades de segmentación que le permitirán seleccionar una población que tenga una dimensión **conocida**. La lista de las actividades disponibles y su configuración se detallan en la sección [Actividades de segmentación](../../automating/using/about-targeting-activities.md).

   Puede utilizar una actividad **[!UICONTROL Query]** o importar datos mediante una actividad **[!UICONTROL Load file]** antes de utilizar una actividad **[!UICONTROL Reconciliation]** para identificar la dimensión de los datos importados. Aquí, queremos segmentar a los destinatarios que se suscribieron al Sport Newsletter con una actividad **[!UICONTROL Query]**.

   ![](assets/audiences_list_2.png)

1. Después del objetivo, arrastre y suelte una actividad **[!UICONTROL Save audience]** en el flujo de trabajo. Por ejemplo, puede elegir **[!UICONTROL Create or update an audience]**, lo que le permite crear y actualizar automáticamente su audiencia con nuevos datos. En este caso, agregue una actividad **[!UICONTROL Scheduler]** al principio del flujo de trabajo.

   Para obtener más información sobre la configuración de esta actividad, consulte la sección [Guardar audiencia](../../automating/using/save-audience.md) .

   ![](assets/audiences_list_3.png)

1. Guarde e inicie el flujo de trabajo.

   Como **[!UICONTROL Save audience]** se coloca después de un objetivo con una dimensión conocida, las audiencias creadas mediante esta actividad son audiencias de **Lista** .

   El contenido de la audiencia guardada está disponible en la vista detallada de la audiencia, a la que se puede acceder mediante la lista de audiencias. Las columnas disponibles en esta vista corresponden a las columnas de la transición de entrada de la actividad de guardado del flujo de trabajo. Por ejemplo: las columnas del archivo importado, los datos adicionales agregados desde una consulta.

   ![](assets/audiences_list_4.png)

## Creación de audiencias de archivo {#creating-file-audiences}

En esta sección se explica cómo crear una audiencia de **Archivo** mediante la importación de un archivo en un flujo de trabajo. También puede crear audiencias a partir de una actividad de segmentación en un [flujo de trabajo](../../automating/using/get-started-workflows.md) o mediante una consulta desde el menú **[!UICONTROL Audiences]**.

Para crear una audiencia de **Archivo**, los pasos son los siguientes:

1. En la pestaña **Marketing activities**, haga clic en **Create** y seleccione **Workflow**.
1. Arrastre y suelte y, a continuación, configure una actividad **[!UICONTROL Load file]** que le permitirá importar una población que tenga una dimensión **desconocida** cuando se ejecute el flujo de trabajo. Para obtener más información sobre la configuración de esta actividad, consulte la sección [Cargar archivo ](../../automating/using/load-file.md) .

   ![](assets/audience_files_1.png)

1. Arrastre y suelte una actividad **[!UICONTROL Save audience]** después de su actividad de **[!UICONTROL Load file]**. Para obtener más información sobre la configuración de esta actividad, consulte la sección [Guardar audiencia](../../automating/using/save-audience.md) .
1. Guarde e inicie el flujo de trabajo.

   ![](assets/audience_files_2.png)

   Como el **[!UICONTROL Save audience]** se coloca después de una importación, la dimensión de datos es desconocida y las audiencias creadas mediante esta actividad son audiencias de **Archivo** .

   El contenido de la audiencia guardada está disponible en la vista detallada de la audiencia, a la que se puede acceder mediante la lista de audiencias. Las columnas disponibles en esta vista corresponden a las columnas de la transición de entrada de la actividad de guardado del flujo de trabajo. Por ejemplo, las columnas del archivo importado o los datos adicionales añadidos desde una consulta.

   ![](assets/audience_files_3.png)

## Creación de audiencias de Experience Cloud {#creating-experience-cloud-audiences}

Adobe Campaign le permite compartir e intercambiar audiencias con Adobe Experience Cloud. Una audiencia de tipo **Experience Cloud** se importa directamente del servicio principal Personas a Adobe Campaign con el flujo de trabajo técnico **[!UICONTROL Import shared audience]**.

A diferencia de la audiencia de tipo **Consulta** que hará consulta de perfiles desde Adobe Campaign, la audiencia de **Experience Cloud** está compuesta por una lista de ID de visitante.

Para que esta integración funcione, primero debe configurarla. Para obtener más información sobre la configuración y cómo importar o exportar audiencias con el servicio principal Personas, consulte la siguiente [sección](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

![](assets/audience_peoplecore.png)

## Edición de audiencias {#editing-audiences}

Existen diferentes formas de editar una audiencia según el tipo de audiencia:

* Para editar una audiencia de **Consulta**, vaya a la lista de audiencias a través del menú **[!UICONTROL Audiences]** o la tarjeta **[!UICONTROL Audiences]** desde la página de inicio de Adobe Campaign.

  Abra la audiencia pertinente. Se pueden editar todos los elementos de una audiencia creada previamente.

  >[!CAUTION]
  >
  >Si cambia la **[!UICONTROL Filtering dimension]** en la consulta, se perderán las reglas que se hayan definido previamente.

* Para editar una audiencia de **Lista** o una audiencia de **Archivo**, edite el flujo de trabajo desde el que se creó y modifique la actividad **[!UICONTROL Save audience]**. Inicio el flujo de trabajo para modificar la audiencia.
* Para editar una audiencia de **Experience Cloud** , consulte la sección [Importación/exportación de audiencias con el servicio principal Personas](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md).

## Eliminación de audiencias {#deleting-audiences}

Existen dos formas de eliminar una o varias audiencias. Primero puede agregar una fecha de vencimiento a la audiencia

Para ello:

1. Acceda a una de sus audiencias.
1. Haga clic en el botón ![](assets/edit_darkgrey-24px.png) para acceder a la configuración de la audiencia.

   ![](assets/audience_delete_2.png)

1. En el campo **[!UICONTROL Expires on]**, agregue una fecha de vencimiento a la audiencia.

   ![](assets/audience_delete_3.png)

1. Haga clic en **[!UICONTROL Confirm]**, luego en **[!UICONTROL Save]**.

La fecha de vencimiento ya estará configurada. En cuanto llegue la fecha, la audiencia se eliminará automáticamente.

Si necesita eliminar una audiencia, simplemente puede seleccionar una o varias audiencias y luego hacer clic en el botón **[!UICONTROL Delete element]**.

![](assets/audience_delete_1.png)
