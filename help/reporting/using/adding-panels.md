---
title: Adición de paneles
description: El informe dinámico permite agregar un panel para filtrar mejor los datos en función del período de tiempo seleccionado.
page-status-flag: nunca activado
uuid: 8e76e837-5efc-4250-8192-dee1a0bd62fe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: informes
content-type: referencia
topic-tags: personalizar informes
discoiquuid: f4e1e676-5ca2-4a58-96d7-d378ff803710
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Adición de paneles{#adding-panels}

## Adición de un panel en blanco {#adding-a-blank-panel}

Para iniciar el informe, puede agregar un conjunto de paneles a un informe predeterminado o personalizado. Cada panel contiene diferentes conjuntos de datos y está compuesto de tablas y visualizaciones improvisadas.

Este panel le permite generar los informes según sea necesario. Puede agregar tantos paneles como desee en los informes para filtrar los datos con diferentes períodos de tiempo.

1. Click the **Panels** icon. También puede agregar un panel haciendo clic en la ficha **** Insertar y seleccionando **Nuevo panel** en blanco.

   ![](assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el panel **en blanco** en el tablero.

   ![](assets/dynamic_report_panel.png)

Ahora puede agregar una tabla improvisada al panel para empezar a dirigir los datos.

## Adición de una tabla improvisada {#adding-a-freeform-table}

Las tablas improvisadas permiten crear una tabla para analizar los datos con las distintas métricas y dimensiones disponibles en la tabla **Componente** .

Se puede cambiar el tamaño de cada tabla y visualización y moverlas para personalizar mejor el informe.

1. Click the **Panels** icon.

   ![](assets/dynamic_report_panel_1.png)

1. Arrastre y suelte el elemento **improvisado** en el tablero.

   También puede agregar una tabla haciendo clic en la ficha **Insertar** y seleccionando **Nueva forma libre** o haciendo clic en **Agregar una tabla** improvisada en un panel vacío.

   ![](assets/dynamic_report_panel_2.png)

1. A partir de la versión 19.4 de Campaign, el **[!UICONTROL Exclude proof]** se seleccionará de forma predeterminada. Si es necesario, puede cambiarlo arrastrando y soltando uno de los **[!UICONTROL Segments]** de la **[!UICONTROL Components]** ficha en la barra superior.

   ![](assets/dynamic_report_panel_3.png)

1. Arrastre y suelte los elementos de la ficha **Componentes** en las columnas y filas para crear la tabla.

   ![](assets/dynamic_report_freeform_3.png)

1. Haga clic en el icono **Configuración** para cambiar la forma en que se muestran los datos en las columnas.

   ![](assets/dynamic_report_freeform_4.png)

   El **[!UICONTROL Column settings]** grupo está compuesto por:

   * **[!UICONTROL Number]**:: permite mostrar u ocultar los números de resumen en la columna.
   * **[!UICONTROL Percent]**:: permite mostrar u ocultar el porcentaje en la columna.
   * **[!UICONTROL Interpret zero as no value]**:: permite mostrar u ocultar cuando el valor es igual a cero.
   * **[!UICONTROL Background]**:: permite mostrar u ocultar la barra de progreso horizontal en las celdas.
   * **[!UICONTROL Include retries]**:: permite incluir reintentos en el resultado. Esto solo está disponible para **[!UICONTROL Sent]** y **[!UICONTROL Bounces + Errors]**.

1. Seleccione una o varias filas y haga clic en el icono **Visualizar** . Se agrega una visualización para reflejar las filas seleccionadas.

   ![](assets/dynamic_report_freeform_5.png)

Ahora puede agregar tantos componentes como necesite y también agregar visualizaciones para proporcionar representaciones gráficas de los datos.
