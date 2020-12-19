---
solution: Campaign Standard
product: campaign
title: Creación de un informe basado en segmentos de flujo de trabajo
description: Descubra cómo comprobar el éxito de su envío en función de los segmentos de sus flujos de trabajo en los informes.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 2%

---


# Creación de un informe basado en segmentos de flujo de trabajo{#creating-a-report-workflow-segment}

Después de crear un flujo de trabajo y filtrar la población en una audiencia de objetivo diferente, puede medir la eficacia de las campañas de marketing en función de los segmentos definidos en este flujo de trabajo de objetivo.
Para destinatario de estos segmentos en los informes:

* [Paso 1: Actualizar recursos personalizados de Perfiles con segmentos](#step-1--update-profiles-custom-resource-segments)
* [Paso 2: Crear un flujo de trabajo con segmentos](#step-2--create-a-workflow-segments)
* [Paso 3: Crear un informe dinámico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Se debe aceptar el acuerdo de uso de sistema de informes dinámico para recopilar estos datos en inicios.
>Para obtener más información sobre este acuerdo, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Paso 1: Actualizar recursos personalizados de Perfiles con segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de sistema de informes en el código de segmento, debe actualizar el **[!UICONTROL Profiles]** recurso personalizado para que se almacenen los códigos de segmento.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y, a continuación, seleccione el recurso **[!UICONTROL Profile (profile)]**.
1. En el menú **[!UICONTROL Sending logs extension]** de la ficha **[!UICONTROL Data structure]**, marque **[!UICONTROL Add segment code]** para permitir que el almacenamiento de sus códigos de segmento no tenga flujos de trabajo de objetivo y enviarlos a sistema de informes dinámico.

   La **[!UICONTROL Segment code]** estará disponible en la sección de dimensión **[!UICONTROL Profile]** del informe.

   ![](assets/report_segment_4.png)

1. Guarde el recurso personalizado.

1. Ahora debe publicar el recurso personalizado.
En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el botón **[!UICONTROL Publish]**. Para obtener más información sobre los recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md).

Ahora puede crear en inicio su flujo de trabajo con códigos de segmento.

Tenga en cuenta que los códigos de segmento se recopilarán en cuanto habilite el código de segmento en **[!UICONTROL Sending logs extension]**.

## Paso 2: Crear un flujo de trabajo con segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Si la transición de entrada del envío de correo electrónico está vacía, el Código de segmento de la transición anterior se agregará de forma predeterminada.

En primer lugar, debe crear un flujo de trabajo con una población objetivo diferente. Aquí, queremos enviar un correo electrónico que será personalizado según la edad de nuestra audiencia: un envío para perfiles de entre 20 y 30 años y otro para perfiles de entre 30 y 40 años.

1. Cree su flujo de trabajo. Para obtener más información sobre cómo crear el flujo de trabajo, consulte esta [página](../../automating/using/building-a-workflow.md).

1. Añada una actividad **[!UICONTROL Query]** arrastrándola desde la paleta y colocándola en el espacio de trabajo.

1. Perfiles de destinatario de 20 a 40 años para luego segmentarlos en poblaciones más específicas.

   ![](assets/report_segment_1.png)

1. Añada una actividad **[!UICONTROL Segmentation]** para dividir los resultados de la consulta en dos poblaciones objetivo. Para obtener más información sobre la segmentación, consulte esta [página](../../automating/using/segmentation.md).

1. Doble haga clic en la actividad **[!UICONTROL Segmentation]** para configurarla. Para editar el primer segmento, haga clic en **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Perfiles de consulta entre 20 y 30 años y haga clic **[!UICONTROL Confirm]** cuando termine.

   ![](assets/report_segment_8.png)

1. Haga clic **[!UICONTROL Add an element]** para crear el segundo segmento y configurarlo como se describe en los pasos anteriores para perfiles de destinatario entre los 30 y los 40 años.

1. Edite el **[!UICONTROL Segment code]** para cada población que se pasa a través de sistemas de informes dinámicos.

   >[!NOTE]
   >Este paso es obligatorio o, de lo contrario, no podrá comprender qué segmentos informar.

   ![](assets/report_segment_9.png)

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad después de los segmentos.

   ![](assets/report_segment_3.png)

1. Personalice sus envíos en función de las diferentes poblaciones objetivo. Para obtener más información sobre la creación de correo electrónico, consulte esta [página](../../designing/using/designing-content-in-adobe-campaign.md).

1. Guarde el flujo de trabajo.

1. Haga clic en **[!UICONTROL Start]** cuando el flujo de trabajo esté listo.

Ahora puede acceder a los informes para rastrear sus códigos de segmento.

## Paso 3: Crear un informe dinámico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Después de enviar envíos con el flujo de trabajo, puede desglosar los informes utilizando los códigos de segmento del flujo de trabajo.

1. En la ficha **[!UICONTROL Reports]**, seleccione un informe listo para usar o haga clic en el botón **[!UICONTROL Create new project]** para inicio uno desde cero.

   ![](assets/custom_profile_18.png)
1. Arrastre y suelte la dimensión **[!UICONTROL Delivery]** en la tabla improvisada.

   ![](assets/report_segment_5.png)

1. Arrastre y suelte distintas métricas en la tabla, como las métricas **[!UICONTROL Open]** y **[!UICONTROL Click]**, para filtrar los datos en inicio.
1. En la categoría **[!UICONTROL Dimensions]**, haga clic en la dimensión **[!UICONTROL Profile]** y, a continuación, arrastre y suelte la dimensión **[!UICONTROL Segment code]** en el envío del flujo de trabajo para medir el éxito del envío de correo electrónico en función de las poblaciones objetivo.

   ![](assets/report_segment_6.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/report_segment_10.png)
