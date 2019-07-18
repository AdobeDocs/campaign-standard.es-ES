---
title: Edición de consultas
seo-title: Edición de consultas
description: Edición de consultas
seo-description: Cree una población gracias a los filtros y reglas predefinidos.
page-status-flag: no activado nunca
uuid: a 49 c 7739-a 96 c -45 cb -9 ac 5-1 ce 299161 a 97
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: filtrar datos
discoiquuid: 84306 a 1 e -0 d 9 f -44 cc -88 a 7-36 d 7 e 5 b 4 da 1 f
context-tags: Queryfilter, descripción general; audiencia, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Editing queries{#editing-queries}

## About query editor {#about-query-editor}

El editor de consultas es un asistente que permite filtrar los datos contenidos en la base de datos de Adobe Campaign.

Esta función permite crear una población para dirigir mejor a los destinatarios gracias a los filtros y reglas predefinidos.

Varias funcionalidades de aplicación lo utilizan para:

* Create **Query** type **audiences**
* Define **email** targets
* Define populations in **workflow** activities

## Query editor interface {#query-editor-interface}

The query editor is made up of a **Palette** and a **Workspace**.

![](assets/query_editor_overview.png)

### Palette {#palette}

La paleta, situada en la parte izquierda del editor, se divide en dos fichas, que contienen elementos divididos en bloques temáticos. Estas fichas son:

* The **Shortcuts**, available by default, or created by the instance administrator. Aquí encontrará campos, nodos, agrupaciones, vínculos 1-1, vínculos 1-N y otros filtros predefinidos.
* **El Explorador** que permite acceder a todos los campos disponibles en el recurso de destino: nodos, agrupados, vínculos (1-1 y 1-N).

Los elementos contenidos en las fichas deben moverse al espacio de trabajo para configurarse y tener en cuenta la consulta. Depending on the targeting dimension selected (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)), you can:

* Seleccione audiencias o perfiles uno por uno
* Utilizar filtros predefinidos
* Definir reglas simples para los campos de su elección
* Definir reglas avanzadas que permiten aplicar funciones a ciertos campos

### Workspace {#workspace}

El espacio de trabajo es la zona central en la que se pueden configurar y combinar reglas, audiencias y filtros predefinidos de la paleta.

When you move an element from the palette into the workspace, a new window opens and you can start [Creating queries](../../automating/using/editing-queries.md#creating-queries).

## Creating queries {#creating-queries}

El editor de consultas puede utilizarse para definir una audiencia o un perfil de prueba en un mensaje, una población en un flujo de trabajo y crear una audiencia de tipo de consulta.

Queries can be defined in the **[!UICONTROL Audience]** window while creating a delivery or in a **Query** activity while creating a workflow.

1. Mover un elemento de la paleta al espacio de trabajo. Se abre la ventana para editar la regla.

   * For a string or numerical **field**, specify the comparison operator and the value.

      ![](assets/query_editor_audience_definition2.png)

   * For a date or date and time **field**, you can choose to define a specific date, a range between two dates, or a period relative to the query's execution date.

      ![](assets/query_editor_date_field.png)

   * For a Boolean **field**, check the boxes linked to the possible values for the field.
   * For a **grouping** field, select the grouping field on which you want to create the rule, then define the condition in the same way as for the other fields.

      ![](assets/query_editor_audience_definition4.png)

   * For a **1-1** link with another database resource, select a value directly from the table targeted.

      ![](assets/query_editor_audience_definition5.png)

   * For a **1-N** link with another database resource, you can define a sub-query on the fields of this second resource.

      No es necesario especificar una condición secundaria.

      For example, you can only select the **[!UICONTROL Exists]** operator on the profile tracking logs and approve the rule. La regla devolverá todos los perfiles para los que existen registros de seguimiento.

      ![](assets/query_editor_audience_definition6.png)

   * For a **predefined filter**, enter or select the elements you like according to the criteria offered.

      Los administradores pueden crear filtros para facilitar consultas complejas y repetitivas. Estos aparecerán en el editor de consultas en forma de reglas preconfiguradas y limitarán el número de pasos que debe llevar a cabo el usuario.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Puede especificar un nombre para la regla. Esto se muestra como nombre de regla en el espacio de trabajo. Si no se da un nombre a la regla, se muestra una descripción automática de las condiciones.
1. Para combinar los elementos del espacio de trabajo, interbloquélos entre sí para crear diferentes grupos o niveles de grupo. A continuación, puede seleccionar un operador lógico para combinar elementos en el mismo nivel:

   * **[!UICONTROL AND]**: una intersección de dos criterios. Solo se tienen en cuenta los elementos que coinciden con cada criterio.
   * **[!UICONTROL OR]**: una unión de dos criterios. Los elementos que coincidan al menos con uno de los dos criterios se tendrán en cuenta.
   * **[!UICONTROL EXCEPT]**: criterios de exclusión. Los elementos que coincidan con el primer criterio se tendrán en cuenta a menos que también coincidan con el segundo criterio.

1. You can now calculate and preview the number of elements targeted by your query using the ![](assets/count.png) and ![](assets/preview.png) buttons from the action bar.

   ![](assets/query_editor_combining_rules.png)

Si desea modificar un elemento de la consulta, haga clic en el icono Editar. La regla se abre tal como estaba configurada anteriormente y luego puede realizar los ajustes necesarios.

Ahora, las consultas se crean y se definen, lo que permite crear una población para personalizar mejor sus envíos.

**Temas relacionados:**

* [Funciones avanzadas](../../automating/using/advanced-expression-editing.md)
* [Definición de filtros](../../developing/using/configuring-filter-definition.md)

