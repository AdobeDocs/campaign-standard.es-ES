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
source-git-commit: bb65cbf808a95e8b42b2a682b7c0a9cc6225d920

---


# Edición de consultas{#editing-queries}

## Acerca del editor de consultas {#about-query-editor}

El editor de consultas es un asistente que permite filtrar los datos contenidos en la base de datos de Adobe Campaign.

Esta función permite crear una población para dirigir mejor a los destinatarios gracias a los filtros y reglas predefinidos.

Varias funcionalidades de aplicación lo utilizan para:

* Crear **audiencias** de tipo **de consulta**
* Definición **de objetivos de correo electrónico**
* Definición de poblaciones en **actividades de flujo de trabajo**

## Interfaz del editor de consultas {#query-editor-interface}

El editor de consultas se compone de una **paleta** y **un espacio de trabajo**.

![](assets/query_editor_overview.png)

### Paleta {#palette}

La paleta, situada en la parte izquierda del editor, se divide en dos fichas, que contienen elementos divididos en bloques temáticos. Estas fichas son:

* Los **accesos directos**, disponibles de forma predeterminada o creados por el administrador de instancias. Aquí encontrará campos, nodos, agrupaciones, vínculos 1-1, vínculos 1-N y otros filtros predefinidos.
* **El Explorador** que permite acceder a todos los campos disponibles en el recurso de destino: nodos, agrupados, vínculos (1-1 y 1-N).

Los elementos contenidos en las fichas deben moverse al espacio de trabajo para configurarse y tener en cuenta la consulta. Según la dimensión de objetivo seleccionada (consulte [Dimensiones y recursos de objetivos](../../automating/using/query.md#targeting-dimensions-and-resources)), puede:

* Seleccione audiencias o perfiles uno por uno
* Utilizar filtros predefinidos
* Definir reglas simples para los campos de su elección
* Definir reglas avanzadas que permiten aplicar funciones a ciertos campos

### Espacio de trabajo {#workspace}

El espacio de trabajo es la zona central en la que se pueden configurar y combinar reglas, audiencias y filtros predefinidos de la paleta.

Cuando mueve un elemento de la paleta al espacio de trabajo, se abre una ventana nueva y puede empezar [a crear consultas](../../automating/using/editing-queries.md#creating-queries).

## Creación de consultas {#creating-queries}

El editor de consultas puede utilizarse para definir una audiencia o un perfil de prueba en un mensaje, una población en un flujo de trabajo y crear una audiencia de tipo de consulta.

Las consultas se pueden definir en **[!UICONTROL Audience]** la ventana al crear una entrega o en una actividad **de consulta** al crear un flujo de trabajo.

1. Mover un elemento de la paleta al espacio de trabajo. Se abre la ventana para editar la regla.

   * Para una cadena o **campo** numérico, especifique el operador de comparación y el valor.

      ![](assets/query_editor_audience_definition2.png)

   * Para una fecha o **un campo** de fecha y hora, puede elegir definir una fecha específica, un intervalo entre dos fechas o un período relativo a la fecha de ejecución de la consulta.

      ![](assets/query_editor_date_field.png)

   * En un **campo** booleano, marque las casillas vinculadas a los valores posibles del campo.
   * Para un **campo de agrupación** , seleccione el campo de agrupación en el que desee crear la regla y, a continuación, defina la condición del mismo modo que para los demás campos.

      ![](assets/query_editor_audience_definition4.png)

   * Para un **vínculo 1-1** con otro recurso de base de datos, seleccione un valor directamente de la tabla objetivo.

      ![](assets/query_editor_audience_definition5.png)

   * Para un **vínculo 1-N** con otro recurso de base de datos, puede definir una subconsulta en los campos de este segundo recurso.

      No es necesario especificar una condición secundaria.

      Por ejemplo, solo puede seleccionar el **[!UICONTROL Exists]** operador en los registros de seguimiento de perfiles y aprobar la regla. La regla devolverá todos los perfiles para los que existen registros de seguimiento.

      ![](assets/query_editor_audience_definition6.png)

   * Para un **filtro** predefinido, introduzca o seleccione los elementos que desee de acuerdo con los criterios ofrecidos.

      Los administradores pueden crear filtros para facilitar consultas complejas y repetitivas. Estos aparecerán en el editor de consultas en forma de reglas preconfiguradas y limitarán el número de pasos que debe llevar a cabo el usuario.

      ![](assets/query-editor_filter_email-audience_filter.png)

1. Puede especificar un nombre para la regla. Esto se muestra como nombre de regla en el espacio de trabajo. Si no se da un nombre a la regla, se muestra una descripción automática de las condiciones.
1. Para combinar los elementos del espacio de trabajo, interbloquélos entre sí para crear diferentes grupos o niveles de grupo. A continuación, puede seleccionar un operador lógico para combinar elementos en el mismo nivel:

   * **[!UICONTROL AND]**: una intersección de dos criterios. Solo se tienen en cuenta los elementos que coinciden con cada criterio.
   * **[!UICONTROL OR]**: una unión de dos criterios. Los elementos que coincidan al menos con uno de los dos criterios se tendrán en cuenta.
   * **[!UICONTROL EXCEPT]**: criterios de exclusión. Los elementos que coincidan con el primer criterio se tendrán en cuenta a menos que también coincidan con el segundo criterio.

1. Ahora puede calcular y obtener una vista previa del número de elementos dirigidos a la consulta utilizando los botones ![](assets/count.png) y los ![](assets/preview.png) botones de la barra de acciones.

   ![](assets/query_editor_combining_rules.png)

Si desea modificar un elemento de la consulta, haga clic en el icono Editar. La regla se abre tal como estaba configurada anteriormente y luego puede realizar los ajustes necesarios.

Ahora, las consultas se crean y se definen, lo que permite crear una población para personalizar mejor sus envíos.

**Temas relacionados:**

* [Funciones avanzadas](../../automating/using/advanced-expression-editing.md)
* [Definición de filtros](../../developing/using/configuring-filter-definition.md)
* [Caso de uso: Crear una entrega de correo electrónico una sola semana](../../automating/using/workflow-weekly-offer.md)
* [Caso de uso: Creación de una entrega segmentada en la ubicación](../../automating/using/workflow-segmentation-location.md)
* [Caso de uso: Creación de entregas con un complemento](../../automating/using/workflow-created-query-with-complement.md)
* [Caso de uso: Volver a configurar el flujo de trabajo envío de una nueva entrega a no abiertos](../../automating/using/workflow-cross-channel-retargeting.md)
