---
title: Edición de expresiones avanzadas
seo-title: Edición de expresiones avanzadas
description: Edición de expresiones avanzadas
seo-description: El asistente de edición de consultas permite definir expresiones avanzadas.
page-status-flag: no activado nunca
uuid: a 635 f 999-27 ce -41 e 0-a 88 c -8 a 3882 e 31 efe
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: filtrar datos
discoiquuid: 4375153 c -0621-4 d 4 c-bfcc -66 d 157 f 04 f 6 c
context-tags: Queryfilter, descripción general; audiencia, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Advanced expression editing{#advanced-expression-editing}

## About advanced expression editing {#about-advanced-expression-editing}

La edición de una expresión implica introducir condiciones manualmente para formar una regla.

Este modo permite utilizar funciones avanzadas. Estas funciones permiten manipular los valores utilizados para llevar a cabo consultas específicas como manipular fechas, cadenas, campos numéricos, ordenar, etc.

También es posible utilizar variables de eventos al editar expresión. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

Puede editar expresiones para:

* Define a query, via the **[!UICONTROL Advanced mode]** option which is available when a rule is added.

   ![](assets/expression_editor_2.png)

* Editar una expresión en un flujo de trabajo. Por ejemplo, para agregar datos adicionales a una actividad.
* Edite una condición de visibilidad para definir cómo se muestra un bloque en el editor de contenido HTML. En este caso, la expresión se edita en formato JavaScript y no ofrece funciones avanzadas como estándar.

## Edit an expression {#edit-an-expression}

La edición de expresión avanzada permite definir manualmente una expresión que se adapta específicamente a sus necesidades.

La edición de expresiones se puede utilizar en la ventana Audiencia al crear un correo electrónico o en una actividad de consulta al crear un flujo de trabajo.

1. Access the expression editing window via one of the methods detailed in the [About advanced expression editing](../../automating/using/advanced-expression-editing.md#about-advanced-expression-editing) section. Implica los siguientes elementos:

   * Campo de entrada en el que se define la expresión.
   * The list of available fields that can be used in the expression and correspond to the targeting dimension of the query (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)).
   * Lista de funciones disponibles, ordenadas por categoría.
   ![](assets/expression_editor_1.png)

1. Edite la expresión introduciendo una expresión directamente en el campo correspondiente o utilizando las listas de campos y funciones disponibles.

   Al hacer doble clic en un campo o una expresión, se agrega a la expresión en la que se coloca el cursor.

   Se pueden utilizar variables de eventos de flujos de trabajo para generar una expresión. For more on this, refer to the [Customizing activities with events variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) section.

1. Asigne un nombre específico a la regla. El nombre ingresado aparecerá como nombre de regla en el espacio de trabajo del editor de consultas.

Editar una expresión permite personalizar la expresión Audiencias para dirigirse a la población según sea necesario.

**Temas relacionados:**

* [Sintaxis de expresión](../../automating/using/advanced-expression-editing.md#expression-syntax)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Expression Syntax {#expression-syntax}

### Standard syntax {#standard-syntax}

Las expresiones estándar se componen de una o varias condiciones que respetan los siguientes elementos de sintaxis:

* Each condition takes the form of **&lt;value1&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; value 1 &gt;** es un campo o una función. For example **@created** for the date a profile was created or **Year(@created)** for the year a profile was created.
   * **&lt; operador de comparación &gt;** es uno de los operadores enumerados en [la sección Operadores](../../automating/using/advanced-expression-editing.md#comparison-operators) de comparación. This operator defines the comparison method between **&lt;value1&gt;** and **&lt;value2&gt;**.
   * **&lt; value 2 &gt;** es un campo, una función o un valor introducido manualmente.
   >[!NOTE]
   >
   >The **&lt;value1&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;value1&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Si desea utilizar varias condiciones, pueden combinarse con operadores lógicos.

   * **[!UICONTROL AND]**: dos condiciones están intersectadas.
   * **[!UICONTROL OR]**: se combinan dos condiciones.

Por ejemplo:

```
Year(@created) = Year(GetDate()) AND Month(@created) = Month(GetDate())
```

En este ejemplo, los perfiles cuya fecha de creación se encuentra en el mes y año en curso son objetivos.

### JavaScript syntax {#javascript-syntax}

Al definir las condiciones de visibilidad de un bloque de tipo de texto del editor de contenido HTML, se debe utilizar una expresión con sintaxis de tipo JavaScript.

Las expresiones JavaScript se componen de una o varias condiciones y utilizan los siguientes elementos de sintaxis:

* Each condition takes the form of **&lt;context&gt; &lt;comparison operator&gt; &lt;value2&gt;** whereby:

   * **&lt; context &gt;** es un campo o una función que permite especificar el contexto. For example **context.profile.@email** for a profile's email address or **context.profile.firstName.length()** for the number of characters of a profile's first name.
   * **&lt; operador de comparación &gt;** es uno de los operadores enumerados en [la sección Operadores](../../automating/using/advanced-expression-editing.md#comparison-operators) de comparación. This operator defines the comparison method between **&lt;context&gt;** and **&lt;value2&gt;**.
   * **&lt; value 2 &gt;** es un campo, una función o un valor introducido manualmente.
   >[!NOTE]
   The **&lt;context&gt;** and **&lt;value2&gt;** type data must be identical. For example, if **&lt;context&gt;** is a date, then **&lt;value2&gt;** must also be a date.

* Si desea utilizar varias condiciones, pueden combinarse con operadores lógicos.

   * **[!UICONTROL &&]**: dos condiciones están intersectadas.
   * **[!UICONTROL ||]**: se combinan dos condiciones.

Por ejemplo:

```
context.profile.age > 21 && context.profile.firstName.length() > 0
```

In this example, profiles older than 21 years of age and whose first name has been provided (symbolized by the fact that the **firstName** field contains at least one character).

## Comparison operators {#comparison-operators}

Para algunas reglas, el editor de consultas permite elegir un valor para definir su condición.

Las condiciones deben estar vinculadas a los valores mediante uno de los operadores siguientes.

<table> 
 <thead> 
  <tr> 
   <th> Operator<br /> </th> 
   <th> Standard syntax<br /> </th> 
   <th> JavaScript syntax<br /> </th> 
   <th> Description<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <span class="uicontrol">Igual a</span><br /> </td> 
   <td> =<br /> </td> 
   <td> ==<br /> </td> 
   <td> The first value must be completely identical to the second value.<br /> </td> 
   <td> <strong>@ Lastname = Martin</strong> recupera perfiles cuyo apellido es'Martin ', con solo estos caracteres idénticos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mayor que</span><br /> </td> 
   <td> &gt;<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> The first value must categorically be more than the second value.<br /> </td> 
   <td> <strong>@ age &gt; 50</strong> recupera perfiles que tienen más de ' 50 ', por lo tanto ' 51 ',' 52 ', etc.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor que</span><br /> </td> 
   <td> &lt;<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> The first value must categorically be less than the second value.<br /> </td> 
   <td> <strong>@ created &lt; daysago (100)</strong> recupera todos los perfiles creados en la base de datos hace menos de 100 días.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Mayor o igual que</span><br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> &gt;=<br /> </td> 
   <td> The first value must be more than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &gt; = 30</strong> recupera perfiles mayores de 30 años y anteriores.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Menor o igual que</span><br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> &lt;=<br /> </td> 
   <td> The first value must be less than or equal to the second value.<br /> </td> 
   <td> <strong>@ age &lt; = 60</strong> recupera perfiles a partir de 60 o menos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Diferentes </span><br /> </td> 
   <td> !=<br /> </td> 
   <td> !=<br /> </td> 
   <td> The first value must be different from the second value.<br /> </td> 
   <td> <strong>@ language!= English</strong> retrieves profiles that have not been defined as English speaking.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Contiene</span><br /> </td> 
   <td> IN<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must contain the second value.<br /> </td> 
   <td> <strong>@ domain IN mail</strong>. Aquí, todos los nombres de dominio con el valor'correo'se devuelven en el resultado. Consequently, the 'gmail.com' domain name will make up part of the returned results.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Me gusta</span><br /> </td> 
   <td> LIKE<br /> </td> 
   <td> N/A<br /> </td> 
   <td> <span class="uicontrol">" Me gusta "</span> es muy similar al <span class="uicontrol">operador Contiene</span> . It lets you insert a <span class="uicontrol">%</span> wild card character in the value that is being searched.<br /> </td> 
   <td> <strong>@ Lastname LIKE Mart % n</strong>. Here, the substitution character <strong>%</strong> serves as a "joker" to find the name "Martin" in the hypothetical case that the spelling is not correct.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">No como</span><br /> </td> 
   <td> NOT<br /> </td> 
   <td> N/A<br /> </td> 
   <td> Is similar to <span class="uicontrol">Like</span>. Permite no recuperar el valor introducido. Here too, the entered value must contain the <span class="uicontrol">%</span> wild card character.<br /> </td> 
   <td> <strong>@ Lastname NOT Smi % h</strong>. Aquí, los destinatarios corresponden al nombre'Smi % h ' (por lo tanto, Smith, etc.) are not returned as a result.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Está vacío</span><br /> </td> 
   <td> IS NULL<br /> </td> 
   <td> N/A<br /> </td> 
   <td> The first value must correspond to an empty value.<br /> </td> 
   <td> <strong>@ Mobilephone IS NULL</strong> recupera todos los perfiles cuyo número de teléfono móvil no se ha proporcionado.<br /> </td> 
  </tr> 
 </tbody> 
</table>

