---
title: Prácticas recomendadas del modelo de datos en Adobe Campaign Standard
description: Conozca las prácticas recomendadas al diseñar el modelo de datos de Adobe Campaign Standard.
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
>Para crear y modificar recursos para ampliar el modelo de datos predefinido de Adobe Campaign, consulte [esta sección](../../developing/using/key-steps-to-add-a-resource.md).
>
>Puede encontrar una representación del modelo de datos de los recursos integrados en [esta página](../../developing/using/datamodel-introduction.md).

## Información general {#overview}

El sistema Adobe Campaign es extremadamente flexible y se puede ampliar más allá de la implementación inicial. Sin embargo, aunque las posibilidades son infinitas, es fundamental tomar decisiones sabias y construir bases sólidas para empezar a diseñar el modelo de datos.

Este documento proporciona casos de uso comunes y prácticas recomendadas para aprender a crear correctamente la herramienta Adobe Campaign.

## Arquitectura del modelo de datos {#data-model-architecture}

Adobe Campaign Standard es un potente sistema de administración de campañas en canales múltiples que le ayuda a alinear sus estrategias en línea y sin conexión para crear experiencias personalizadas con los clientes.

### Enfoque centrado en el cliente {#customer-centric-approach}

Aunque la mayoría de los proveedores de correo electrónico se comunican con los clientes mediante un enfoque centrado en listas, Adobe Campaign depende de una base de datos relacional para aprovechar una vista más amplia de los clientes y sus atributos.

Este enfoque centrado en el cliente se muestra en el gráfico siguiente. El **Perfil** el recurso en gris representa la tabla principal cliente en torno a la cual se está creando todo:

![](assets/customer-centric-data-model.png)

El modelo de datos predeterminado de Adobe Campaign se muestra en esta sección [sección](../../developing/using/datamodel-introduction.md).

<!--You can find a datamodel representation for the out-of-the-box resources [here](../../developing/using/datamodel-introduction.md).-->

<!--### What is a customer? {#customer-definition}

If you have customer data in more than one system, you need to determine which solution will allow you to identify records as one person. This work might require rules, eventually a match and merge processes to determine the primary record. This primary record should be the one sent to Adobe Campaign.

While some of this data cleansing might be performed in Adobe Campaign, the recommendation is to run these processes outside and only import clean data in Adobe Campaign. You should keep Campaign as a marketing solution more than a data cleansing tool.

Be able to provide a primary customer record which will be sent to Adobe Campaign.-->

### Datos para Adobe Campaign {#data-for-campaign}

¿Qué datos deben enviarse a Adobe Campaign? Es fundamental determinar los datos necesarios para las actividades de marketing.

>[!NOTE]
>
>Adobe Campaign no es un almacén de datos. Por lo tanto, no intente importar todos los clientes posibles y su información asociada en Adobe Campaign.

Para tomar la decisión de si un atributo sería necesario o no en Adobe Campaign, determine si estaría dentro de una de estas categorías:
* Atributo utilizado para **segmentación**
* Atributo utilizado para **procesos de administración de datos** (cálculo acumulado, por ejemplo)
* Atributo utilizado para **personalización**
* Atributo utilizado para **informe** (los informes se pueden crear en función de datos de perfil personalizados)

Si no entra en ninguna de estas situaciones, lo más probable es que no necesite este atributo en Adobe Campaign.

### Tipos de datos {#data-types}

Para garantizar la buena arquitectura y el rendimiento de su sistema, siga las prácticas recomendadas a continuación para configurar los datos en Adobe Campaign:
* La longitud de un campo de cadena siempre debe definirse con la columna. De forma predeterminada, la longitud máxima de Adobe Campaign es de 255 caracteres, pero Adobe recomienda mantener el campo más corto si ya sabe que el tamaño no excederá una longitud más corta.
* Es aceptable tener un campo más corto en Adobe Campaign que en el sistema de origen si está seguro de que el tamaño en el sistema de origen se ha sobreestimado y no se alcanzaría. Esto podría significar una cadena más corta o un entero más pequeño en Adobe Campaign.

## Configuración de estructura de datos {#configuring-data-structure}

Esta sección describe las prácticas recomendadas cuando [configuración de la estructura de datos de un recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

### Identificadores {#identifiers}

Los recursos de Adobe Campaign tienen tres identificadores y es posible añadir uno adicional.

En la tabla siguiente se describen estos identificadores y su propósito.

>[!NOTE]
>
>El nombre para mostrar es el nombre del campo que se muestra al usuario a través de la interfaz de usuario de Adobe Campaign. El nombre técnico es el nombre real del campo en la definición del recurso (y el nombre de la columna de la tabla).

| Nombre para mostrar | Nombre técnico | Descripción | Prácticas recomendadas |
|--- |--- |--- |--- |
|  | PKey | <ul><li>La clave PK es la clave primaria física de una tabla de Adobe Campaign.</li><li>Este identificador suele ser único para una instancia de Adobe Campaign específica.</li><li>En Adobe Campaign Standard, este valor no es visible para el usuario final (excepto en las direcciones URL).</li></ul> | <ul><li>Mediante el [sistema de API](../../api/using/get-started-apis.md)Sin embargo, es posible recuperar un valor PKey (que es un valor generado/con hash, no la clave física).</li><li>No se recomienda utilizarlo para nada más que recuperar, actualizar o eliminar registros a través de API.</li></ul> |
| ID | name o internalName | <ul><li>Esta información es un identificador único de un registro de una tabla. Este valor se puede actualizar manualmente.</li><li>Este identificador mantiene su valor cuando se implementa en una instancia diferente de Adobe Campaign. Debe tener un nombre diferente al valor generado para que se pueda exportar mediante un paquete.</li><li>Esta no es la clave principal real de la tabla.</li></ul> | <ul><li>No utilice caracteres especiales como el espacio &quot;&quot;, el punto y coma &quot;:&quot; o el guión &quot;-&quot;.</li><li>Todos estos caracteres se sustituirían por un guion bajo &quot;_&quot; (carácter permitido). Por ejemplo, &quot;abc-def&quot; y &quot;abc:def&quot; se almacenarían como &quot;abc_def&quot; y se sobrescribirían mutuamente.</li></ul> |
| Etiqueta | label | <ul><li>La etiqueta es el identificador comercial de un objeto o registro en Adobe Campaign.</li><li>Este objeto permite espacios y caracteres especiales.</li><li>No garantiza la exclusividad de un registro.</li></ul> | <ul><li>Se recomienda determinar una estructura para las etiquetas de objetos.</li><li>Esta es la solución más fácil de usar para identificar un registro u objeto para un usuario de Adobe Campaign.</li></ul> |
| ID de ACS | acsId | <ul><li>Se puede generar un identificador adicional: [ID de ACS](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).</li><li>Como la clave PKey no se puede utilizar en la interfaz de usuario de Adobe Campaign, esta es una solución para obtener un valor único generado durante la inserción de un registro de perfil.</li><li>El valor solo se puede generar automáticamente si la opción está habilitada en el recurso antes de que se inserte un registro en Adobe Campaign.</li></ul> | <ul><li>Este UUID se puede utilizar como clave de reconciliación.</li><li>Un ID ACS generado automáticamente no se puede utilizar como referencia en un flujo de trabajo o en una definición de paquete.</li><li>Este valor es específico de una instancia de Adobe Campaign.</li></ul> |

### Claves de identificación {#keys}

Cada recurso creado en Adobe Campaign debe tener al menos un único [clave identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

<!--Most organizations are importing records from external systems. While the physical key of a resource lies behind the PKey attribute, it is possible to determine a custom key in addition.

This custom key is the actual record primary key in the external system feeding Adobe Campaign.

When an out-of-the-box resource has both an internal auto-generated and an internal custom key, the internal key will be set as a unique index in the physical database table.-->

Al crear un recurso personalizado, tiene dos opciones:

* Una combinación de clave generada automáticamente y clave personalizada interna. Esta opción es interesante si la clave del sistema es una clave compuesta o no un número entero. Los enteros proporcionarán un mayor rendimiento en las tablas grandes y se unirán con otras tablas.
* Uso de la clave principal como clave principal externa del sistema. Esta solución suele ser la preferida, ya que simplifica el método de importación y exportación de datos, con una clave coherente entre los distintos sistemas.

Las claves de identificación no deben utilizarse como referencia en los flujos de trabajo.

<!--For more on defining identification keys, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).-->

### Índices {#indexes}

Adobe Campaign añade automáticamente un [índice](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes) a todas las claves principales e internas definidas en un recurso.

* Adobe recomienda definir índices adicionales, ya que puede mejorar el rendimiento.
* Sin embargo, no agregue demasiados índices, ya que utilizan espacio en la base de datos. Numerosos índices también pueden tener un impacto negativo en el rendimiento.
* Seleccione cuidadosamente los índices que debe definir.

<!--For more on defining indexes, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes).

When you are performing an initial import with very high volumes of data insert in Adobe Campaign database, it is recommended to run that import without custom indexes at first. It will allow to accelerate the insertion process. Once you’ve completed this important import, it is possible to enable the index(es).-->

### Vínculos {#links}

La definición de vínculos con otros recursos se presenta en [esta sección](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).

* Aunque es posible unir cualquier tabla en un flujo de trabajo, Adobe recomienda definir vínculos comunes entre recursos directamente en la definición de la estructura de datos.
* El vínculo debe definirse en consonancia con los datos reales de las tablas. Una definición incorrecta podría afectar a los datos recuperados mediante vínculos como, por ejemplo, la duplicación inesperada de registros.
* Asigne un nombre al vínculo que sea coherente con el nombre del recurso: el nombre del vínculo debe ayudar a comprender qué es la tabla distante.
* No asigne un nombre a un vínculo con &quot;id&quot; como sufijo. Por ejemplo, asígnele el nombre &quot;transaction&quot; en lugar de &quot;transactionId&quot;.

<!--For more on defining links with other resources, see [this section](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources).-->

## Rendimiento {#performance}

Para garantizar un mejor rendimiento en cualquier momento, siga las prácticas recomendadas a continuación.

### Recomendaciones generales {#general-recommendations}

* Evite utilizar operaciones como &quot;CONTAINS&quot; en consultas. Si sabe lo que se espera y desea filtrar, aplique la misma condición con un operador &quot;EQUAL TO&quot; u otro operador de filtro específico.
* Evite unirse a campos no indexados al crear datos en flujos de trabajo.
* Intente y asegúrese de que los procesos de importación y exportación se produzcan fuera del horario laboral.
* Asegúrese de que haya un horario para todas las actividades diarias y apéguese al horario.
* Si uno o varios de los procesos diarios fallan y si es obligatorio ejecutarlos ese mismo día, asegúrese de que no haya procesos en conflicto ejecutándose cuando se inicie el proceso manual, ya que esto podría afectar el rendimiento del sistema.
* Asegúrese de que ninguna de las campañas diarias se ejecute durante el proceso de importación o cuando se ejecute cualquier proceso manual.
* Utilice una o varias tablas de referencia en lugar de duplicar un campo en cada fila. Al utilizar pares clave/valor, se prefiere elegir una clave numérica.
* Una cadena corta sigue siendo aceptable. Si las tablas de referencias ya están en su lugar en un sistema externo, la reutilización de las mismas facilitará la integración de datos con Adobe Campaign.

### Relaciones &quot;uno a varios&quot; {#one-to-many-relationships}

* El diseño de datos afecta la facilidad de uso y la funcionalidad. Si diseña el modelo de datos con muchas relaciones &quot;uno a varios&quot;, a los usuarios les resulta más difícil construir una lógica significativa en la aplicación. La lógica de filtro uno a varios puede resultar difícil para los especialistas en marketing no técnico de construir y comprender correctamente.
* Es bueno tener todos los campos esenciales en una tabla porque facilita a los usuarios la creación de consultas. A veces también es bueno para el rendimiento duplicar algunos campos entre tablas si se puede evitar una combinación.
* Algunas funcionalidades integradas no podrán hacer referencia a relaciones &quot;uno a varios&quot;, por ejemplo, la fórmula de ponderación de oferta y las entregas.

### Mesas grandes {#large-tables}

A continuación se describen algunas prácticas recomendadas que deben seguirse al diseñar el modelo de datos con tablas grandes y uniones complejas.

* Reduzca la cantidad de columnas, especialmente identificando las que no se utilizan.
* Optimice las relaciones del modelo de datos evitando uniones complejas, como uniones en varias condiciones o varias columnas.
* Para las claves de combinación, utilice siempre datos numéricos en lugar de cadenas de caracteres.
* Reduzca al máximo la profundidad de la retención de registros. Si necesita un historial más profundo, puede acumular cálculos o gestionar tablas de registro personalizadas para almacenar un historial más grande.
