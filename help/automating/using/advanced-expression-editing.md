---
title: Edición avanzada de expresiones
description: El asistente de edición de consultas le permite definir expresiones avanzadas.
page-status-flag: nunca activado
uuid: a635f99-27ce-41e0-a88c-8a3882e31efe
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: filter-data
discoiquuid: 4375153c-0621-4d4c-bfcc-66d157f04f6c
context-tags: queryFilter,información general;audience,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Edición avanzada de expresiones{#advanced-expression-editing}

## Acerca de la edición avanzada de expresiones {#about-advanced-expression-editing}

La edición de una expresión implica la introducción manual de condiciones para formar una regla.

Este modo le permite utilizar funciones avanzadas. Estas funciones permiten manipular los valores utilizados para realizar consultas específicas, como la manipulación de fechas, cadenas, campos numéricos, ordenación, etc.

También es posible utilizar variables events al editar expresiones. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

Puede editar expresiones para:

* Defina una consulta mediante la **[!UICONTROL Advanced mode]** opción que está disponible cuando se agrega una regla.

   ![](assets/expression_editor_2.png)

* Edite una expresión en un flujo de trabajo. Por ejemplo, para agregar datos adicionales a una actividad.
* Edite una condición de visibilidad para definir cómo se muestra un bloque en el editor de contenido HTML. En este caso, la expresión se edita en formato JavaScript y no ofrece el uso de funciones avanzadas como estándar.

## Editar una expresión {#edit-an-expression}

La edición de expresiones avanzadas permite definir manualmente una expresión que se adapte específicamente a sus necesidades.

La edición de expresiones se puede utilizar en la ventana Audiencia al crear un correo electrónico o en una actividad de consulta al crear un flujo de trabajo.

1. Acceda a la ventana de edición de expresiones mediante uno de los métodos detallados en la sección Edición [avanzada de expresiones](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) Acerca de. Incluye los siguientes elementos:

   * Campo de entrada en el que se define la expresión.
   * Lista de campos disponibles que se pueden utilizar en la expresión y que corresponden a la dimensión de objetivo de la consulta (consulte [Segmentación de dimensiones y recursos](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * Lista de funciones disponibles, ordenadas por categoría.
   ![](assets/expression_editor_1.png)

1. Edite la expresión introduciendo una expresión directamente en el campo correspondiente o utilizando las listas de campos y funciones disponibles.

   Al hacer doble clic en un campo o una expresión, se agrega a la expresión en la que se coloca el cursor.

   Es posible utilizar variables de eventos de flujos de trabajo para crear una expresión. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

1. Asigne un nombre específico a la regla si es necesario. El nombre introducido aparecerá como nombre de regla en el espacio de trabajo del editor de consultas.

Editar una expresión le permite personalizar la expresión Audiencias para que se dirija a su población según sea necesario.

**Temas relacionados:**

* [Sintaxis de expresión](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Sintaxis de expresión {#expression-syntax}

### Sintaxis estándar {#standard-syntax}

Las expresiones estándar están formadas por una o varias condiciones que respetan los siguientes elementos de sintaxis:

* Cada condición adopta la forma de **&lt;valor1&gt; &lt;operador de comparación&gt; &lt;valor2&gt;** por el cual:

   * **&lt;value1&gt;** es un campo o una función. Por ejemplo, **@created** para la fecha en que se creó un perfil o **Year(@created)** para el año en que se creó un perfil.
   * **&lt;operador de comparación&gt;** es uno de los operadores enumerados en la sección Operadores [de](../../automating/using/advanced-expression-editing.md#comparison-operators) comparación. Este operador define el método de comparación entre **&lt;valor1&gt;** y **&lt;valor2&gt;**.
   * **&lt;value2&gt;** es un campo, una función o un valor introducido manualmente.
   >[!NOTE]
   >
   >Los datos de tipo **&lt;valor1&gt;** y **&lt;valor2&gt;** deben ser idénticos. Por ejemplo, si **&lt;valor1&gt;** es una fecha, entonces **&lt;valor2&gt;** también debe ser una fecha.

* Si desea usar varias condiciones, se pueden combinar con operadores lógicos.

   * **[!UICONTROL AND]**:: se intersectan dos condiciones.
   * **[!UICONTROL OR]**:: se combinan dos condiciones.

Por ejemplo:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

En este ejemplo, los perfiles cuya fecha de creación está en el mes y año actuales están segmentados.

### Sintaxis de JavaScript {#javascript-syntax}

Al definir las condiciones de visibilidad de un bloque de tipo de texto del editor de contenido HTML, debe utilizar una expresión con sintaxis de tipo JavaScript.

Las expresiones JavaScript están formadas por una o varias condiciones y utilizan los siguientes elementos de sintaxis:

* Cada condición adopta la forma de **&lt;context&gt; &lt;operador de comparación&gt; &lt;valor2&gt;** mediante la cual:

   * **&lt;context&gt;** es un campo o una función que le permite especificar el contexto. Por ejemplo, **context.profile.@email** para la dirección de correo electrónico de un perfil o **context.profile.firstName.length()** para el número de caracteres del nombre de un perfil.
   * **&lt;operador de comparación&gt;** es uno de los operadores enumerados en la sección Operadores [de](../../automating/using/advanced-expression-editing.md#comparison-operators) comparación. Este operador define el método de comparación entre **&lt;context&gt;** y **&lt;value2&gt;**.
   * **&lt;value2&gt;** es un campo, una función o un valor introducido manualmente.
   >[!NOTE]
   Los datos de tipo **&lt;context&gt;** y **&lt;value2&gt;** deben ser idénticos. Por ejemplo, si **&lt;context&gt;** es una fecha, entonces **&lt;value2&gt;** también debe ser una fecha.

* Si desea usar varias condiciones, se pueden combinar con operadores lógicos.

   * **[!UICONTROL &&]**:: se intersectan dos condiciones.
   * **[!UICONTROL ||]**:: se combinan dos condiciones.

Por ejemplo:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

En este ejemplo, los perfiles de más de 21 años de edad y cuyo nombre se ha proporcionado (simbolizado por el hecho de que el campo **firstName** contiene al menos un carácter).

## Operadores de comparación {#comparison-operators}

Para algunas reglas, el editor de consultas permite elegir un valor para definir la condición.

Las condiciones deben vincularse a los valores mediante uno de los siguientes operadores.

<table> 
 <thead> 
  <tr> 
   <th> Operador<br /> </th> 
   <th> Sintaxis estándar<br /> </th> 
   <th> Sintaxis de JavaScript<br /> </th> 
   <th> Descripción<br /> </th> 
   <th> Ejemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Igual a</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> El primer valor debe ser completamente idéntico al segundo.<br /> </td> 
   <td> <strong>@lastName = Martin</strong> recupera perfiles cuyo apellido es 'Martin', con sólo estos caracteres idénticos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mayor que</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> El primer valor debe ser categóricamente mayor que el segundo.<br /> </td> 
   <td> <strong>@age &gt; 50</strong> recupera perfiles mayores a '50', así que '51', '52', etc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> El primer valor debe ser categóricamente menor que el segundo.<br /> </td> 
   <td> <strong>@created &lt; DaysAgo(100)</strong> recupera todos los perfiles creados en la base de datos hace menos de 100 días.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mayor o igual que</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> El primer valor debe ser mayor o igual que el segundo valor.<br /> </td> 
   <td> <strong>@age &gt;= 30</strong> recupera perfiles de 30 años o más.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor o igual que</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> El primer valor debe ser menor o igual que el segundo valor.<br /> </td> 
   <td> <strong>@age &lt;= 60</strong> recupera perfiles de 60 años o menos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diferente </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> El primer valor debe ser diferente del segundo.<br /> </td> 
   <td> <strong>@language != English</strong> recupera perfiles que no se han definido como de habla inglesa.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contiene</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/D<br /> </td> 
   <td> El primer valor debe contener el segundo valor.<br /> </td> 
   <td> <strong>@domain IN mail</strong>. Aquí se devuelven todos los nombres de dominio con el valor 'mail' en el resultado. En consecuencia, el nombre de dominio 'gmail.com' formará parte de los resultados devueltos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Me gusta</span><br /> </td> 
   <td> COMO<br /> </td> 
   <td> N/D<br /> </td> 
   <td> <span class="uicontrol">Como</span> es muy similar al operador <span class="uicontrol">Contiene</span> . Permite insertar un carácter comodín <span class="uicontrol">%</span> en el valor que se está buscando.<br /> </td> 
   <td> <strong>@lastName COMO Mart%n</strong>. Aquí, el carácter de sustitución <strong>%</strong> sirve como "bromista" para encontrar el nombre "Martin" en el caso hipotético de que la ortografía no es correcta.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">No me gusta</span><br /> </td> 
   <td>  NOT<br /> </td> 
   <td> N/D<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. Permite no recuperar el valor introducido. Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@lastName NO es Smi%h</strong>. Aquí, los destinatarios corresponden al nombre 'Smi%h' (por lo que Smith, etc.) no se devuelven como resultado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Está vacío</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/D<br /> </td> 
   <td> El primer valor debe corresponder a un valor vacío.<br /> </td> 
   <td> <strong>@mobilePhone IS NULL</strong> recupera todos los perfiles cuyo número de teléfono móvil no se ha proporcionado.<br /> </td> 
  </tr> 
 </tbody> 
</table>

