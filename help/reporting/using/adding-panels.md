---
title: Adición de paneles
description: El informe dinámico permite agregar un panel para filtrar mejor los datos en función del período de tiempo elegido.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: e48b9630-c5ce-4d5d-90e6-97b77fbe3d50
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%

---

# Adición de paneles{#adding-panels}

## Adición de un panel en blanco {#adding-a-blank-panel}

Para iniciar el informe, puede agregar un conjunto de paneles a un informe predeterminado o personalizado. Cada panel contiene diferentes conjuntos de datos y está compuesto por tablas improvisadas y visualizaciones.

Este panel le permite crear los informes según sea necesario. Puede agregar tantos paneles como desee en los informes para filtrar los datos con diferentes períodos de tiempo.

1. Haga clic en el icono **Paneles**. También puede agregar un panel haciendo clic en la **pestaña Insertar** y seleccionando **Nuevo panel en blanco**.

   ![](assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el **Panel en blanco** en el tablero.

   ![](assets/dynamic_report_panel.png)

Ahora puede agregar una tabla improvisada al panel para comenzar a segmentar los datos.

## Adición de una tabla improvisada {#adding-a-freeform-table}

Las tablas improvisadas le permiten crear una tabla para analizar sus datos utilizando las diferentes métricas y dimensiones disponibles en la tabla **Component**.

Cada tabla y visualización se puede cambiar de tamaño y se puede mover para personalizar mejor el informe.

1. Haga clic en el icono **[!UICONTROL Panels]**.

   ![](assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el elemento **[!UICONTROL Freeform]** en el tablero.

   También puede agregar una tabla haciendo clic en la pestaña **[!UICONTROL Insert]** y seleccionando **[!UICONTROL New Freeform]** o haciendo clic en **[!UICONTROL Add a freeform table]** en un panel vacío.

   ![](assets/dynamic_report_panel_2.png)

1. En el campo **[!UICONTROL Drop a segment here]**, añada **[!UICONTROL Segment]** de la pestaña **[!UICONTROL Components]** a la barra superior.

   ![](assets/dynamic_report_panel_3.png)

1. Arrastre y suelte los elementos de la ficha **[!UICONTROL Components]** en las columnas y filas para crear la tabla.

   ![](assets/dynamic_report_freeform_3.png)

1. Haga clic en el icono **[!UICONTROL Settings]** para cambiar cómo se muestran los datos en las columnas.

   ![](assets/dynamic_report_freeform_4.png)

   El **[!UICONTROL Column settings]** está compuesto por:

   * **[!UICONTROL Number]**: permite mostrar u ocultar los números de resumen en la columna .
   * **[!UICONTROL Percent]**: permite mostrar u ocultar el porcentaje en la columna .
   * **[!UICONTROL Interpret zero as no value]**: permite mostrar u ocultar cuando el valor es igual a cero.
   * **[!UICONTROL Background]**: permite mostrar u ocultar la barra de progreso horizontal en las celdas.
   * **[!UICONTROL Include retries]**: permite incluir reintentos en el resultado. Esto solo está disponible para **[!UICONTROL Sent]** y **[!UICONTROL Bounces + Errors]**.

1. Seleccione una o varias filas y haga clic en el icono **[!UICONTROL Visualize]**. Se añade una visualización para reflejar las filas seleccionadas.

   ![](assets/dynamic_report_freeform_5.png)

Ahora puede agregar tantos componentes como necesite y también agregar visualizaciones para proporcionar representaciones gráficas de sus datos.
