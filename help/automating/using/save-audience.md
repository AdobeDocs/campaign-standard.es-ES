---
title: Guardar audiencia
description: La actividad Guardar audiencia le permite actualizar una audiencia existente o crear una nueva a partir de la población calculada en sentido ascendente en un flujo de trabajo.
page-status-flag: nunca activado
uuid: 8babb173-fa59-44a7-a2a5-49f45ba6bf99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 1f6bb048-7abd-499b-a4b0-187f9492dc47
context-tags: saveAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Guardar audiencia{#save-audience}

## Descripción {#description}

![](assets/save_audience.png)

La **[!UICONTROL Save audience]** actividad le permite actualizar una audiencia existente o crear una nueva a partir de la población calculada en sentido ascendente en un flujo de trabajo. Las audiencias creadas o actualizadas a partir de esta actividad son audiencias de **lista** o **archivo** . Se añaden a la lista de audiencias de la aplicación y están disponibles a través del **[!UICONTROL Audiences]** menú.

>[!NOTE]
>
>Si la audiencia creada a través de la **[!UICONTROL Save audience]** actividad se ha enriquecido con datos adicionales, no podrá utilizar estos datos para personalizar una entrega independiente. Solo se pueden usar desde una entrega ejecutada en un flujo de trabajo.

Esta actividad también le permite exportar perfiles como audiencias o segmentos de Adobe Experience Cloud. Esto le permite aprovechar estas audiencias en otras soluciones de Adobe Experience Cloud. Para obtener más información sobre las audiencias compartidas, consulte [Uso de Campaign y Servicio](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)principal de personas.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Save audience]** actividad se utiliza esencialmente para mantener los grupos de población calculados en el mismo flujo de trabajo, convirtiéndolos en audiencias reutilizables.

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Save audience]** actividad en el flujo de trabajo.
1. Conéctelo después de otras actividades de segmentación como una consulta, una intersección, una unión o una exclusión.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione la acción que desee realizar:

   * **[!UICONTROL Update an existing audience]**:: Seleccione una audiencia existente y elija el tipo de actualización:

      * **[!UICONTROL Replace audience content with new data]**:: Se reemplaza todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición entrante de la actividad de guardar audiencia.
      * **[!UICONTROL Complete audience with new data]**:: Se conservan los datos de audiencia anteriores y se agregan a ellos los datos de la transición de entrada de la actividad de audiencia guardada.
   * **[!UICONTROL Create then update an audience]**:: Introduzca el nombre de la audiencia y seleccione el tipo de actualización. Si la audiencia no existe, se crea. Si ya existe, se actualiza según el modo seleccionado:

      * **[!UICONTROL Replace audience content with new data]**:: Se reemplaza todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición entrante de la actividad de guardar audiencia.

         Advertencia, esta opción borra el tipo de audiencia y la dimensión de segmentación de la audiencia actualizada.

      * **[!UICONTROL Complete audience with new data]**:: Se conservan los datos de audiencia anteriores y se agregan a ellos los datos de la transición de entrada de la actividad de audiencia guardada.

         Advertencia, esta opción provoca un error si el tipo de audiencia o la dimensión de segmentación de la audiencia actualizada no son compatibles con la configuración actual del flujo de trabajo. Por ejemplo, no se puede completar una audiencia de tipo de archivo con perfiles procedentes de una consulta.
   * **[!UICONTROL Create a new audience]**:: Introduzca el nombre de la audiencia que desea crear. La hora y la fecha de creación de la audiencia se agregarán automáticamente al nombre de la audiencia. Esto hace que la audiencia sea única cada vez que se ejecuta el flujo de trabajo.
   * **[!UICONTROL Share in Adobe Experience Cloud]**:: Si tiene perfiles de objetivo y desea exportar su audiencia a Adobe Experience Cloud, seleccione esta opción y, a continuación, seleccione una audiencia compartida existente o cree una audiencia nueva.

      Seleccione también un elemento **[!UICONTROL Shared Data source]** que corresponda al recurso de los datos contenidos en la audiencia para que los datos se reconcilien correctamente en Adobe Experience Cloud.

      Con esta opción, la audiencia compartida no se agrega a la lista de audiencias de Adobe Campaign disponibles a través del **[!UICONTROL Audiences]** menú.

      >[!NOTE]
      >
      >Esta opción solo está disponible si el administrador ha configurado la funcionalidad de audiencias compartidas con Adobe Experience Cloud. Para obtener más información, consulte [Trabajo con Campaign y Servicio](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)principal de personas.
   El tipo de audiencias guardadas o disponibles durante una actualización depende de las actividades que se coloquen en el flujo de trabajo.

   Si se desconoce la dimensión de segmentación de la audiencia al guardarla (por ejemplo, si procede de un archivo importado), la audiencia se crea o actualiza como audiencia de **[!UICONTROL File]** tipo.

   Si la dimensión de objetivo de la audiencia guardada ya está definida cuando se guarda (por ejemplo, si procede de un objetivo, después de una consulta, etc.), la audiencia se guarda o actualiza como audiencia de **[!UICONTROL List]** tipo.

   El contenido de la audiencia guardada está disponible en la vista de detalles de la audiencia, a la que se puede acceder desde el **[!UICONTROL Audiences]** menú. Las columnas disponibles en esta vista corresponden a las columnas de la transición de entrada de la actividad de guardar audiencia del flujo de trabajo.  Por ejemplo: las columnas del archivo importado, los datos adicionales agregados a partir de una consulta.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El flujo de trabajo definido en este ejemplo muestra una actualización de audiencia regular desde la segmentación:

* Se ejecuta automáticamente una vez al mes mediante un **[!UICONTROL Scheduler]**.
* Puede utilizar un **[!UICONTROL Query]** para recuperar todos los perfiles suscritos a los diferentes servicios de aplicaciones disponibles.
* La **[!UICONTROL Save audience]** actividad actualiza la audiencia eliminando perfiles que se han cancelado de suscripción al servicio desde la última ejecución del flujo de trabajo y agregando los perfiles recién suscritos.

![](assets/save_audience_example_1.png)

La **[!UICONTROL Save audience]** actividad se configura de la siguiente manera:

![](assets/save_audience_example_2.png)

