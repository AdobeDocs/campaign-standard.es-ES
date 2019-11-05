---
title: Creación de un informe basado en segmentos de flujo de trabajo
description: Obtenga información sobre cómo comprobar el éxito de la entrega en función de los segmentos de los flujos de trabajo de los informes.
page-status-flag: nunca activado
uuid: f75e005b-5328-4c98-9e78-51d54fd0e246
contentOwner: benat
products: SG_CAMPAIGN/STANDARD
audience: informes
content-type: referencia
topic-tags: personalizar informes
discoiquuid: b6d3de63-3add-4881-8917-04a6f8b6be4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación de un informe basado en segmentos de flujo de trabajo{#creating-a-report-workflow-segment}

Después de crear un flujo de trabajo y filtrar la población a diferentes audiencias objetivo, puede medir la eficacia de las campañas de marketing en función de los segmentos definidos en este flujo de trabajo de objetivo.
Para dirigir estos segmentos en los informes:

* [Paso 1: Actualizar el recurso personalizado de perfiles con segmentos](#step-1--update-profiles-custom-resource-segments)
* [Paso 2: Crear un flujo de trabajo con segmentos](#step-2--create-a-workflow-segments)
* [Paso 3: Crear un informe dinámico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Se debe aceptar el acuerdo de uso de informes dinámicos para empezar a recopilar estos datos.
>For more on this agreement, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Paso 1: Actualizar el recurso personalizado de perfiles con segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de generar informes sobre el código de segmento, debe actualizar el recurso personalizado para que se almacenen los códigos de segmento **[!UICONTROL Profiles]** .

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** y, a continuación, seleccione el **[!UICONTROL Profile (profile)]** recurso.
1. En el **[!UICONTROL Sending logs extension]** menú de la **[!UICONTROL Data structure]** ficha, marque **[!UICONTROL Add segment code]** para permitir el almacenamiento de los códigos de segmento desde flujos de trabajo de objetivo y enviarlos a informes dinámicos.

   El **[!UICONTROL Segment code]** estará disponible en la sección de **[!UICONTROL Profile]** dimensiones del informe.

   ![](assets/report_segment_4.png)

1. Guarde el recurso personalizado.

1. Ahora debe publicar el recurso personalizado.
En el menú avanzado, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el **[!UICONTROL Publish]** botón. For more information on custom resource, refer to this [page](../../developing/using/updating-the-database-structure.md).

Ahora puede empezar a crear el flujo de trabajo con códigos de segmento.

Tenga en cuenta que los códigos de segmento se recopilarán tan pronto como habilite el código de segmento en el **[!UICONTROL Sending logs extension]**.

## Paso 2: Crear un flujo de trabajo con segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Si la transición de entrada del envío de correo electrónico está vacía, el código de segmento de la transición anterior se agregará de forma predeterminada.

En primer lugar, debe crear un flujo de trabajo con una población objetivo diferente. Aquí, queremos enviar un correo electrónico que será personalizado en función de la edad de nuestra audiencia: una entrega para perfiles de 20 a 30 años y otra para perfiles de entre 30 y 40 años.

1. Cree su flujo de trabajo. Para obtener más información sobre cómo crear el flujo de trabajo, consulte esta [página](../../automating/using/building-a-workflow.md).

1. Agregue una **[!UICONTROL Query]** actividad arrastrándola desde la paleta y colocándola en el espacio de trabajo.

1. Perfiles de 20 a 40 años de edad para segmentarlos posteriormente en poblaciones más específicas.

   ![](assets/report_segment_1.png)

1. Agregue una **[!UICONTROL Segmentation]** actividad para dividir los resultados de la consulta en dos poblaciones objetivo. For more on segmentation, refer to this [page](../../automating/using/targeting-data.md#segmenting-data).

1. Haga doble clic en la **[!UICONTROL Segmentation]** actividad para configurarla. Para editar el primer segmento, haga clic en **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Consulte los perfiles entre 20 y 30 años y haga clic **[!UICONTROL Confirm]** cuando termine.

   ![](assets/report_segment_8.png)

1. Haga clic en **[!UICONTROL Add an element]** para crear el segundo segmento y configúrelo como se describe en los pasos anteriores para dirigirse a perfiles entre 30 y 40 años.

1. Edite **[!UICONTROL Segment code]** para cada población que se pasa a través de informes dinámicos.

   >[!NOTE]
   >Este paso es obligatorio o, de lo contrario, no podrá comprender qué segmentos informar.

   ![](assets/report_segment_9.png)

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad después de los segmentos.

   ![](assets/report_segment_3.png)

1. Personalice los envíos en función de las distintas poblaciones objetivo. For more on email creation, refer to this [page](../../designing/using/overview.md).

1. Guarde el flujo de trabajo.

1. Haga clic **[!UICONTROL Start]** cuando el flujo de trabajo esté listo.

Ahora puede acceder a sus informes para rastrear sus códigos de segmento.

## Paso 3: Crear un informe dinámico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Después de enviar los envíos con el flujo de trabajo, puede desglosar los informes utilizando los códigos de segmento del flujo de trabajo.

1. Desde la **[!UICONTROL Reports]** ficha, seleccione un informe listo para usar o haga clic en el **[!UICONTROL Create new project]** botón para iniciar uno desde cero.

   ![](assets/custom_profile_18.png)
1. Arrastre y suelte la **[!UICONTROL Delivery]** dimensión en la tabla improvisada.

   ![](assets/report_segment_5.png)

1. Arrastre y suelte distintas métricas en la tabla, como las métricas **[!UICONTROL Open]** y **[!UICONTROL Click]** , para empezar a filtrar los datos.
1. En la **[!UICONTROL Dimensions]** categoría, haga clic en la **[!UICONTROL Profile]** dimensión y, a continuación, arrastre y suelte la **[!UICONTROL Segment code]** dimensión en la entrega del flujo de trabajo para medir el éxito de la entrega de correo electrónico en función de las poblaciones objetivo.

   ![](assets/report_segment_6.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/report_segment_10.png)
