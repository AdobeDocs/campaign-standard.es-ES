---
title: Creación de un flujo de trabajo
seo-title: Creación de un flujo de trabajo
description: Creación de un flujo de trabajo
seo-description: Esta sección detalla los principios principales y las prácticas recomendadas para crear un nuevo flujo de trabajo.
page-status-flag: no activado nunca
uuid: 11374 f 64-8 d 34-40 da -937 b -09 f 419250 f 4 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: flujo de trabajo general operation
discoiquuid: c 26 fcb 0 e -19 d 5-4 bd 5-b 7 d 6-2 d 22 ce 92 ad 90
context-tags: workflow, asistente; flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51154892b2d5bd5685272735cdd6e7d9474e09a6

---


# Building a workflow{#building-a-workflow}

Esta sección detalla los principios principales y las prácticas recomendadas para crear un nuevo flujo de trabajo:

* Creación de un flujo de trabajo.
* Adición y vinculación de actividades.
* Configuración de actividades.

## Creating a workflow {#creating-a-workflow}

Puede crear un flujo de trabajo a partir de un programa, una campaña o la lista de actividades de marketing.

Creating a marketing activity is detailed in the [Creating marketing activities](../../start/using/marketing-activities.md#creating-a-marketing-activity) section.

1. Una vez que haya comenzado a crear una actividad de marketing tipo de flujo de trabajo, seleccione la plantilla que desee utilizar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada actividad de mercadotecnia ofrece varios tipos de forma predeterminada. Permiten preconfigurar determinados parámetros según sus necesidades. For more information, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. Introduzca las propiedades generales del flujo de trabajo.

   ![](assets/workflow_creation_2.png)

   You can enter a name in the **Label** field and modify the ID. El nombre de la actividad y su ID aparecen en la interfaz, pero los destinatarios del mensaje los ven.

   >[!NOTE]
   >
   >Puede crear el flujo de trabajo dentro de una campaña principal desde la lista de actividades de marketing. Puede vincular este flujo de trabajo a una campaña seleccionando uno que ya se haya creado.

   Puede agregar una descripción que el usuario puede ver en el contenido de la campaña.

   Dado que facilita la búsqueda y resolución de problemas si no funcionan de las formas esperadas, Adobe recomienda dar a los flujos de trabajo nombres y etiquetas propios: complete el campo de descripción del flujo de trabajo para resumir el proceso que se realizará para que el operador pueda comprenderlo fácilmente.

1. Confirmar la creación de la actividad y el tablero para esa actividad se mostrarán. For more on this, refer to the [Workflow interface](../../automating/using/workflow-interface.md) section.

**Tema relacionado:**

[Creación de](https://helpx.adobe.com/campaign/kt/acs/using/acs-create-workflow-feature-video-use.html) un vídeo de flujo de trabajo

## Adding and linking activities {#adding-and-linking-activities}

Ahora debe definir las diversas actividades y vincularlas en el diagrama.

>[!NOTE]
>
>Si no se muestra la paleta, haga clic en el primer botón de la barra de herramientas para mostrarlo.

Las actividades se agrupan por categoría dentro de las diferentes secciones de la paleta.

* La primera sección contiene actividades de segmentación.
* La segunda sección contiene las actividades de ejecución, que se utilizan principalmente para coordinar otras actividades.
* La tercera sección contiene actividades que pueden utilizarse para enviar mensajes en distintos canales. Las actividades de esta sección pueden variar según los canales que estén habilitados en la instancia.
* La cuarta sección contiene actividades de manipulación de archivos y administración de datos.

Para crear el diagrama:

1. Agregue una actividad arrastrándola desde la paleta y soltándola en el diagrama.

   For example, add a **Start** activity and then an **Email delivery** activity on the diagram.

1. Link the activities together by dragging the **Start** activity transition and dropping it on to the **Email delivery** activity.

   >[!NOTE]
   >
   >Puede vincular automáticamente una actividad a la anterior colocando la nueva actividad al final de la transición de la anterior.

1. Agregue las actividades que necesita y vincule las mismas para completar el flujo de trabajo.

   >[!NOTE]
   >
   >También puede duplicar actividades existentes copiándolas y pegándolas. De esta forma, mantiene la configuración definida originalmente. For more on this, refer to [Duplicating workflow activities](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Once your workflow activities are linked together, you can personalize the transitions between them with the **label** of your choice. Para ello, haga doble clic en la transición para acceder a sus propiedades.

Moreover, **[!UICONTROL Targeting]** and **[!UICONTROL Data management (ETL)]** activities allows you to define **segment codes** for their outbound transitions. Luego puede crear informes basados en estos códigos de segmento para medir la eficacia de sus campañas de inserción. For more on this, refer to [this section](../../reporting/using/creating-a-report-workflow-segment.md).

## Configuring activities {#configuring-activities}

De forma predeterminada, las actividades no se establecen y no procesarán los datos correctamente si no están configurados. Cada actividad contiene varias fichas para administrar configuraciones específicas y opciones de actividad genéricas como transiciones salientes, etiquetas, etc.

1. Asegúrese de que todas las actividades estén correctamente conectadas. Algunas actividades requieren detectar la estructura o naturaleza de los datos entrantes para ofrecer las opciones de configuración correctas.
1. Double-click an activity or select it and click the **[!UICONTROL Edit]** contextual action to open its configuration window.
1. Edite la etiqueta de la actividad.
1. Defina todas las opciones que necesite para procesar los datos. Consulte la sección específica de esta documentación para conocer las posibles opciones de cada actividad.
1. Guarde la actividad y repita estas operaciones para cada actividad del flujo de trabajo.
1. Guarde el flujo de trabajo.

