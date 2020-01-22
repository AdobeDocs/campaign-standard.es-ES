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
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Creación de un flujo de trabajo{#building-a-workflow}

Esta sección detalla los principios fundamentales y las prácticas recomendadas para crear un nuevo flujo de trabajo:

* Creación de un flujo de trabajo.
* Adición y vinculación de actividades.
* Configuración de actividades.

## Creación de un flujo de trabajo {#creating-a-workflow}

Puede crear un flujo de trabajo desde un programa, una campaña o la lista de actividades de marketing.

La creación de una actividad de marketing se detalla en la sección [Creación de actividades](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing.

1. Una vez que haya empezado a crear una actividad de marketing de tipo de flujo de trabajo, seleccione la plantilla que desee utilizar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada actividad de marketing ofrece varios tipos de forma predeterminada. Esto le permite preconfigurar ciertos parámetros según sus necesidades. For more information, refer to the [Managing templates](../../start/using/marketing-activity-templates.md) section.

1. Introduzca las propiedades generales del flujo de trabajo.

   ![](assets/workflow_creation_2.png)

   Puede introducir un nombre en el campo **Etiqueta** y modificar el ID. El nombre de la actividad y su ID aparecen en la interfaz, pero los destinatarios del mensaje no los ven.

   >[!NOTE]
   >
   >Puede crear el flujo de trabajo dentro de una campaña principal desde la lista de actividades de marketing. Puede vincular este flujo de trabajo a una campaña seleccionando una que ya se haya creado.

   Puede agregar una descripción que el usuario pueda ver en el contenido de la campaña.

   Para facilitarle la búsqueda y la resolución de problemas si no funcionan de la forma esperada, Adobe recomienda dar nombres propios a los flujos de trabajo y a las etiquetas: rellene el campo de descripción del flujo de trabajo para resumir el proceso a realizar de modo que el operador pueda entenderlo fácilmente.

1. Confirme la creación de la actividad y se mostrará el tablero de dicha actividad. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**Tema relacionado:**

[Creación de un vídeo de flujo de trabajo](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)

## Adición y vinculación de actividades {#adding-and-linking-activities}

A continuación debe definir las distintas actividades y vincularlas todas en el diagrama.

>[!NOTE]
>
>Si no se muestra la paleta, haga clic en el primer botón de la barra de herramientas para mostrarla.

Las actividades se agrupan por categorías dentro de las diferentes secciones de la paleta.

* La primera sección contiene actividades de segmentación.
* La segunda sección contiene las actividades de ejecución, que se utilizan principalmente para coordinar otras actividades.
* La tercera sección contiene actividades que se pueden utilizar para enviar mensajes por distintos canales. Las actividades de esta sección pueden variar en función de los canales habilitados en la instancia.
* La cuarta sección contiene actividades de administración de datos y manipulación de archivos.

Creación del diagrama:

1. Para agregar una actividad, arrástrela desde la paleta y colóquela en el diagrama.

   Por ejemplo, agregue una actividad de **inicio** y, a continuación, una actividad de envío por **correo electrónico** en el diagrama.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >Puede vincular automáticamente una actividad a la anterior colocando la nueva actividad al final de la transición de la anterior.

1. Agregue las actividades que necesite y vincúlelas para completar el flujo de trabajo.

   >[!NOTE]
   >
   >También puede duplicar las actividades existentes copiándolas y pegándolas. De este modo, se conservan los ajustes que se definieron originalmente. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Una vez que las actividades de flujo de trabajo estén vinculadas, puede personalizar las transiciones entre ellas con la **etiqueta** que desee. Para ello, haga doble clic en la transición para acceder a sus propiedades.

Además, **[!UICONTROL Targeting]**y**[!UICONTROL Data management (ETL)]** las actividades le permiten definir códigos **de** segmentos para sus transiciones de salida. A continuación, puede crear informes basados en estos códigos de segmento para medir la eficacia de las campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso del flujo de trabajo:**

* [Caso de uso: Crear un envío de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía una nueva entrega a no abridores](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuración de actividades {#configuring-activities}

De forma predeterminada, las actividades no están configuradas y no procesarán los datos correctamente si no están configuradas. Cada actividad contiene varias fichas para administrar configuraciones específicas y opciones genéricas de actividad, como transiciones de salida, etiquetas, etc.

1. Asegúrese de que todas las actividades están correctamente conectadas. Algunas actividades requieren detectar la estructura o la naturaleza de los datos entrantes para ofrecer las opciones de configuración correctas.
1. Haga doble clic en una actividad o selecciónela y haga clic en la acción contextual para abrir su ventana de configuración. **[!UICONTROL Edit]**
1. Edite la etiqueta de la actividad.
1. Defina todas las diferentes opciones que necesite para procesar los datos. Consulte la sección específica de la actividad de esta documentación para conocer las opciones posibles para cada actividad.
1. Guarde la actividad y repita estas operaciones para cada actividad del flujo de trabajo.
1. Guarde el flujo de trabajo.
