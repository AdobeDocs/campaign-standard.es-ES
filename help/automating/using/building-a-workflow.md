---
title: Creación de un flujo de trabajo
description: Esta sección detalla los principios fundamentales y las prácticas recomendadas para crear un nuevo flujo de trabajo.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
context-tags: workflow,wizard;workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7553588c-4679-4dfd-93cb-e705ad4dc0aa
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '981'
ht-degree: 96%

---

# Creación de un flujo de trabajo{#building-a-workflow}

Esta sección detalla los principios fundamentales y las prácticas recomendadas para crear un nuevo flujo de trabajo.

## Principios operativos del flujo de trabajo{#workflow-operating-principles}

Un flujo de trabajo es una **secuencia de actividades que se pueden configurar**. Cada actividad tiene una función específica en el proceso. El resultado de cada actividad se reenvía a la siguiente actividad mediante una **transición**, representada por una flecha.

El tipo de datos intercambiados entre una actividad y otra puede afectar a cómo se configuran las siguientes actividades. Por ejemplo, si se establece una población antes de la actividad de la entrega de correo electrónico, puede servir como destinatario para el correo electrónico en cuestión.

Puede abrir actividades para comprobar o editar parámetros antes o después de ejecutar el flujo de trabajo.

Puede abrir transiciones para comprobar que los datos enviados son correctos durante o después de ejecutar el flujo de trabajo. Para acceder a la vista de detalles de las transiciones, debe comprobar la opción **[!UICONTROL Keep interim results]** en la sección **[!UICONTROL Execution]** de las propiedades del flujo de trabajo.

>[!CAUTION]
>
>Esta opción consume mucho espacio en el disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.

![](assets/workflow_overview.png)

## Creación de un flujo de trabajo {#creating-a-workflow}

Puede crear un flujo de trabajo desde un programa, una campaña o la lista de actividad de marketing.

![](assets/do-not-localize/how-to-video.png) [Descubra cómo crear un flujo de trabajo con este vídeo](#video)

La creación de una actividad de marketing se detalla en la sección [Creación de actividades de marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

1. Una vez que haya empezado a crear una actividad de marketing de tipo de flujo de trabajo, seleccione la plantilla que desee utilizar.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Cada actividad de marketing ofrece varios tipos por defecto. Esto le permite configurar previamente ciertos parámetros según sus necesidades. Para obtener más información, consulte la sección [Administración de plantillas](../../start/using/marketing-activity-templates.md).

1. Introduzca las propiedades generales del flujo de trabajo.

   ![](assets/workflow_creation_2.png)

   Puede introducir un nombre en el campo **Etiqueta** y modificar el ID. El nombre de la actividad y su ID aparecen en la interfaz, pero no son visibles para los destinatarios de mensajes.

   >[!NOTE]
   >
   >Puede crear su flujo de trabajo dentro de una campaña principal desde la lista de actividades de marketing. Puede vincular este flujo de trabajo a una campaña seleccionando una que ya se haya creado.

   Puede añadir una descripción que el usuario pueda ver en el contenido de la campaña.

   Para facilitarle la búsqueda y la resolución de problemas si no funcionan de la forma esperada, Adobe recomienda dar nombres propios a los flujos de trabajo y a las etiquetas: rellene el campo de descripción del flujo de trabajo para resumir el proceso a realizar de modo que el operador pueda entenderlo fácilmente.

1. Confirme la creación de la actividad y, entonces, se mostrará el panel de dicha actividad. Para obtener más información, consulte la sección [Interfaz de flujo de trabajo](../../automating/using/workflow-interface.md).

1. Una vez que el flujo de trabajo esté listo para configurarse, puede acceder a opciones adicionales haciendo clic en el botón **[!UICONTROL Edit properties]**.

   Por ejemplo, puede definir un huso horario específico para utilizarlo de forma predeterminada en todas las actividades del flujo de trabajo. De forma predeterminada, el uso horario del flujo de trabajo es la definida para el operador de Campaign actual.

   Para obtener más información sobre las propiedades de los flujos de trabajo, consulte [esta página](../../automating/using/managing-execution-options.md).

   ![](assets/workflow_properties.png)

## Adición y vinculación de actividades {#adding-and-linking-activities}

A continuación debe definir las distintas actividades y vincularlas todas en el diagrama.

>[!NOTE]
>
>Si no se muestra la paleta, haga clic en el primer botón de la barra de herramientas para mostrarla.

Las actividades se agrupan por categorías dentro de las diferentes secciones de la paleta.

* La primera sección contiene las [actividades de segmentación](../../automating/using/about-targeting-activities.md)
* La segunda sección contiene las [actividades de ejecución ](../../automating/using/about-execution-activities.md), que se utilizan principalmente para coordinar otras actividades.
* La tercera sección contiene actividades que pueden utilizarse para enviar mensajes en diferentes [canales](../../automating/using/about-channel-activities.md). Las actividades de esta sección pueden variar en función de los canales habilitados en su instancia.
* La cuarta sección contiene [actividades de manipulación de archivos y gestión de datos](../../automating/using/about-data-management-activities.md).

Creación del diagrama:

1. Añada una actividad arrastrándola desde la paleta y soltándola en el diagrama.

   Por ejemplo, añada una actividad de **[inicio](../../automating/using/start-and-end.md)** y, a continuación, una actividad de **[entrega de correo electrónico](../../automating/using/email-delivery.md)** en el diagrama.

1. Vincule las actividades arrastrando la transición de la actividad **inicio** y soltándola en la actividad **entrega de correo electrónico**.

   >[!NOTE]
   >
   >Puede vincular automáticamente una actividad a la anterior colocando la nueva actividad al final de la transición de la anterior.

1. Añada las actividades que necesite y vincúlelas para completar el flujo de trabajo.

   >[!NOTE]
   >
   >También puede duplicar actividades existentes copiándolas y pegándolas. De este modo, se conserva la configuración que se definió originalmente. Para obtener más información, consulte [Duplicado de actividades de flujo de trabajo](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Una vez que las actividades de flujo de trabajo estén vinculadas, puede personalizar las transiciones entre ellas con la **etiqueta** que desee. Para ello, haga doble clic en la transición para acceder a sus propiedades.

Además, las actividades **[!UICONTROL Targeting]** y **[!UICONTROL Data management (ETL)]** le permiten definir **códigos de segmento** para sus transiciones salientes. Puede crear informes basados en estos códigos de segmento para medir la eficacia de sus campañas de marketing. Para obtener más información, consulte [esta sección](../../reporting/using/creating-a-report-workflow-segment.md).

**Casos de uso del flujo de trabajo:**

* [Caso de uso: Creación de una entrega de correo electrónico una vez a la semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en una ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Flujo de trabajo de redireccionamiento que envía una nueva entrega a receptores que no abran el correo](../../automating/using/workflow-cross-channel-retargeting.md)

## Configuración de actividades {#configuring-activities}

De forma predeterminada, las actividades no están configuradas y no procesarán los datos correctamente si no están configuradas. Cada actividad contiene varias pestañas para administrar configuraciones específicas y opciones genéricas de actividad como transiciones salientes, etiquetas, etc.

1. Asegúrese de que todas las actividades están correctamente conectadas. Algunas actividades requieren detectar la estructura o la naturaleza de los datos entrantes para ofrecer las opciones de configuración correctas.
1. Haga doble clic en una actividad o selecciónela y haga clic en la acción contextual **[!UICONTROL Edit]** para abrir su ventana de configuración.
1. Edite la etiqueta de la actividad.
1. Defina todas las opciones diferentes que necesite para procesar los datos. Consulte la sección específica de la actividad de esta documentación para conocer las posibles opciones para cada actividad.
1. Guarde la actividad y repita estas operaciones para cada actividad del flujo de trabajo.
1. Guarde el flujo de trabajo.

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear un flujo de trabajo.

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

Hay disponibles más vídeos de procedimientos para el Campaign Standard [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
