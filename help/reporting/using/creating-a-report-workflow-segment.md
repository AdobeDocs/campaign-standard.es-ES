---
title: Creación de un informe basado en segmentos de flujo de trabajo
description: Obtenga información sobre cómo comprobar el éxito de la entrega en función de los segmentos de los flujos de trabajo de los informes.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 514bffa0-2413-4212-b1b9-e070031c462f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Creación de un informe basado en segmentos de flujo de trabajo{#creating-a-report-workflow-segment}

>[!CAUTION]
> **[!UICONTROL Segment code]**solo puede dirigirse a envíos de correo electrónico y SMS.

Después de crear un flujo de trabajo y filtrar la población a una audiencia objetivo diferente, puede medir la eficacia de las campañas de marketing en función de los segmentos definidos en este flujo de trabajo de objetivo.
Para dirigir estos segmentos a sus informes:

* [Paso 1: Actualizar el recurso personalizado de perfiles con segmentos](#step-1--update-profiles-custom-resource-segments)
* [Paso 2: Creación de un flujo de trabajo con segmentos](#step-2--create-a-workflow-segments)
* [Paso 3: Crear un informe dinámico para filtrar segmentos](#step-3--create-a-dynamic-report-filter-segments)

>[!CAUTION]
>Se debe aceptar el acuerdo de uso de los informes dinámicos para empezar a recopilar estos datos.
>
>Para obtener más información sobre este acuerdo, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Paso 1: Actualizar el recurso personalizado de perfiles con segmentos{#step-1--update-profiles-custom-resource-segments}

Antes de generar informes sobre el código de segmento, debe actualizar el recurso personalizado **[!UICONTROL Profiles]** para almacenar los códigos de segmento.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y, a continuación, seleccione el recurso **[!UICONTROL Profile (profile)]**.
1. En el menú **[!UICONTROL Sending logs extension]** de la pestaña **[!UICONTROL Data structure]**, marque **[!UICONTROL Add segment code]** para permitir el almacenamiento de los códigos de segmento de flujos de trabajo de objetivos y enviarlos a informes dinámicos.

   El **[!UICONTROL Segment code]** estará disponible en la sección de dimensión **[!UICONTROL Profile]** del informe.

   ![](assets/report_segment_4.png)

1. Guarde el recurso personalizado.

1. Ahora debe publicar el recurso personalizado.
En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**.

   ![](assets/custom_profile_7.png)

1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando haya terminado la preparación, haga clic en el botón **[!UICONTROL Publish]**. Para obtener más información sobre los recursos personalizados, consulte esta [página](../../developing/using/updating-the-database-structure.md).

Ahora puede empezar a crear su flujo de trabajo con códigos de segmento.

Tenga en cuenta que los códigos de segmento se recopilarán en cuanto habilite el código de segmento en **[!UICONTROL Sending logs extension]**.

## Paso 2: Creación de un flujo de trabajo con segmentos {#step-2--create-a-workflow-segments}

>[!NOTE]
>Si la transición de entrada del envío de correo electrónico está vacía, el código de segmento de la transición anterior se añade de forma predeterminada.

Primero debe crear un flujo de trabajo con una población objetivo diferente. Aquí, queremos enviar un correo electrónico que se personalizará según la edad de nuestra audiencia: una entrega para perfiles de 20 a 30 años y otra para perfiles de entre 30 y 40 años.

1. Cree el flujo de trabajo. Para obtener más información sobre cómo crear el flujo de trabajo, consulte esta [página](../../automating/using/building-a-workflow.md).

1. Agregue una actividad **[!UICONTROL Query]** arrastrándola desde la paleta y soltándola en el espacio de trabajo.

1. Segmente perfiles de 20 a 40 años de edad para segmentarlos posteriormente en poblaciones más específicas.

   ![](assets/report_segment_1.png)

1. Agregue una actividad **[!UICONTROL Segmentation]** para dividir los resultados de la consulta en dos poblaciones objetivo. Para obtener más información sobre segmentación, consulte esta [página](../../automating/using/segmentation.md).

1. Haga doble clic en la actividad **[!UICONTROL Segmentation]** para configurarla. Edite el primer segmento haciendo clic en **[!UICONTROL Edit properties]**.

   ![](assets/report_segment_7.png)

1. Consulte los perfiles entre 20 y 30 años y haga clic en **[!UICONTROL Confirm]** cuando termine.

   ![](assets/report_segment_8.png)

1. Haga clic en **[!UICONTROL Add an element]** para crear el segundo segmento y configurarlo como se describe en los pasos anteriores para dirigirse a perfiles entre 30 y 40 años.

1. Edite el **[!UICONTROL Segment code]** para cada población que se transmitirá a través del sistema de informes dinámico.

   >[!NOTE]
   >Este paso es obligatorio o, de lo contrario, no podrá comprender qué segmentos informar.

   ![](assets/report_segment_9.png)

1. Arrastre y suelte una actividad **[!UICONTROL Email delivery]** después de los segmentos.

   ![](assets/report_segment_3.png)

1. Personalice los envíos en función de las diferentes poblaciones objetivo. Para obtener más información sobre la creación de correos electrónicos, consulte esta [página](../../designing/using/designing-content-in-adobe-campaign.md).

1. Guarde el flujo de trabajo.

1. Haga clic en **[!UICONTROL Start]** cuando el flujo de trabajo esté listo.

Ahora puede acceder a sus informes para realizar un seguimiento de sus códigos de segmento.

## Paso 3: Crear un informe dinámico para filtrar segmentos {#step-3--create-a-dynamic-report-filter-segments}

Después de realizar envíos con el flujo de trabajo, puede desglosar los informes mediante los códigos de segmento del flujo de trabajo.

1. En la pestaña **[!UICONTROL Reports]** , seleccione un informe predeterminado o haga clic en el botón **[!UICONTROL Create new project]** para comenzar desde cero.

   ![](assets/custom_profile_18.png)
1. Arrastre y suelte la dimensión **[!UICONTROL Delivery]** en la tabla de forma libre.

   ![](assets/report_segment_5.png)

1. Arrastre y suelte distintas métricas en la tabla, como las métricas **[!UICONTROL Open]** y **[!UICONTROL Click]** , para comenzar a filtrar los datos.
1. En la categoría **[!UICONTROL Dimensions]** , haga clic en la dimensión **[!UICONTROL Profile]** y arrastre y suelte la dimensión **[!UICONTROL Segment code]** en el envío del flujo de trabajo para medir el éxito del envío de correo electrónico en función de las poblaciones objetivo.

   ![](assets/report_segment_6.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/report_segment_10.png)
