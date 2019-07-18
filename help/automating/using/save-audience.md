---
title: Guardar audiencia
seo-title: Guardar audiencia
description: Guardar audiencia
seo-description: La actividad Guardar audiencia permite actualizar una audiencia existente o crear una audiencia nueva desde la población calculada hacia arriba en un flujo de trabajo.
page-status-flag: no activado nunca
uuid: 8 babb 173-fa 59-44 a 7-a 2 a 5-49 f 45 ba 6 bf 99
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 1 f 6 bb 048-7 abd -499 b-a 4 b 0-187 f 9492 dc 47
context-tags: Saveaudience, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Save audience{#save-audience}

## Description {#description}

![](assets/save_audience.png)

The **[!UICONTROL Save audience]** activity allows you to update an existing audience or create a new audience from the population computed upstream in a workflow. The audiences created or updated from this activity are **List** or **File** audiences. They are added to the list of application audiences, and are made available via the **[!UICONTROL Audiences]** menu.

>[!NOTE]
>
>If the audience created through the **[!UICONTROL Save audience]** activity has been enriched with additional data, you will not be able to use these data to personalize a standalone delivery. Solo se pueden utilizar desde una entrega ejecutada en un flujo de trabajo.

Esta actividad también permite exportar perfiles como audiencias/segmentos de Adobe Experience Cloud. Esto le permite aprovechar estas audiencias en otras soluciones de Adobe Experience Cloud. For more information about shared audiences, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Context of use {#context-of-use}

The **[!UICONTROL Save audience]** activity is essentially used to keep population groups computed in the same workflow, by converting them into reusable audiences.

## Configuration {#configuration}

1. Drop a **[!UICONTROL Save audience]** activity into your workflow.
1. Conéctela después de otras actividades de segmentación, como una consulta, una intersección, una unión o una exclusión.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Seleccione la acción que desee llevar a cabo:

   * **[!UICONTROL Update an existing audience]**: Seleccione una audiencia existente y elija el tipo de actualización:

      * **[!UICONTROL Replace audience content with new data]**: Se reemplazará todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición entrante de la actividad de guardar audiencia.
      * **[!UICONTROL Complete audience with new data]**: Se conservan los datos antiguos de audiencia y se agregan los datos de la transición de entrada de la actividad de la audiencia de guardado.
   * **[!UICONTROL Create then update an audience]**: Introduzca el nombre de la audiencia y seleccione el tipo de actualización. Si la audiencia no existe, entonces se crea. Si ya existe, se actualiza según el modo seleccionado:

      * **[!UICONTROL Replace audience content with new data]**: Se reemplazará todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición entrante de la actividad de guardar audiencia.

         Advertencia, esta opción borra el tipo de audiencia y la dimensión de objetivo de la audiencia actualizada.

      * **[!UICONTROL Complete audience with new data]**: Se conservan los datos antiguos de audiencia y se agregan los datos de la transición de entrada de la actividad de la audiencia de guardado.

         Advertencia, esta opción genera un error si el tipo de audiencia o la dimensión de objetivo de la audiencia actualizada no son compatibles con la configuración actual del flujo de trabajo. Por ejemplo, no se puede completar una audiencia de tipo de archivo con perfiles procedentes de una consulta.
   * **[!UICONTROL Create a new audience]**: Escriba el nombre de la audiencia que desee crear. La hora y la fecha de creación de la audiencia se agregarán automáticamente al nombre de la audiencia. Esto hace que la audiencia sea única cada vez que se ejecuta el flujo de trabajo.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: Si tiene perfiles de objetivo y desea exportar su audiencia a Adobe Experience Cloud, seleccione esta opción y, a continuación, seleccione una audiencia compartida existente o cree una nueva.

      Also select a **[!UICONTROL Shared Data source]** that corresponds to the resource of the data contained in the audience so that the data is correctly reconciled in Adobe Experience Cloud.

      Using this option, the shared audience is not added to the list of Adobe Campaign audiences available via the **[!UICONTROL Audiences]** menu.

      >[!NOTE]
      >
      >Esta opción solo está disponible si su administrador ha configurado la funcionalidad de audiencias compartidas con Adobe Experience Cloud. For more information, refer to [Working with Campaign and People Core Service](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).
   El tipo de audiencias guardadas o disponibles durante una actualización depende de las actividades colocadas en el flujo de trabajo.

   If the targeting dimension of the audience is unknown when it is saved (for example if it is from an imported file), the audience is created or updated as a **[!UICONTROL File]** type audience.

   If the targeting dimension of the saved audience is already defined when it is saved (for example, if it comes from a targeting, after a query, etc.), then the audience is saved or updated as a **[!UICONTROL List]** type audience.

   The content of the saved audience is then available in the detail view of the audience, which can be accessed from the **[!UICONTROL Audiences]** menu. Las columnas disponibles en esta vista corresponden a las columnas de la transición entrante de la actividad de audiencia guardada del flujo de trabajo. Por ejemplo: las columnas del archivo importado, los datos adicionales agregados de una consulta.

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

El flujo de trabajo definido en este ejemplo muestra una actualización de audiencia normal desde la segmentación:

* It is automatically executed once a month using a **[!UICONTROL Scheduler]**.
* You can use a **[!UICONTROL Query]** to recover all the profiles subscribed to the different application services available.
* **[!UICONTROL Save audience]** La actividad actualiza la audiencia eliminando perfiles que se han cancelado la suscripción del servicio desde la última ejecución del flujo de trabajo y añadiendo los perfiles recién suscritos.

![](assets/save_audience_example_1.png)

**[!UICONTROL Save audience]** La actividad se configura de la siguiente manera:

![](assets/save_audience_example_2.png)

