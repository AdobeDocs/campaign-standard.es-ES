---
title: Guardar público
description: La actividad Guardar público le permite actualizar un público existente o crear uno nuevo a partir de la población calculada en sentido ascendente en un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: saveAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c3f029d7-779e-47e7-a925-1e8f672da4dd
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 99%

---

# Guardado de público{#save-audience}

## Descripción {#description}

![](assets/save_audience.png)

La actividad **[!UICONTROL Save audience]** le permite actualizar un público existente o crear uno nuevo a partir de la población calculada en sentido ascendente en un flujo de trabajo. Los públicos creados o actualizadas a partir de esta actividad son públicos de **lista** o **archivo**. Se añaden a la lista de públicos de aplicación y están disponibles en el menú **[!UICONTROL Audiences]**.

>[!NOTE]
>
>Si el público creado con la actividad **[!UICONTROL Save audience]** se ha enriquecido con datos adicionales, no puede utilizar estos datos para personalizar un envío independiente. Solo se pueden usar desde un envío ejecutado en un flujo de trabajo.

Esta actividad también le permite exportar perfiles como audiencias o segmentos de Adobe Experience Cloud. Esto le permite aprovechar estos públicos en otras soluciones de Adobe Experience Cloud. Para obtener más información sobre públicos compartidos, consulte [Trabajar con Campaign y el servicio principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Save audience]** se utiliza esencialmente para mantener los grupos de población calculados en el mismo flujo de trabajo, convirtiéndolos en públicos reutilizables.

## Configuración {#configuration}

1. Coloque una actividad **[!UICONTROL Save audience]** en el flujo de trabajo.
1. Conéctelo después de otras actividades de segmentación, como una consulta, una intersección, una unión o una exclusión.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione la acción que desee realizar:

   * **[!UICONTROL Update an existing audience]**: seleccione un público existente y elija el tipo de actualización:

      * **[!UICONTROL Replace audience content with new data]**: reemplace todo el contenido del público. Se pierden los datos antiguos. Solo se conservan los datos de la transición de entrada de la actividad Guardar público.
      * **[!UICONTROL Complete audience with new data]**: los datos de público anteriores se conservan y se añaden a ellos los datos de la transición de entrada de la actividad Guardar público.

   * **[!UICONTROL Create then update an audience]**: introduzca el nombre del público y seleccione el tipo de actualización. Si el público no existe, se crea. Si ya existe, se actualiza según el modo seleccionado:

      * **[!UICONTROL Replace audience content with new data]**: reemplace todo el contenido del público. Se pierden los datos antiguos. Solo se conservan los datos de la transición de entrada de la actividad Guardar público.

        Advertencia, esta opción borra el tipo de público y la dimensión de segmentación del público actualizado.

      * **[!UICONTROL Complete audience with new data]**: los datos de público anteriores se conservan y se añaden a ellos los datos de la transición de entrada de la actividad Guardar público.

        Advertencia: Esta opción provoca un error si el tipo de público o la dimensión de segmentación del público actualizado no son compatibles con la configuración actual del flujo de trabajo. Por ejemplo, no se puede completar un público de tipo de archivo con perfiles procedentes de una consulta.

   * **[!UICONTROL Create a new audience]**: introduzca el nombre del público que va a crear. La hora y la fecha de creación del público se añaden automáticamente al nombre. Esto hace que el público sea único cada vez que se ejecuta el flujo de trabajo.
   * **[!UICONTROL Share in Adobe Experience Cloud]**: si tiene perfiles objetivo y desea exportar el público a Adobe Experience Cloud, seleccione esta opción y, a continuación, seleccione un público compartido existente o cree uno nuevo.

     Seleccione también una **[!UICONTROL Shared Data source]** que corresponda al recurso de los datos contenidos en el público para que los datos se reconcilien correctamente en Adobe Experience Cloud.

     Con esta opción, el público compartido no se añade a la lista de públicos de Adobe Campaign disponible en el menú **[!UICONTROL Audiences]**.

     >[!NOTE]
     >
     >Esta opción solo está disponible si el administrador ha configurado la funcionalidad de públicos compartidos con Adobe Experience Cloud. Para obtener más información, consulte [Trabajar con Campaign y el servicio principal People](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md).

   El tipo de públicos guardados o disponibles durante una actualización depende de las actividades que se coloquen en el flujo de trabajo.

   Si la dimensión de segmentación del público es desconocida cuando se guarda (por ejemplo, si procede de un archivo importado), el público se crea o se actualiza como un público de tipo **[!UICONTROL File]**.

   Si la dimensión de segmentación del público guardado ya está definida cuando se guarda (por ejemplo, si procede de una segmentación, después de una consulta, etc.), el público se guarda o actualiza como un público de tipo **[!UICONTROL List]**.

   El contenido del público guardado está disponible en la vista de detalles del público, a la que se puede acceder desde el menú **[!UICONTROL Audiences]**. Las columnas disponibles en esta vista corresponden a las de la transición de entrada de la actividad Guardar público del flujo de trabajo. Por ejemplo, las columnas del archivo importado o los datos adicionales añadidos desde una consulta.

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El flujo de trabajo definido en este ejemplo muestra una actualización de público normal desde la segmentación:

* Se ejecuta automáticamente una vez al mes mediante un **[!UICONTROL Scheduler]**.
* Puede utilizar una **[!UICONTROL Query]** para recuperar todos los perfiles suscritos a los diferentes servicios de aplicaciones disponibles.
* La actividad **[!UICONTROL Save audience]** actualiza el público eliminando perfiles que han dejado de suscribirse al servicio desde la última ejecución del flujo de trabajo y añadiendo los perfiles recién suscritos.

![](assets/save_audience_example_1.png)

La actividad **[!UICONTROL Save audience]** se configura de la siguiente manera:

![](assets/save_audience_example_2.png)
