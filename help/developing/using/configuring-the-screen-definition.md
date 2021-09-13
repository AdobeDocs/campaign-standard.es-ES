---
title: Configuración de la definición de pantalla
description: Obtenga información sobre la definición de nuevas pantallas de Adobe Campaign en función de la estructura de datos de recursos.
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
context-tags: cusResource,main
feature: Data Model
role: Developer
level: Experienced
exl-id: dc45f487-7502-478d-a2b3-51669cc6b225
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 100%

---

# Configuración de la definición de pantalla{#configuring-the-screen-definition}

Al crear un recurso o al añadir campos nuevos a un recurso existente, puede definir cómo desea que aparezcan en la interfaz.

Este paso no es obligatorio, ya que aún puede rellenar el recurso y acceder a sus datos a través de flujos de trabajo, audiencias y API de REST.

En la pestaña **[!UICONTROL Screen definition]**, puede:

* Añadir el acceso al recurso personalizado en el panel de navegación.
* Personalizar la forma en que se presenta la lista de elementos que conforman el recurso.
* Definir la forma en que se muestra la vista de detalles de cada elemento del recurso.

## Habilitación del acceso desde el menú de navegación {#enabling-access-from-the-navigation-menu}

Si desea que el recurso tenga una pantalla dedicada, puede activarla en el menú de navegación.

1. Desde la pestaña **[!UICONTROL Screen definition]** del recurso, despliegue la sección **[!UICONTROL Navigation]**.
1. Marque la casilla **[!UICONTROL Add an entry in the 'Client data' section]** para permitir el acceso a este recurso desde el panel de navegación.

   ![](assets/schema_extension_19.png)

El recurso aparece como una entrada secundaria dentro de la sección **[!UICONTROL Client data]**.

## Definición de la configuración de lista predeterminada {#defining-the-default-list-configuration}

La sección **[!UICONTROL List configuration]** de la definición de pantalla permite definir las columnas y la información que se muestran de forma predeterminada en la descripción general de un recurso.

1. Marque la casilla **[!UICONTROL Customize the list configuration]** para definir la forma en que se muestran las columnas del recurso.
1. Utilice el botón **[!UICONTROL Create element]** para seleccionar un campo de los que ha creado.
1. El campo creado se muestra en la lista. Puede editar la etiqueta y el ancho.

   ![](assets/schema_extension_20.png)

1. En la sección **[!UICONTROL Simple search]**, marque la casilla **[!UICONTROL Specify the fields to be taken into account in the search]** para definir qué campos se incluyen en la búsqueda.

   >[!IMPORTANT]
   >
   >Esta configuración reemplaza los campos utilizados en la búsqueda predeterminada.

1. En la sección **[!UICONTROL Advanced filtering]**, marque la casilla **[!UICONTROL Add search fields]** para añadir campos adicionales más allá del campo de búsqueda simple. Por ejemplo, si selecciona el campo “fecha” de los campos que ha creado, el usuario puede realizar una búsqueda que solo haga referencia a la fecha.
1. Puede modificar el orden de los campos para los dos tipos de búsqueda.
1. Para una búsqueda avanzada, puede añadir campos que enlacen a un recurso vinculado. Estos filtros aparecen en el menú **[!UICONTROL Search]** de la pantalla generada.

La pantalla de información general del recurso ya está definida.

## Definición de la configuración de la pantalla de detalles {#defining-the-detail-screen-configuration}

La sección **[!UICONTROL Detail screen configuration]** de la definición de pantalla permite definir las columnas y la información que se muestran en la pantalla de detalles de cada elemento del recurso.

1. Despliegue la sección **[!UICONTROL Detail screen configuration]** y marque la casilla de verificación **[!UICONTROL Define a detail screen]** para configurar la pantalla que corresponde a cada elemento del recurso. Si no marca esta casilla, no se podrá acceder a la vista detallada de los elementos de este recurso.
1. Puede añadir todos los campos del recurso personalizado con un solo clic. Para ello, haga clic en el icono ![](assets/addallfieldsicon.png) o utilice el botón **[!UICONTROL Add an element]**.
1. Seleccione un elemento de los creados para este recurso y especifique un tipo de campo:

   * **[!UICONTROL Input field]**: es un campo editable.
   * **[!UICONTROL Value]**: es un campo de solo lectura.
   * **[!UICONTROL List]**: es una tabla.
   * **[!UICONTROL Separator]**: divide los elementos en categorías.

   ![](assets/schema_extension_23.png)

1. El elemento añadido se muestra en la lista. Puede editar la etiqueta.

   ![](assets/schema_extension_22.png)

1. Añada tantos **[!UICONTROL Separator]** como sea necesario para dividir los elementos en distintas categorías.

   Esto le permite mostrar el separador para organizar mejor las ventanas.

   ![](assets/schema_extension_25.png)

La pantalla de detalles del recurso ya está configurada.

## Acciones en la sección de datos {#actions-on-data-section}

Esta configuración le permite mostrar una barra de control en la pantalla de recursos personalizada. Hay tres opciones disponibles:

![](assets/schema_extension_actions.png)

* **[!UICONTROL Authorize creating]**: esta opción permite activar la creación de elementos del recurso. Por lo tanto, el usuario puede añadir registros adicionales.

   >[!NOTE]
   >
   >Primero debe activar la pantalla de detalles vinculada al recurso para que esta opción esté disponible.

* **[!UICONTROL Authorize duplicating]**: esta opción permite activar registros duplicados vinculados al recurso personalizado.
* **[!UICONTROL Authorize deleting]**: esta opción permite activar la eliminación de registros vinculados al recurso personalizado.
