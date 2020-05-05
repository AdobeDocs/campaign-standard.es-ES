---
title: Creación de un flujo de trabajo
description: Esta sección detalla los principios fundamentales y las prácticas recomendadas para crear un nuevo flujo de trabajo.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Creación de un flujo de trabajo{#building-a-workflow}

Esta sección detalla los principios fundamentales y las prácticas recomendadas para crear un nuevo flujo de trabajo.

## Principios operativos del flujo de trabajo{#workflow-operating-principles}

Un flujo de trabajo es una **secuencia de actividades** configurables. Cada actividad tiene una función específica en el proceso. El resultado de cada actividad se reenvía a la siguiente actividad mediante una **transición**, representada por una flecha.

El tipo de datos intercambiados entre una actividad y otra puede afectar a la configuración de las siguientes actividades. Por ejemplo, si se establece una población antes de la actividad del envío de correo electrónico, puede servir como destinatario para el correo electrónico en cuestión.

Puede abrir actividades para comprobar o editar parámetros antes o después de ejecutar el flujo de trabajo.

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Para acceder a la vista de detalles de las transiciones, debe comprobar la **[!UICONTROL Keep interim results]** opción en la **[!UICONTROL Execution]** sección de las propiedades del flujo de trabajo.

![](assets/workflow_overview.png)


## Creación de un flujo de trabajo {#creating-a-workflow}

Puede crear un flujo de trabajo desde un programa, una campaña o la lista de actividad de marketing.

La creación de una actividad de marketing se detalla en la sección [Creación de actividades](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing.

1. Una vez que haya empezado a crear una actividad de marketing de tipo de flujo de trabajo, seleccione la plantilla que desee utilizar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada actividad de marketing oferta varios tipos de forma predeterminada. Esto le permite preconfigurar ciertos parámetros según sus necesidades. For more information, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Introduzca las propiedades generales del flujo de trabajo.

   ![](assets/workflow_creation_2.png)

   Puede introducir un nombre en el campo **Etiqueta** y modificar el ID. El nombre de la actividad y su ID aparecen en la interfaz, pero los destinatarios de mensajes no los ven.

   >[!NOTE]
   >
   >Puede crear el flujo de trabajo dentro de una campaña principal desde la lista de actividades de marketing. Puede vincular este flujo de trabajo a una campaña seleccionando una que ya se haya creado.

   Puede agregar una descripción que el usuario pueda ver en el contenido de la campaña.

   Para facilitarle la búsqueda y la resolución de problemas si no funcionan de la forma esperada, Adobe recomienda dar nombres propios a los flujos de trabajo y a las etiquetas: rellene el campo de descripción del flujo de trabajo para resumir el proceso a realizar de modo que el operador pueda entenderlo fácilmente.

1. Confirme la creación de la actividad y se mostrará el panel de dicha actividad. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

1. Una vez que el flujo de trabajo esté listo para configurarse, puede acceder a opciones adicionales haciendo clic en el **[!UICONTROL Edit properties]** botón. Por ejemplo, puede definir un huso horario específico para utilizarlo de forma predeterminada en todas las actividades del flujo de trabajo. De forma predeterminada, el huso horario del flujo de trabajo es el definido para el operador de Campaña actual.

   ![](assets/workflow_properties.png)

**Temas relacionados:**

* [Creación de un vídeo de flujo de trabajo](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Propiedades del flujo de trabajo](../../automating/using/executing-a-workflow.md#workflow-properties)

## Adición y vinculación de actividades {#adding-and-linking-activities}

A continuación debe definir las distintas actividades y vincularlas todas en el diagrama.

>[!NOTE]
>
>Si no se muestra la paleta, haga clic en el primer botón de la barra de herramientas para mostrarla.

Las Actividades se agrupan por categorías dentro de las diferentes secciones de la paleta.

* La primera sección contiene actividades [de objetivo](../../automating/using/about-targeting-activities.md)
* The second section contains the [execution activities](../../automating/using/about-execution-activities.md), which are mainly used for coordinating other activities.
* La tercera sección contiene actividades que pueden utilizarse para enviar mensajes en diferentes [canales](../../automating/using/about-channel-activities.md). Las Actividades de esta sección pueden variar en función de los canales habilitados en la instancia.
* La cuarta sección contiene actividades [de manipulación de](../../automating/using/about-data-management-activities.md)archivos y gestión de datos.

Creación del diagrama:

1. Añada una actividad arrastrándola desde la paleta y colocándola en el diagrama.

   Por ejemplo, agregue una actividad de **[Inicio](../../automating/using/start-and-end.md)**y, a continuación, una actividad de envío**[ de](../../automating/using/email-delivery.md)** correo electrónico en el diagrama.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >Puede vincular automáticamente una actividad a la anterior colocando la nueva actividad al final de la transición de la anterior.

1. Añada las actividades que necesita y vincúlelas para completar el flujo de trabajo.

   >[!NOTE]
   >
   >También puede duplicado actividades existentes copiándolas y pegándolas. De este modo, se conservan los ajustes que se definieron originalmente. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Una vez que las actividades de flujo de trabajo estén vinculadas, puede personalizar las transiciones entre ellas con la **etiqueta** que desee. Para ello, haga clic con el doble en la transición para acceder a sus propiedades.

Además, **[!UICONTROL Targeting]** y **[!UICONTROL Data management (ETL)]** actividades permite definir **códigos de segmento** para sus transiciones salientes. A continuación, puede crear informes basados en estos códigos de segmento para medir la eficacia de las campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso del flujo de trabajo:**

* [Caso de uso: Crear un envío de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de un envío segmentado en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de envíos con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía un nuevo envío a los no abridores](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuración de actividades {#configuring-activities}

De forma predeterminada, las actividades no están configuradas y no procesarán los datos correctamente si no están configuradas. Cada actividad contiene varias fichas para administrar configuraciones específicas y opciones genéricas de actividad como transiciones salientes, etiquetas, etc.

1. Asegúrese de que todas las actividades están correctamente conectadas. Algunas actividades requieren detectar la estructura o la naturaleza de los datos entrantes para realizar la oferta de las opciones de configuración correctas.
1. Haga clic con el botón Doble en una actividad o selecciónela y haga clic en la acción contextual para abrir su ventana de configuración. **[!UICONTROL Edit]**
1. Edite la etiqueta de la actividad.
1. Defina todas las diferentes opciones que necesite para procesar los datos. Consulte la sección específica de la actividad de esta documentación para conocer las opciones posibles para cada actividad.
1. Guarde la actividad y repita estas operaciones para cada actividad del flujo de trabajo.
1. Guarde el flujo de trabajo.
