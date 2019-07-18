---
title: Configuración de la definición de pantalla
seo-title: Configuración de la definición de pantalla
description: Configuración de la definición de pantalla
seo-description: Descubra cómo definir nuevas pantallas de Adobe Campaign basándose en la estructura de datos de recursos.
page-status-flag: no activado nunca
uuid: 40848197-b 1 a 0-4018-bfc 3-7 df 64 fb 83307
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 9 dabb 328-ac 0 c -49 fd -8996-8 d 56341 ee 7 ac
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b3291f7c0cbede6a3180ad4a4ab8a365720f5031

---


# Configuring the screen definition{#configuring-the-screen-definition}

Al crear un recurso o al agregar campos nuevos a un recurso existente, puede definir cómo desea que aparezcan en la interfaz.

Este paso no es obligatorio porque aún podrá rellenar el recurso y acceder a sus datos a través de flujos de trabajo, audiencias y API de REST.

In the **[!UICONTROL Screen definition]** tab, you can:

* Agregar acceso al recurso personalizado en el panel de navegación
* Personalice la forma en que se presenta la lista de elementos que componen el recurso
* Definir la manera en que se muestra la vista de detalles de cada elemento del recurso

## Enabling access from the navigation menu {#enabling-access-from-the-navigation-menu}

Si desea que su recurso tenga una pantalla dedicada, puede hacerlo disponible en el menú de navegación.

1. From the **[!UICONTROL Screen definition]** tab of the resource, unfold the **[!UICONTROL Navigation]** section.
1. Check the **[!UICONTROL Add an entry in the 'Client data' section]** box to allow access to this resource from the navigation pane.

   ![](assets/schema_extension_19.png)

The resource will appear as a sub-entry within the **[!UICONTROL Client data]** section.

## Defining the default list configuration {#defining-the-default-list-configuration}

The **[!UICONTROL List configuration]** section of the screen definition lets you define the columns and information that will be displayed by default in the overview of a resource.

1. Check the **[!UICONTROL Customize the list configuration]** box to define the way the columns of the resource are displayed.
1. Use the **[!UICONTROL Create element]** button to select a field from those that you have created.
1. El campo creado se muestra en la lista. Puede editar su etiqueta y su ancho.

   ![](assets/schema_extension_20.png)

1. In the **[!UICONTROL Simple search]** section, check the **[!UICONTROL Specify the fields to be taken into account in the search]** to define which fields will be included in the search.

   >[!CAUTION]
   >
   >Esta configuración reemplaza los campos utilizados en la búsqueda predeterminada.

1. In the **[!UICONTROL Advanced filtering]** section, check the **[!UICONTROL Add search fields]** box to add additional fields beyond the simple search field. Por ejemplo, si selecciona el campo "fecha" de los campos que ha creado, el usuario podrá realizar una búsqueda que solo hace referencia a la fecha.
1. Puede modificar el orden de los campos para los dos tipos de búsqueda.
1. Para una búsqueda avanzada, puede agregar campos que se vinculen a un recurso vinculado. These filters appear in the **[!UICONTROL Search]** menu of the generated screen.

Ahora se ha definido la pantalla de información general del recurso.

## Defining the detail screen configuration {#defining-the-detail-screen-configuration}

The **[!UICONTROL Detail screen configuration]** section of the screen definition lets you define the columns and information that will be displayed in the detail screen of each element of the resource.

1. Unfold the **[!UICONTROL Detail screen configuration]** section and check the **[!UICONTROL Define a detail screen]** to configure the screen that corresponds to each element of the resource. Si no marca esta casilla, la vista de detalles de los elementos de este recurso no será accesible.
1. Puede agregar todos los campos desde el recurso personalizado con un solo clic. To do this, click the ![](assets/addallfieldsicon.png) icon or use the **[!UICONTROL Add an element]** button.
1. Seleccione un elemento de los creados para este recurso y especifique un tipo de campo:

   * **[!UICONTROL Input field]**: es un campo editable.
   * **[!UICONTROL Value]**: es un campo de solo lectura.
   * **[!UICONTROL List]**: es una tabla.
   * **[!UICONTROL Separator]**: divide los elementos en categorías.
   ![](assets/schema_extension_23.png)

1. El elemento agregado se muestra en la lista. Puede editar su etiqueta.

   ![](assets/schema_extension_22.png)

1. Add as many **[!UICONTROL Separator]** as needed to split your elements into different categories.

   Esto le permite mostrar separador para organizar mejor las ventanas.

   ![](assets/schema_extension_25.png)

La pantalla de detalles del recurso ahora está configurada.

## Actions on data section {#actions-on-data-section}

Esta configuración permite mostrar una barra de control en la pantalla de recursos personalizados. Existen tres opciones disponibles:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: esta opción permite activar la creación de elementos del recurso. Por lo tanto, el usuario puede agregar registros adicionales.

   >[!NOTE]
   >
   >Primero debe activar la pantalla de detalles vinculada al recurso para que esta opción esté disponible.

* **[!UICONTROL Authorize duplicating]**: esta opción permite activar la duplicación de registros vinculados al recurso personalizado.
* **[!UICONTROL Authorize deleting]**: esta opción permite activar la eliminación de registros vinculados al recurso personalizado.

