---
title: Lista de funciones
seo-title: Lista de funciones
description: Lista de funciones
seo-description: La herramienta de edición de consultas permite utilizar funciones avanzadas para llevar a cabo filtraciones complejas.
page-status-flag: no activado nunca
uuid: fd 50 fc 99-1 e 7 a -479 b-beb 7-1 f 246 b 419 d 46
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: filtrar datos
discoiquuid: 3 cdbe 962-1 c 59-4 cd 8-b 29 e -36 aa 2562 fac 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 83be3f22f3508248f2a4666080a7207998093dc3

---


# Lista de funciones{#list-of-functions}

## Acerca de las funciones {#about-functions}

La herramienta de edición de consultas permite utilizar funciones avanzadas para llevar a cabo filtraciones complejas. Para ello, la paleta de herramientas contiene el **[!UICONTROL Expression]** elemento que puede utilizar en el espacio de trabajo. Encontrará más información sobre este elemento en una [sección específica](../../automating/using/advanced-expression-editing.md).

Este elemento permite introducir las condiciones manualmente. Aquí puede utilizar las funciones definidas en las secciones siguientes.

Hay disponibles varios tipos de funciones, según los resultados deseados y los tipos de datos manipulados:

* Fechas
* Geomarketing
* Valores numéricos
* Otras funciones
* Agrega
* Manipulación de cadenas
* Ordenar

## Fechas {#dates}

Las funciones de fecha se utilizan para manipular los valores de fecha o hora.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Adddays</strong><br /> </td> 
   <td> Agrega un número de días a una fecha<br /> </td> 
   <td> Adddays (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addhours</strong><br /> </td> 
   <td> Agrega un número de horas a una fecha<br /> </td> 
   <td> Addhours (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addminutes</strong><br /> </td> 
   <td> Agrega un número de minutos a una fecha<br /> </td> 
   <td> Addminutes (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addmonths</strong><br /> </td> 
   <td> Agrega un número de meses a una fecha<br /> </td> 
   <td> Addmonths (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addseconds</strong><br /> </td> 
   <td> Agrega un número de segundos a una fecha<br /> </td> 
   <td> Addseconds (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addyears</strong><br /> </td> 
   <td> Agrega un número de años a una fecha<br /> </td> 
   <td> Addyears (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dateonly</strong><br /> </td> 
   <td> Devuelve sólo la fecha (con el tiempo a las 00:00)<br /> </td> 
   <td> Dateonly (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Día</strong><br /> </td> 
   <td> Devuelve el número que representa el día de la fecha<br /> </td> 
   <td> Día (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dayofyear</strong><br /> </td> 
   <td> Devuelve un número que representa el día del año de la fecha.<br /> </td> 
   <td> Dayofyear (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> Devuelve la fecha actual menos n días<br /> </td> 
   <td> Daysago (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysagoint</strong><br /> </td> 
   <td> Devuelve la fecha actual menos n días (como entero aaaammdd)<br /> </td> 
   <td> Daysagoint (&lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysdiff</strong><br /> </td> 
   <td> Cantidad de días entre dos fechas<br /> </td> 
   <td> Daysdiff (&lt; fecha de finalización &gt;, &lt; fecha de inicio &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysell</strong><br /> </td> 
   <td> Devuelve la edad en días de una fecha<br /> </td> 
   <td> Daysell (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getdate</strong><br /> </td> 
   <td> Devuelve la fecha del sistema actual del servidor<br /> </td> 
   <td> Getdate ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hora</strong><br /> </td> 
   <td> Devuelve la hora de la fecha<br /> </td> 
   <td> Hora (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hoursdiff</strong><br /> </td> 
   <td> Devuelve el número de horas entre dos fechas<br /> </td> 
   <td> Hoursdiff (&lt; fecha de finalización &gt;, &lt; fecha de inicio &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Localtoutc</strong><br /> </td> 
   <td> Convierte una fecha y hora locales a UTC<br /> </td> 
   <td> Localtoutc (&lt; date &gt;, &lt; Huso horario &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuto</strong><br /> </td> 
   <td> Devuelve los minutos de la fecha<br /> </td> 
   <td> Minuto (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minutesdiff</strong><br /> </td> 
   <td> Devuelve el número de minutos entre dos fechas<br /> </td> 
   <td> Minutesdiff (&lt; end date &gt;, &lt; date date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mes</strong><br /> </td> 
   <td> Devuelve el número que representa el mes de la fecha<br /> </td> 
   <td> Mes (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> Devuelve la fecha correspondiente a la fecha actual menos n meses<br /> </td> 
   <td> Monthsago (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsdiff</strong><br /> </td> 
   <td> Devuelve el número de meses entre dos fechas<br /> </td> 
   <td> Monthsdiff (&lt; fecha de finalización &gt;, &lt; fecha de inicio &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthvendido</strong><br /> </td> 
   <td> Devuelve la edad en meses de una fecha<br /> </td> 
   <td> Monthsell (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Segundo</strong><br /> </td> 
   <td> Devuelve los segundos de la fecha<br /> </td> 
   <td> Segundo (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Más antiguos</strong><br /> </td> 
   <td> Devuelve la fecha más antigua </td> 
   <td> Más antiguas (&lt; Fecha &gt;, &lt; Fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondsdiff</strong><br /> </td> 
   <td> Devuelve el número de segundos entre dos fechas<br /> </td> 
   <td> Secondsdiff (&lt; fecha de finalización &gt;, &lt; fecha de inicio &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subdays</strong><br /> </td> 
   <td> Resta un número de días desde una fecha<br /> </td> 
   <td> Subdays (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subhoras</strong><br /> </td> 
   <td> Resta un número de horas desde una fecha<br /> </td> 
   <td> Subhours (&lt; fecha &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subminutes</strong><br /> </td> 
   <td> Resta un número de minutos desde una fecha<br /> </td> 
   <td> Subminutes (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Submeses</strong><br /> </td> 
   <td> Resta un número de meses desde una fecha<br /> </td> 
   <td> Submonths (&lt; fecha &gt;, &lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subseconds</strong><br /> </td> 
   <td> Resta un número de segundos desde una fecha<br /> </td> 
   <td> Subseconds (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subyears</strong><br /> </td> 
   <td> Resta un número de años desde una fecha<br /> </td> 
   <td> Subyears (&lt; date &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todate</strong><br /> </td> 
   <td> Convierte una fecha + hora como fecha<br /> </td> 
   <td> Todate (&lt; fecha + hora &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetime</strong><br /> </td> 
   <td> Convierte una cadena en una fecha + hora<br /> </td> 
   <td> Todatetime (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetimewithtimezone</strong><br /> </td> 
   <td> Convierte una cadena en una fecha + huso horario.<br /> Ejemplo: Todatetimewithtimezone ("2019-02-19 08:09:00", "Asia/Teherán")<br /> </td> 
   <td> Todatetimewithtimezone (&lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdate</strong><br /> </td> 
   <td> Redondea una fecha + hora al segundo más cercano<br /> </td> 
   <td> Truncdate (@ lastmodified, &lt; número de segundos &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdatetz</strong><br /> </td> 
   <td> Redondea una fecha + hora a una precisión determinada expresada en segundos<br /> </td> 
   <td> Truncdatetz (&lt; date &gt;, &lt; número de segundos &gt;, &lt; huso horario &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncquarter</strong><br /> </td> 
   <td> Redondea una fecha al trimestre.<br /> </td> 
   <td> Truncquarter (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunctime</strong><br /> </td> 
   <td> Redondea la parte del tiempo hasta el segundo más cercano<br /> </td> 
   <td> Trunctime (&lt; date &gt;, &lt; número de segundos &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncweek</strong><br /> </td> 
   <td> Redondea una fecha a la semana<br /> </td> 
   <td> Truncweek (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncyear</strong><br /> </td> 
   <td> Redondea una fecha + hora hasta el 1 de enero del año<br /> </td> 
   <td> Truncyear (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Día de la semana</strong><br /> </td> 
   <td> Devuelve el número que representa el día de la semana de la fecha.<br /> </td> 
   <td> Día laborable (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Año</strong><br /> </td> 
   <td> Devuelve el número que representa el año de la fecha<br /> </td> 
   <td> Año (&lt; fecha &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearand Month</strong><br /> </td> 
   <td> Devuelve el número que representa el año y el mes de la fecha<br /> </td> 
   <td> Yearandmonth (&lt; date &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsdiff</strong><br /> </td> 
   <td> Devuelve el número de años entre las dos fechas<br /> </td> 
   <td> Yearsdiff (&lt; fecha de finalización &gt;, &lt; fecha de inicio &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsell</strong><br /> </td> 
   <td> Devuelve la edad en años de una fecha<br /> </td> 
   <td> Yearsell (&lt; fecha &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

Las funciones geomarketing se utilizan para manipular los valores geográficos.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distancia</strong><br /> </td> 
   <td> Devuelve la distancia en kilómetros entre dos puntos definidos por su longitud y latitud (expresados en grados).<br /> </td> 
   <td> Distancia (&lt; Longitude A &gt;, &lt; Latitud A &gt;, &lt; Longitude B &gt;, &lt; Latitud B &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numérico {#numerical}

Las funciones numéricas de valor se utilizan para convertir texto a números.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Abs</strong><br /> </td> 
   <td> Devuelve el valor absoluto de un número<br /> </td> 
   <td> Abs (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Devuelve el número entero más bajo mayor o igual que un número<br /> </td> 
   <td> Ceil (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Devuelve el mayor entero mayor que o igual a un número<br /> </td> 
   <td> Floor (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mayor</strong><br /> </td> 
   <td> Devuelve el mayor de dos números<br /> </td> 
   <td> Major (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Devuelve el menor de dos números<br /> </td> 
   <td> Least (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Devuelve el resto de la división integer desde n 1 por n 2<br /> </td> 
   <td> Mod (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Porcentaje</strong><br /> </td> 
   <td> Devuelve la proporción entre dos números expresados como porcentaje<br /> </td> 
   <td> Porcentaje (&lt; número 1 &gt;, &lt; número 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aleatorio</strong><br /> </td> 
   <td> Devuelve el valor aleatorio<br /> </td> 
   <td> Aleatorio ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Redondea un número a n decimales<br /> </td> 
   <td> Round (&lt; número &gt;, &lt; número de decimales &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Devuelve el signo del número<br /> </td> 
   <td> Sign (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todouble</strong><br /> </td> 
   <td> Convierte un entero en flotante<br /> </td> 
   <td> Todouble (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Convierte un flotante a un entero de 64 bits<br /> </td> 
   <td> Toint 64 (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointeger</strong><br /> </td> 
   <td> Convierte un flotante a un entero<br /> </td> 
   <td> Tointeger (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Trunca n 1 a n 2 decimales<br /> </td> 
   <td> Trunc (&lt; n 1 &gt;, &lt; n 2 &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Otras {#others}

Esta tabla contiene las funciones restantes que son predecibles.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Caso</strong><br /> </td> 
   <td> Devuelve el valor 1 si se ha verificado la condición. De lo contrario, devuelve valor 2<br /> </td> 
   <td> Case (When (&lt; condition &gt;, &lt; value 1 &gt;), Else (&lt; value 2 &gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> Elimina el indicador del valor<br /> </td> 
   <td> Clearbit (&lt; identificador &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Devuelve valor 2 si el valor 1 es cero o nulo, devuelve el valor 1<br /> </td> 
   <td> Coalesce (&lt; value 1 &gt;, &lt; value 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Devuelve value 3 es value 1 = value 2, de lo contrario devuelve 4<br /> </td> 
   <td> Decode (&lt; value 1 &gt;, &lt; value 2 &gt;, &lt; value 3 &gt;, &lt; value 4 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Devuelve valor 1 (sólo puede utilizarse como parámetro de la función case)<br /> </td> 
   <td> Else (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getemaildomain</strong><br /> </td> 
   <td> Extrae el dominio de una dirección de correo electrónico<br /> </td> 
   <td> Getemaildomain (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getmirrorurl</strong><br /> </td> 
   <td> Recupera la URL del servidor de páginas espejo<br /> </td> 
   <td> Getmirrorurl (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Devuelve el valor 1 si la expresión es verdadera, devuelve valor 2<br /> </td> 
   <td> Iif (&lt; condición &gt;, &lt; valor 1 &gt;, &lt; valor 2 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isbitset</strong><br /> </td> 
   <td> Indica si el indicador está en el valor<br /> </td> 
   <td> Isbitset (&lt; identificador &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isemptystring</strong><br /> </td> 
   <td> Devuelve valor 2 si la cadena está vacía, devuelve valor 3<br /> </td> 
   <td> Isemptystring (&lt; string &gt;, &lt; value 2 &gt;, &lt; value 3 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> Devuelve la cadena vacía si el argumento es NULO<br /> </td> 
   <td> Nonull (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rowid</strong><br /> </td> 
   <td> Devuelve el número de línea<br /> </td> 
   <td> Rowid<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Setbit</strong><br /> </td> 
   <td> Fuerza el indicador en el valor<br /> </td> 
   <td> Setbit (&lt; identificador &gt;, &lt; flag &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> Convierte un número en un booleano<br /> </td> 
   <td> Toboolean (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Cuando</strong><br /> </td> 
   <td> Devuelve el valor 1 si la expresión se ha verificado. De lo contrario, devuelve valor 2 (sólo se puede utilizar como parámetro de la función case)<br /> </td> 
   <td> When (&lt; condition &gt;, &lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Newuuid</strong><br /> </td> 
   <td> Devuelve un nuevo UUID.<br /> </td> 
   <td> Newuuid<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Cadena {#string}

Las funciones de cadena se utilizan para manipular un conjunto de cadenas.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull2</strong><br /> </td> 
   <td> Indica si todos los parámetros no son nulos y no están vacíos<br /> </td> 
   <td> Allnonnull 2 (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica si todos los parámetros no son nulos y no están vacíos<br /> </td> 
   <td> Allnonnull 3 (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Devuelve el valor ASCII del primer carácter de la cadena<br /> </td> 
   <td> Ascii (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Devuelve el carácter correspondiente al código ASCII'n '<br /> </td> 
   <td> Char (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Devuelve la posición de la cadena 2 en la cadena 1<br /> </td> 
   <td> Charindex (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Datalength</strong><br /> </td> 
   <td> Devuelve el número de caracteres de una cadena<br /> </td> 
   <td> Datalength (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getline</strong><br /> </td> 
   <td> Devuelve la línea nth (del 1 al n) de la cadena<br /> </td> 
   <td> Getline (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> Devuelve el tercer parámetro si los dos primeros parámetros son iguales, devuelve el último parámetro<br /> </td> 
   <td> Ifequals (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ismemonull</strong><br /> </td> 
   <td> Indica si el memorando enviado como parámetro es nulo<br /> </td> 
   <td> Ismemonull (&lt; Memo &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Juxtwords</strong><br /> </td> 
   <td> Concatena las dos cadenas pasadas como parámetros. Se agrega un espacio entre cada cadena del valor devuelto.<br /> </td> 
   <td> Juxtwords (&lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concatena las tres cadenas pasadas como parámetros. Se agrega un espacio entre cada cadena del valor devuelto.<br /> </td> 
   <td> Juxtwords 3 (&lt; string &gt;, &lt; string &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lpad</strong><br /> </td> 
   <td> Devuelve la cadena completada a la izquierda<br /> </td> 
   <td> Lpad (&lt; cadena &gt;, &lt; número &gt;, &lt; caractère &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Izquierda</strong><br /> </td> 
   <td> Devuelve los primeros n caracteres de la cadena<br /> </td> 
   <td> Left (&lt; string &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Longitud</strong><br /> </td> 
   <td> Devuelve la longitud de cadena<br /> </td> 
   <td> Length (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Devuelve la cadena en minúsculas<br /> </td> 
   <td> Lower (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Quita los espacios a la izquierda de la cadena<br /> </td> 
   <td> Ltrim (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Devuelve una representación hexadecimal de la clave MD 5 de una cadena<br /> </td> 
   <td> Md 5 Digest (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Memocontiene</strong><br /> </td> 
   <td> Especifica si el memorando contiene la cadena pasada como parámetro<br /> </td> 
   <td> Memocontains (&lt; memo &gt;, &lt; string &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rpad</strong><br /> </td> 
   <td> Devuelve la cadena completada a la derecha<br /> </td> 
   <td> Rpad (&lt; string &gt;, &lt; number &gt;, &lt; carácter &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Reemplazar</strong><br /> </td> 
   <td> Reemplaza todas las incidencias de una cadena especificada (segundo parámetro) por otro valor de cadena (tercer parámetro) en una cadena (primer parámetro).<br /> </td> 
   <td> Replace (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Derecha</strong><br /> </td> 
   <td> Devuelve los últimos n caracteres de la cadena<br /> </td> 
   <td> Right (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Quita los espacios a la derecha de la cadena<br /> </td> 
   <td> Rtrim (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA 256</strong> estándar para una cadena UTF 8 determinada.<br /> </td> 
   <td> Sha 256 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA 384</strong> estándar para una cadena UTF 8 determinada.<br /> </td> 
   <td> Sha 384 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA 512</strong> estándar para una cadena UTF 8 determinada.<br /> </td> 
   <td> Sha 512 Digest (&lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Inteligente</strong><br /> </td> 
   <td> Devuelve la cadena con la primera letra de cada palabra en mayúsculas<br /> </td> 
   <td> Inteligente (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subcadena</strong><br /> </td> 
   <td> Extrae la subcadena comenzando por el carácter n 1 de la cadena y con una longitud n 2<br /> </td> 
   <td> Subcadena (&lt; cadena &gt;, &lt; desplazamiento &gt;, &lt; longitud &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointlstring</strong><br /> </td> 
   <td> Convierte el número en una cadena<br /> </td> 
   <td> Tointlstring (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tostring</strong><br /> </td> 
   <td> Convierte el número en una cadena<br /> </td> 
   <td> Tostring (&lt; número &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Superior</strong><br /> </td> 
   <td> Devuelve la cadena en mayúsculas<br /> </td> 
   <td> Upper (&lt; cadena &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallink</strong><br /> </td> 
   <td> Devuelve la clave externa de un vínculo pasado como parámetro si los otros dos parámetros son iguales<br /> </td> 
   <td> Virtuallink (&lt; number &gt;, &lt; number &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallinkstr</strong><br /> </td> 
   <td> Devuelve la clave foreign (text) de un vínculo pasado como parámetro si los otros dos parámetros son iguales<br /> </td> 
   <td> Virtuallinkstr (&lt; string &gt;, &lt; number &gt;, &lt; number &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcdecrypt</strong><br /> </td> 
   <td> Descifra un valor cifrado en formato HEX con prefijo "<strong>x</strong>" (primer parámetro) con una clave en formato HEX (segundo parámetro) y un vector de inicialización en formato HEX (tercer parámetro)<br /> </td> 
   <td> encryption_ aescbcdecrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcencrypt</strong><br /> </td> 
   <td> Codifica el uso de algoritmo AES (modo bloque CBC) una cadena de caracteres (primer parámetro) con una clave (2. º parámetro) y un vector de inicialización (tercer parámetro). La clave y el vector de inicialización deben proporcionarse en una representación hexadecimal (partiendo de <strong>\ x</strong>). El resultado será hexadecimal sin la <strong>\ x</strong>.<br /> Tenga en cuenta que el tamaño de la clave puede ser de 128 bits, 192 bits, 256 bits (16, 24, 32 caracteres hexadecimales) pero le recomendamos que utilice 256 bits y un IV aleatorizado de la misma longitud que la clave.<br /> </td> 
   <td> encryption_ aescbcencrypt (&lt; String &gt;, &lt; String &gt;, &lt; String &gt;)<br /> Por ejemplo: encryption_ aescbcencrypt (johndoe@example.com, "<strong>\ x 0123456789 ABCDEF 0123456789 ABCDEF</strong>", "<strong>\ x 0123456789 ABCDEFFEDCBA 9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Agrega {#aggregates}

Las funciones de agregación solo están disponibles al [agregar datos adicionales](../../automating/using/query.md#enriching-data) a partir **[!UICONTROL Query]** de una actividad del flujo de trabajo.

Las funciones agregadas se utilizan para realizar cálculos en un conjunto de valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Promedio</strong>, promedio<br /> </td> 
   <td> Devuelve el promedio en una columna numérica.<br /> </td> 
   <td> Avg (&lt; valor &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Recuento</strong>, Recuento (excepto NULL)<br /> </td> 
   <td> Cuenta los valores no nulos de una columna.<br /> </td> 
   <td> Count (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countall</strong>, Count all<br /> </td> 
   <td> Cuenta todos los valores (incluidos los valores nulos y los duplicados).<br /> </td> 
   <td> Countall ()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Recuento distinto y</strong>diferenciado<br /> </td> 
   <td> Cuenta los valores no nulos y distintos de una columna.<br /> </td> 
   <td> Countdistinct (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Máx</strong>., Máx.<br /> </td> 
   <td> Devuelve el valor máximo de una columna numérica, de cadena o numérica.<br /> </td> 
   <td> Max (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Devuelve el valor mínimo en una columna numérica, de cadena o numérica.<br /> </td> 
   <td> Min (&lt; value &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Suma</strong>, suma<br /> </td> 
   <td> Devuelve la suma de los valores en una columna numérica.<br /> </td> 
   <td> Sum (&lt; value &gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representación {#representation}

Las funciones de representación se utilizan para ordenar valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Desc</strong><br /> </td> 
   <td> Aplica un orden descendente<br /> </td> 
   <td> Desc (&lt; valor 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Orderby</strong><br /> </td> 
   <td> Ordena el resultado dentro de la partición<br /> </td> 
   <td> Orderby (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Partitionby</strong><br /> </td> 
   <td> Particiones el resultado de una consulta en una tabla<br /> </td> 
   <td> Partitionby (&lt; value 1 &gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rownum</strong><br /> </td> 
   <td> Genera un número de línea basado en la partición de tabla y en una secuencia de orden. Esta función no es compatible con MySQL<br /> </td> 
   <td> Rownum (partitionby (&lt; value 1 &gt;), orderby (&lt; value 1 &gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

