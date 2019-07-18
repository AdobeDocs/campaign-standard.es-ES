---
title: Personalización de listas
seo-title: Personalización de listas
description: Personalización de listas
seo-description: '" Obtenga información sobre cómo personalizar visualización y actuar en pantallas de lista en Adobe Campaign Standard: ordenar, filtrar, eliminar o duplicar elementos. Enumera las pantallas de uno o varios recursos determinados. "'
page-status-flag: no activado nunca
uuid: 3350583 c -91 ca -4 ea 5-ac 14-6 b 6 f 11 c 4 a 64 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: descubrir la interfaz
discoiquuid: 4 ba 4 f 766-fdee -4 ff 0-8 fe 4-0612 ed 2 b 69 a 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Customizing lists{#customizing-lists}

**Las pantallas de lista** permiten mostrar elementos de uno o varios recursos determinados.

Adobe Campaign tiene dos tipos de listas:

* A **homogeneous** list, which is when it contains a single type of resource. Por ejemplo, la lista de perfiles solo contiene perfiles.
* A **heterogeneous** list, which is when it contains several types of resources. Por ejemplo: la lista de actividades de mercadotecnia contiene páginas de aterrizaje, flujos de trabajo, correos electrónicos, SMS, etc.

Las listas se muestran en columnas. Cada columna puede ordenarse de forma ascendente o descendente de una en una.

Los elementos de una lista tienen una casilla de verificación que le permite seleccionarlos. Al seleccionar uno o varios elementos, puede realizar varias acciones, como editar, duplicar y eliminar estos elementos.

When hovering over an element in the list, **quick actions**. Estas acciones permiten al usuario realizar varias acciones en el elemento sobre el que se pasa el ratón, como editar, seleccionar, eliminar o mostrar detalles.

![](assets/overview_list_quickactions.png)

También puede configurar si las columnas de una lista se van a mostrar o no. Para agregar o eliminar columnas:

1. Make sure that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Go to the list configuration window by selecting the ![](assets/columnsettings.png) button in the action bar.

   ![](assets/list_configuration1.png)

1. Agregue las columnas que desee incluir en la lista. To do this, select a column from the left-hand side of the window, then use the ![](assets/arrowright.png) button from the action bar to add a column.

   Las columnas seleccionables corresponden al recurso de lista.

   Agregue la clasificación de forma predeterminada para cada columna agregada.

   * **[!UICONTROL NO]**: Sin ordenar la columna
   * **[!UICONTROL ASC]**: Aplica una ordenación ascendente (ascendente) en la columna
   * **[!UICONTROL DESC]**: Aplica una ordenación descendente (descendente) en la columna.

1. Elimine las columnas que no desee que se muestren marcando las casillas correspondientes a las columnas que desee eliminar. Then, use the ![](assets/delete.png) button from the action bar to confirm deleting them.
1. Una vez que la lista contenga las columnas correctas, puede cambiar el orden en que se muestran en la lista marcando las columnas que desee mover. Then, use the ![](assets/arrowdown.png) and ![](assets/arrowup.png) arrows.
1. Confirm your list configuration by selecting **[!UICONTROL OK]**.

La lista ahora se muestra como la ha configurado.
