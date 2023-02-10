---
title: Guardar audiencia
description: La actividad Guardar audiencia le permite actualizar una audiencia existente o crear una nueva a partir de la población calculada en sentido ascendente en un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 100%

---

# Guardado de audiencia{#save-audience}

## Descripción {#description}

![](assets/save_audience.png)

La actividad **[!UICONTROL Save audience]** le permite actualizar una audiencia existente o crear una nueva a partir de la población calculada en sentido ascendente en un flujo de trabajo. Las audiencias creadas o actualizadas a partir de esta actividad son audiencias de **lista** o **archivo**. Se añaden a la lista de audiencias de aplicación y están disponibles en el menú **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Si la audiencia creada con la actividad **[!UICONTROL Save audience]** se ha enriquecido con datos adicionales, no puede utilizar estos datos para personalizar un envío independiente. Solo se pueden usar desde un envío ejecutado en un flujo de trabajo.

Esta actividad también le permite exportar perfiles como audiencias o segmentos de Adobe Experience Cloud. Esto le permite aprovechar estas audiencias en otras soluciones de Adobe Experience Cloud. Para obtener más información sobre audiencias compartidas, consulte [Trabajar con Campaign y el servicio principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Save audience]** se utiliza esencialmente para mantener los grupos de población calculados en el mismo flujo de trabajo, convirtiéndolos en audiencias reutilizables.

## Configuración {#configuration}

1. Coloque una actividad **[!UICONTROL Save audience]** en el flujo de trabajo.
1. Conéctelo después de otras actividades de segmentación, como una consulta, una intersección, una unión o una exclusión.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione la acción que desee realizar:

   * **[!UICONTROL Update an existing audience]**: seleccione una audiencia existente y elija el tipo de actualización:

      * **[!UICONTROL Replace audience content with new data]**: reemplace todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición de entrada de la actividad Guardar audiencia.
      * **[!UICONTROL Complete audience with new data]**: los datos de audiencia anteriores se conservan y se añaden a ellos los datos de la transición de entrada de la actividad Guardar audiencia.
   * **[!UICONTROL Create then update an audience]**: introduzca el nombre de la audiencia y seleccione el tipo de actualización. Si la audiencia no existe, se crea. Si ya existe, se actualiza según el modo seleccionado:

      * **[!UICONTROL Replace audience content with new data]**: reemplace todo el contenido de la audiencia. Se pierden los datos antiguos. Solo se conservan los datos de la transición de entrada de la actividad Guardar audiencia.

         Advertencia, esta opción borra el tipo de audiencia y la dimensión de segmentación de la audiencia actualizada.

      * **[!UICONTROL Complete audience with new data]**: los datos de audiencia anteriores se conservan y se añaden a ellos los datos de la transición de entrada de la actividad Guardar audiencia.

         Advertencia: Esta opción provoca un error si el tipo de audiencia o la dimensión de segmentación de la audiencia actualizada no son compatibles con la configuración actual del flujo de trabajo. Por ejemplo, no se puede completar una audiencia de tipo de archivo con perfiles procedentes de una consulta.
   * **[!UICONTROL Create a new audience]**: introduzca el nombre de la audiencia que va a crear. La hora y la fecha de creación de la audiencia se añaden automáticamente al nombre. Esto hace que la audiencia sea única cada vez que se ejecuta el flujo de trabajo.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: si tiene perfiles objetivo y desea exportar la audiencia a Adobe Experience Cloud, seleccione esta opción y, a continuación, seleccione una audiencia compartida existente o cree una nueva.

      Seleccione también una **[!UICONTROL Shared Data source]** que corresponda al recurso de los datos contenidos en la audiencia para que los datos cuadren en Adobe Experience Cloud.

      Con esta opción, la audiencia compartida no se añade a la lista de audiencias de Adobe Campaign disponible en el menú **[!UICONTROL Audiences]**.

      >[!NOTE]
      >
      >Esta opción solo está disponible si el administrador ha configurado la funcionalidad de audiencias compartidas con Adobe Experience Cloud. Para obtener más información, consulte [Trabajar con Campaign y el servicio principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

   El tipo de audiencias guardadas o disponibles durante una actualización depende de las actividades que se coloquen en el flujo de trabajo.

   Si la dimensión de segmentación de la audiencia es desconocida cuando se guarda (por ejemplo, si procede de un archivo importado), la audiencia se crea o se actualiza como una audiencia de tipo **[!UICONTROL File]**.

   Si la dimensión de segmentación de la audiencia guardada ya está definida cuando se guarda (por ejemplo, si procede de una segmentación, después de una consulta, etc.), la audiencia se guarda o actualiza como una audiencia de tipo **[!UICONTROL List]**.

   El contenido de la audiencia guardada está disponible en la vista de detalles de la audiencia, a la que se puede acceder desde el menú **[!UICONTROL Audiences]**. Las columnas disponibles en esta vista corresponden a las de la transición de entrada de la actividad Guardar audiencia del flujo de trabajo. Por ejemplo, las columnas del archivo importado o los datos adicionales añadidos desde una consulta.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El flujo de trabajo definido en este ejemplo muestra una actualización de audiencia normal desde la segmentación:

* Se ejecuta automáticamente una vez al mes mediante un **[!UICONTROL Scheduler]**.
* Puede utilizar una **[!UICONTROL Query]** para recuperar todos los perfiles suscritos a los diferentes servicios de aplicaciones disponibles.
* La actividad **[!UICONTROL Save audience]** actualiza la audiencia eliminando perfiles que han dejado de suscribirse al servicio desde la última ejecución del flujo de trabajo y añadiendo los perfiles recién suscritos.

![](assets/save_audience_example_1.png)

La actividad **[!UICONTROL Save audience]** se configura de la siguiente manera:

![](assets/save_audience_example_2.png)
