---
title: Creación de un informe basado en segmentos de flujo de trabajo
description: Obtenga información sobre cómo comprobar el éxito de la entrega en función de los segmentos de los flujos de trabajo en los informes.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 2%

---

# Creación de un informe basado en segmentos de flujo de trabajo{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]** solo puede segmentar envíos de correo electrónico y SMS.

Después de crear un flujo de trabajo y filtrar la población en diferentes audiencias de destino, puede medir la eficacia de las campañas de marketing en función de los segmentos definidos en este flujo de trabajo de objetivo.
Para segmentar estos segmentos en los informes:

* [Paso 1: Actualización del recurso personalizado de perfiles con segmentos](#step-1--update-profiles-custom-resource-segments)
* [Paso 2: Crear un flujo de trabajo con segmentos](#step-2--create-a-workflow-segments)
* [Paso 3: Crear un informe dinámico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Se debe aceptar el acuerdo de uso de creación de informes dinámica para empezar a recopilar estos datos.
>
>Para obtener más información sobre este acuerdo, consulte [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Paso 1: Actualización del recurso personalizado de perfiles con segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de informar sobre el código de segmento, debe actualizar su **[!UICONTROL Profiles]** recurso personalizado para almacenar sus códigos de segmento.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**, luego seleccione la **[!UICONTROL Profile (profile)]** recurso.
1. En el **[!UICONTROL Sending logs extension]** desde el menú **[!UICONTROL Data structure]** pestaña, marca **[!UICONTROL Add segment code]** para permitir el almacenamiento de los códigos de segmento de los flujos de trabajo de segmentación y enviarlos a dynamic reporting.

   El **[!UICONTROL Segment code]** estará disponible en el **[!UICONTROL Profile]** de dimensión del informe.

   ![](assets/report_segment_4.png)

1. Guarde el recurso personalizado.

1. Ahora debe publicar el recurso personalizado.
En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Clic **[!UICONTROL Prepare publication]** a continuación, cuando haya terminado la preparación, haga clic en **[!UICONTROL Publish]** botón. Para obtener más información sobre recursos personalizados, consulte [página](../../developing/using/updating-the-database-structure.md).

Ahora puede empezar a crear el flujo de trabajo con códigos de segmento.

Tenga en cuenta que los códigos de segmento se recopilarán en cuanto habilite el código de segmento en la **[!UICONTROL Sending logs extension]**.

## Paso 2: Crear un flujo de trabajo con segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Si la transición de entrada de la entrega de correo electrónico está vacía, el código de segmento de la transición anterior se añade de forma predeterminada.

Primero debe crear un flujo de trabajo con una población objetivo diferente. Aquí, queremos enviar un correo electrónico que se personalizará según la edad de nuestra audiencia: una entrega para perfiles de 20 a 30 años y otra para perfiles de entre 30 y 40 años.

1. Cree su flujo de trabajo. Para obtener más información sobre cómo crear el flujo de trabajo, consulte esta sección [página](../../automating/using/building-a-workflow.md).

1. Añadir un **[!UICONTROL Query]** actividad arrastrándola desde la paleta y soltándola en el espacio de trabajo.

1. Segmente perfiles de entre 20 y 40 años para posteriormente segmentarlos en poblaciones más específicas.

   ![](assets/report_segment_1.png)

1. Añadir un **[!UICONTROL Segmentation]** actividad para dividir los resultados de la consulta en dos poblaciones segmentadas. Para obtener más información sobre segmentación, consulte [página](../../automating/using/segmentation.md).

1. Haga doble clic en **[!UICONTROL Segmentation]** actividad para configurarla. Edite el primer segmento haciendo clic en **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Consulte perfiles entre 20 y 30 años y haga clic en **[!UICONTROL Confirm]** cuando termine.

   ![](assets/report_segment_8.png)

1. Clic **[!UICONTROL Add an element]** para crear el segundo segmento y configurarlo como se describe en los pasos anteriores para dirigirse a perfiles entre 30 y 40 años.

1. Edite el **[!UICONTROL Segment code]** para cada población que se pasará a través del sistema de informes dinámico.

   >[!NOTE]
   >Este paso es obligatorio; de lo contrario, no podrá comprender sobre qué segmentos informar.

   ![](assets/report_segment_9.png)

1. Arrastre y suelte un **[!UICONTROL Email delivery]** actividad después de los segmentos.

   ![](assets/report_segment_3.png)

1. Personalice las entregas según las diferentes poblaciones objetivo. Para obtener más información sobre la creación de correos electrónicos, consulte [página](../../designing/using/designing-content-in-adobe-campaign.md).

1. Guarde el flujo de trabajo.

1. Clic **[!UICONTROL Start]** cuando el flujo de trabajo esté listo.

Ahora puede acceder a sus informes para rastrear los códigos de segmento.

## Paso 3: Crear un informe dinámico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Después de realizar las entregas con el flujo de trabajo, puede desglosar los informes utilizando los códigos de segmento del flujo de trabajo.

1. Desde el **[!UICONTROL Reports]** , seleccione un informe predeterminado o haga clic en el botón **[!UICONTROL Create new project]** para comenzar uno desde cero.

   ![](assets/custom_profile_18.png)
1. Arrastre y suelte el **[!UICONTROL Delivery]** a la tabla de forma libre.

   ![](assets/report_segment_5.png)

1. Arrastre y suelte distintas métricas en la tabla, como **[!UICONTROL Open]** y **[!UICONTROL Click]** métricas para empezar a filtrar los datos.
1. En el **[!UICONTROL Dimensions]** categoría, haga clic en **[!UICONTROL Profile]** a continuación, arrastre y suelte la dimensión **[!UICONTROL Segment code]** en la entrega del flujo de trabajo para medir el éxito de su envío de correo electrónico en función de las poblaciones objetivo.

   ![](assets/report_segment_6.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/report_segment_10.png)
