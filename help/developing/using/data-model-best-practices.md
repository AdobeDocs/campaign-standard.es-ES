---
title: Prácticas recomendadas del modelo de datos en Adobe Campaign Standard
description: Conozca las prácticas recomendadas al diseñar su modelo de datos de Adobe Campaign Standard.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 58d4e02f-3c9a-4e5d-a6aa-fdbcec0d8dda
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1556'
ht-degree: 1%

---

# Prácticas recomendadas del modelo de datos{#data-model-best-practices}

Este documento describe las recomendaciones clave al diseñar el modelo de datos de Adobe Campaign.


>[!NOTE]
>
>Para crear y modificar recursos con el fin de ampliar el modelo de datos predefinido de Adobe Campaign, consulte [esta sección](../../developing/using/key-steps-to-add-a-resource.md).
>
>Puede encontrar una representación del modelo de datos de los recursos integrados en [esta página](../../developing/using/datamodel-introduction.md).

## Información general {#overview}

El sistema Adobe Campaign es extremadamente flexible y se puede ampliar más allá de la implementación inicial. Sin embargo, aunque las posibilidades son infinitas, es fundamental tomar decisiones sabias y construir bases sólidas para empezar a diseñar su modelo de datos.

Este documento proporciona casos de uso comunes y prácticas recomendadas para aprender a diseñar correctamente la herramienta Adobe Campaign.

## Arquitectura del modelo de datos {#data-model-architecture}

Adobe Campaign Standard es un potente sistema de administración de campañas en canales múltiples que puede ayudarle a alinear sus estrategias en línea y sin conexión para crear experiencias personalizadas con los clientes.

### Enfoque centrado en el cliente {#customer-centric-approach}

Aunque la mayoría de los proveedores de servicios de correo electrónico se comunican a los clientes mediante un enfoque centrado en la lista, Adobe Campaign depende de una base de datos relacional para aprovechar una vista más amplia de los clientes y sus atributos.

Este enfoque centrado en el cliente se muestra en el gráfico siguiente. La variable **Perfil** recurso en gris representa la tabla de cliente principal en torno a la cual se está creando todo:

![](assets/customer-centric-data-model.png)

El modelo de datos predeterminado de Adobe Campaign se presenta en esta [sección](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Datos para Adobe Campaign {#data-for-campaign}

¿Qué datos se deben enviar a Adobe Campaign? Es fundamental determinar los datos necesarios para sus actividades de marketing.

>[!NOTE]
>
>Adobe Campaign no es un almacén de datos. Por lo tanto, no intente importar todos los clientes posibles y su información asociada en Adobe Campaign.

Para tomar la decisión de si un atributo sería necesario o no en Adobe Campaign, determine si correspondería a una de estas categorías:
* Atributo utilizado para **segmentación**
* Atributo utilizado para **procesos de administración de datos** (cálculo acumulado, por ejemplo)
* Atributo utilizado para **personalización**
* Atributo utilizado para **creación de informes** (los informes se pueden crear en función de los datos de perfil personalizados)

Si no se incluye en ninguno de estos parámetros, lo más probable es que no necesite este atributo en Adobe Campaign.

### Tipos de datos {#data-types}

Para garantizar una buena arquitectura y un buen rendimiento de su sistema, siga las prácticas recomendadas a continuación para configurar los datos en Adobe Campaign:
* La longitud de un campo de cadena siempre debe definirse con la columna . De forma predeterminada, la longitud máxima en Adobe Campaign es de 255 caracteres, pero Adobe recomienda mantener el campo más corto si ya sabe que el tamaño no superará una longitud más corta.
* Es aceptable tener un campo más corto en Adobe Campaign que en el sistema de origen si está seguro de que el tamaño del sistema de origen se sobreestimó y no se alcanzaría. Esto podría significar una cadena más corta o un número entero menor en Adobe Campaign.

## Configuración de la estructura de datos {#configuring-data-structure}

Esta sección describe las prácticas recomendadas cuando [configuración de la estructura de datos de un recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

### Identificadores {#identifiers}

Los recursos de Adobe Campaign tienen tres identificadores y es posible añadir un identificador adicional.

En la tabla siguiente se describen estos identificadores y su finalidad.

>[!NOTE]
>
>El nombre para mostrar es el nombre del campo que se muestra al usuario a través de la interfaz de usuario de Adobe Campaign. El nombre técnico es el nombre real del campo en la definición del recurso (y el nombre de la columna de tabla).

| Nombre para mostrar | Nombre técnico | Descripción | Prácticas recomendadas |
|--- |--- |--- |--- |
|  | PKey | <ul><li>La clave PKey es la clave principal física de una tabla Adobe Campaign.</li><li>Este identificador suele ser único para una instancia de Adobe Campaign específica.</li><li>En Adobe Campaign Standard, este valor no es visible para el usuario final (excepto en las direcciones URL).</li></ul> | <ul><li>A través de la función [Sistema de API](../../api/using/get-started-apis.md), es posible recuperar un valor PKey (que es un valor generado/hash, no la clave física).</li><li>No se recomienda utilizarlo para nada más que recuperar, actualizar o eliminar registros mediante API.</li></ul> |
| ID | name o internalName | <ul><li>Esta información es un identificador único de un registro de una tabla. Este valor se puede actualizar manualmente.</li><li>Este identificador mantiene su valor cuando se implementa en una instancia diferente de Adobe Campaign. Debe tener un nombre diferente al valor generado para poder exportarlo a través de un paquete.</li><li>Esta no es la clave principal real de la tabla.</li></ul> | <ul><li>No utilice caracteres especiales como espacio &quot;&quot;, semicolumna &quot;:&quot; o guión &quot;-&quot;.</li><li>Todos estos caracteres se sustituirían por un guión bajo &quot;_&quot; (carácter permitido). Por ejemplo, &quot;abc-def&quot; y &quot;abc:def&quot; se almacenarían como &quot;abc_def&quot; y se sobrescribirían entre sí.</li></ul> |
| Etiqueta | label | <ul><li>La etiqueta es el identificador comercial de un objeto o registro en Adobe Campaign.</li><li>Este objeto permite espacios y caracteres especiales.</li><li>No garantiza la exclusividad de un registro.</li></ul> | <ul><li>Se recomienda determinar una estructura para las etiquetas de objeto.</li><li>Esta es la solución más fácil de usar para identificar un registro u objeto para un usuario de Adobe Campaign.</li></ul> |
| ID de ACS | acsId | <ul><li>Se puede generar un identificador adicional: el [ID de ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Como el PKey no se puede usar en la interfaz de usuario de Adobe Campaign, esta es una solución para obtener un valor único generado durante la inserción de un registro de perfil.</li><li>El valor solo se puede generar automáticamente si la opción está habilitada en el recurso antes de que se inserte un registro en Adobe Campaign.</li></ul> | <ul><li>Este UUID se puede utilizar como clave de reconciliación.</li><li>Un ID ACS generado automáticamente no se puede utilizar como referencia en un flujo de trabajo o en una definición de paquete.</li><li>Este valor es específico de una instancia de Adobe Campaign.</li></ul> |

### Claves de identificación {#keys}

Cada recurso creado en Adobe Campaign debe tener al menos una [clave de identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Al crear un recurso personalizado, tiene dos opciones:

* Combinación de clave generada automáticamente y clave personalizada interna. Esta opción es interesante si la clave del sistema es una clave compuesta o no un número entero. Los integradores proporcionarán un mayor rendimiento en las mesas grandes y se unirán a otras tablas.
* Uso de la clave principal como clave principal del sistema externo. Esta solución suele ser preferible, ya que simplifica el enfoque para importar y exportar datos, con una clave coherente entre los distintos sistemas.

Las claves de identificación no deben utilizarse como referencia en flujos de trabajo.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Índices {#indexes}

Adobe Campaign agrega automáticamente un [index](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a todas las claves principales e internas definidas en un recurso.

* Adobe recomienda definir índices adicionales, ya que puede mejorar el rendimiento.
* Sin embargo, no agregue demasiados índices ya que utilizan espacio en la base de datos. Muchos índices también pueden tener un impacto negativo en el rendimiento.
* Seleccione cuidadosamente los índices que deben definirse.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Vínculos {#links}

La definición de vínculos con otros recursos se muestra en [esta sección](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Aunque es posible unir cualquier tabla en un flujo de trabajo, Adobe recomienda definir vínculos comunes entre los recursos directamente en la definición de la estructura de datos.
* El vínculo se debe definir en alineación con los datos reales de las tablas. Una definición incorrecta podría afectar a los datos recuperados mediante vínculos, por ejemplo, duplicando registros de forma inesperada.
* Asigne un nombre al vínculo de forma coherente con el nombre del recurso: el nombre del vínculo debería ayudar a comprender cuál es la tabla distante.
* No asigne a un vínculo el nombre &quot;id&quot; como sufijo. Por ejemplo, asígnele el nombre &quot;transaction&quot; en lugar de &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Rendimiento {#performance}

Para garantizar un mejor rendimiento en cualquier momento, siga las prácticas recomendadas a continuación.

### Recomendaciones generales {#general-recommendations}

* Evite utilizar operaciones como &quot;CONTIENE&quot; en consultas. Si sabe para qué se espera y desea que se filtre, aplique la misma condición con un &quot;EQUAL TO&quot; u otros operadores de filtro específicos.
* Evite unirse a campos no indexados al crear datos en flujos de trabajo.
* Intente asegurarse de que los procesos como la importación y exportación se producen fuera del horario laboral.
* Asegúrese de que haya una programación para todas las actividades diarias y cumpla con la programación.
* Si uno o varios de los procesos diarios fallan y si es obligatorio ejecutarlo ese mismo día, asegúrese de que no haya procesos conflictivos en ejecución cuando se inicie el proceso manual, ya que esto podría afectar al rendimiento del sistema.
* Asegúrese de que ninguna de las campañas diarias se ejecuta durante el proceso de importación o cuando se ejecuta cualquier proceso manual.
* Utilice una o varias tablas de referencia en lugar de duplicar un campo en cada fila. Al utilizar pares clave/valor, se prefiere elegir una clave numérica.
* Una cadena corta sigue siendo aceptable. En caso de que las tablas de referencias ya estén implementadas en un sistema externo, reutilizar la misma facilitará la integración de datos con Adobe Campaign.

### Relaciones &quot;uno a varios&quot; {#one-to-many-relationships}

* El diseño de datos afecta a la capacidad de uso y la funcionalidad. Si diseña su modelo de datos con muchas relaciones de uno a varios, a los usuarios les resultará más difícil construir una lógica significativa en la aplicación. La lógica de filtro &quot;uno a varios&quot; puede resultar difícil para los especialistas en marketing que no son técnicos construir y comprender correctamente.
* Es bueno tener todos los campos esenciales en una tabla porque facilita a los usuarios la creación de consultas. A veces también es bueno para el rendimiento duplicar algunos campos entre tablas si puede evitar una unión.
* Algunas funcionalidades integradas no podrán hacer referencia a relaciones &quot;uno a varios&quot;, por ejemplo, la fórmula de Ponderación de ofertas y los Envíos.

### Tablas grandes {#large-tables}

A continuación se indican algunas prácticas recomendadas que deben seguirse al diseñar el modelo de datos con tablas grandes y uniones complejas.

* Reduzca el número de columnas, especialmente identificando aquellas que no se utilizan.
* Optimice las relaciones del modelo de datos evitando las uniones complejas, como las uniones en varias condiciones o varias columnas.
* Para las claves de unión, utilice siempre datos numéricos en lugar de cadenas de caracteres.
* Reduzca al máximo la profundidad de la retención de registros. Si necesita un historial más profundo, puede acumular cálculos y/o administrar tablas de registro personalizadas para almacenar un historial más grande.
