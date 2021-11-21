---
title: Lista de funciones
description: La herramienta de edición de consultas le permite utilizar funciones avanzadas para realizar filtrados complejos.
audience: automating
content-type: reference
topic-tags: filtering-data
feature: Workflows
role: Data Architect
level: Experienced
exl-id: d1575626-55bb-4303-a796-ad323a399330
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '1970'
ht-degree: 95%

---

# Lista de funciones{#list-of-functions}

## Acerca de las funciones {#about-functions}

La herramienta de edición de consultas le permite utilizar funciones avanzadas para realizar filtrados complejos. Para ello, la paleta herramientas contiene el elemento **[!UICONTROL Expression]** que puede utilizar en el espacio de trabajo. Encontrará más información sobre este elemento en una [sección específica](../../automating/using/advanced-expression-editing.md).

Este elemento le permite introducir las condiciones manualmente. Aquí puede utilizar las funciones definidas en las siguientes secciones.

Existen varios tipos de funciones disponibles, según los resultados deseados y los tipos de datos manipulados:

* Fechas
* Geomarketing
* Valores numéricos
* Otras funciones
* Agregados
* Manipulación de cadenas
* Ordenar

>[!NOTE]
>
>Hay funciones adicionales disponibles en todas las actividades que permiten utilizar variables de eventos después de llamar a un flujo de trabajo con parámetros externos. Se detallan en [esta sección](../../automating/using/customizing-workflow-external-parameters.md).

## Fechas {#dates}

Las funciones de fecha se utilizan para manipular los valores de fecha y hora.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Syntax</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddDays</strong><br /> </td> 
   <td> Agrega un número de días a una fecha<br /> </td> 
   <td> AddDays(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddHours</strong><br /> </td> 
   <td> Agrega un número de horas a una fecha<br /> </td> 
   <td> AddHours(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMinutes</strong><br /> </td> 
   <td> Añade un número de minutos a una fecha<br /> </td> 
   <td> AddMinutes(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddMonths</strong><br /> </td> 
   <td> Añade un número de meses a una fecha<br /> </td> 
   <td> AddMonths(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddSeconds</strong><br /> </td> 
   <td> Añade un número de segundos a una fecha<br /> </td> 
   <td> AddSeconds(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AddYears</strong><br /> </td> 
   <td> Agrega un número de años a una fecha<br /> </td> 
   <td> AddYears(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DateOnly</strong><br /> </td> 
   <td> Devuelve solo la fecha (con hora 00:00)<br /> </td> 
   <td> DateOnly(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Day</strong><br /> </td> 
   <td> Devuelve el número que representa el día de la fecha.<br /> </td> 
   <td> Day(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DayOfYear</strong><br /> </td> 
   <td> Devuelve un número que representa el día del año de la fecha<br /> </td> 
   <td> DayOfYear(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgo</strong><br /> </td> 
   <td> Devuelve la fecha actual menos N días<br /> </td> 
   <td> DaysAgo(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysAgoInt</strong><br /> </td> 
   <td> Devuelve la fecha actual menos N días (como un entero aaaammdd)<br /> </td> 
   <td> DaysAgoInt(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysDiff</strong><br /> </td> 
   <td> Número de días entre dos fechas<br /> </td> 
   <td> DaysDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DaysOld</strong><br /> </td> 
   <td> Devuelve la edad en días de una fecha<br /> </td> 
   <td> DaysOld(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetDate</strong><br /> </td> 
   <td> Devuelve la fecha del sistema actual del servidor<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hour</strong><br /> </td> 
   <td> Devuelve la hora de la fecha<br /> </td> 
   <td> Hour(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HoursDiff</strong><br /> </td> 
   <td> Devuelve el número de horas entre dos fechas<br /> </td> 
   <td> HoursDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LocalToUTC</strong><br /> </td> 
   <td> Convierte una fecha y hora locales a UTC<br /> </td> 
   <td> LocalToUTC(&lt;fecha&gt;, &lt;zona horaria&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minute</strong><br /> </td> 
   <td> Devuelve los minutos de la fecha<br /> </td> 
   <td> Minute(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MinutesDiff</strong><br /> </td> 
   <td> Devuelve el número de minutos entre dos fechas<br /> </td> 
   <td> MinutesDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Month</strong><br /> </td> 
   <td> Devuelve el número que representa el mes de la fecha<br /> </td> 
   <td> Month(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsAgo</strong><br /> </td> 
   <td> Devuelve la fecha correspondiente a la fecha actual menos n meses<br /> </td> 
   <td> MonthsAgo(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsDiff</strong><br /> </td> 
   <td> Devuelve el número de meses entre dos fechas<br /> </td> 
   <td> MonthsDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MonthsOld</strong><br /> </td> 
   <td> Devuelve la edad en meses de una fecha<br /> </td> 
   <td> MonthsOld(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Second</strong><br /> </td> 
   <td> Devuelve los segundos de la fecha<br /> </td> 
   <td> Second(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Oldest</strong><br /> </td> 
   <td> Devuelve la fecha más antigua </td> 
   <td> Oldest(&lt;Fecha&gt;, &lt;Fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SecondsDiff</strong><br /> </td> 
   <td> Devuelve el número de segundos entre dos fechas<br /> </td> 
   <td> SecondsDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubDays</strong><br /> </td> 
   <td> Resta un número de días a partir de una fecha<br /> </td> 
   <td> SubDays(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubHours</strong><br /> </td> 
   <td> Resta un número de horas a partir de una fecha<br /> </td> 
   <td> SubHours(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMinutes</strong><br /> </td> 
   <td> Resta un número de minutos desde una fecha<br /> </td> 
   <td> SubMinutes(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubMonths</strong><br /> </td> 
   <td> Resta un número de meses desde una fecha<br /> </td> 
   <td> SubMonths(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubSeconds</strong><br /> </td> 
   <td> Resta un número de segundos desde una fecha<br /> </td> 
   <td> SubSeconds(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SubYears</strong><br /> </td> 
   <td> Resta un número de años a partir de una fecha<br /> </td> 
   <td> SubYears(&lt;fecha&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDate</strong><br /> </td> 
   <td> Convierte una fecha y hora como fecha<br /> </td> 
   <td> ToDate(&lt;fecha + hora&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTime</strong><br /> </td> 
   <td> Convierte una cadena en una fecha + hora.<br /> </td> 
   <td> ToDateTime(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDateTimeWithTimezone</strong><br /> </td> 
   <td> Convierte una cadena en una fecha + huso horario.<br /> Ejemplo: ToDateTimeWithTimezone ("2019-02-19 08:09:00", "Asia/Teherán")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDate</strong><br /> </td> 
   <td> Redondea una fecha y hora hacia el segundo más cercano<br /> </td> 
   <td> TruncDate(@lastModified, &lt;número de segundos&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncDateTZ</strong><br /> </td> 
   <td> Redondea una fecha y hora con una precisión determinada expresada en segundos<br /> </td> 
   <td> TruncDateTZ(&lt;fecha&gt;, &lt;número de segundos&gt;, &lt;zona horaria&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncQuarter</strong><br /> </td> 
   <td> Redondea una fecha al trimestre<br /> </td> 
   <td> TruncQuarter(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncTime</strong><br /> </td> 
   <td> Redondea la parte de tiempo hasta el segundo más cercano<br /> </td> 
   <td> TruncTime(&lt;fecha&gt;, &lt;número de segundos&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncWeek</strong><br /> </td> 
   <td> Redondea una fecha a la semana<br /> </td> 
   <td> TruncWeek(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>TruncYear</strong><br /> </td> 
   <td> Redondea una fecha y hora al 1 de enero del año<br /> </td> 
   <td> TruncYear(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>WeekDay</strong><br /> </td> 
   <td> Devuelve el número que representa el día de la semana de la fecha<br /> </td> 
   <td> WeekDay(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Year</strong><br /> </td> 
   <td> Devuelve el número que representa el año de la fecha<br /> </td> 
   <td> Year(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearAndMonth</strong><br /> </td> 
   <td> Devuelve el número que representa el año y el mes de la fecha<br /> </td> 
   <td> YearAndMonth(&lt;fecha&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsDiff</strong><br /> </td> 
   <td> Devuelve el número de años entre las dos fechas<br /> </td> 
   <td> YearsDiff(&lt;fecha de finalización&gt;, &lt;fecha de inicio&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>YearsOld</strong><br /> </td> 
   <td> Devuelve la edad en años de una fecha<br /> </td> 
   <td> YearsOld(&lt;fecha&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Geomarketing {#geomarketing}

Las funciones de geomarketing se utilizan para manipular los valores geográficos.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Distance</strong><br /> </td> 
   <td> Devuelve la distancia en kilómetros entre dos puntos definidos por su longitud y latitud (expresada en grados)<br /> </td> 
   <td> Distance(&lt;Longitud A&gt;, &lt;Latitud A&gt;, &lt;Longitud B&gt;, &lt;Latitud B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numérico {#numerical}

Las funciones de valores numéricos se utilizan para convertir texto en números.

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
   <td> Abs(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Devuelve el menor entero que sea mayor o igual que un número<br /> </td> 
   <td> Ceil(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Devuelve el mayor entero que sea menor o igual que un número<br /> </td> 
   <td> Floor(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Greatest</strong><br /> </td> 
   <td> Devuelve el número mayor de dos números<br /> </td> 
   <td> Greatest(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Devuelve el número menor de dos números<br /> </td> 
   <td> Least(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Devuelve el resto de la división del entero de n1 entre n2<br /> </td> 
   <td> Mod(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Percent</strong><br /> </td> 
   <td> Devuelve la proporción de dos números expresado como un porcentaje<br /> </td> 
   <td> Percent(&lt;número 1&gt;, &lt;número 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aleatorio</strong><br /> </td> 
   <td> Devuelve un valor aleatorio<br /> </td> 
   <td> Aleatorio()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Redondea un número a “n” decimales<br /> </td> 
   <td> Redondeo(&lt;número&gt;, &lt;número de decimales&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Devuelve el signo del número<br /> </td> 
   <td> Sign(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToDouble</strong><br /> </td> 
   <td> Convierte un entero en flotante<br /> </td> 
   <td> ToDouble(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Convierte un flotante en un entero de 64 bits<br /> </td> 
   <td> ToInt64(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInteger</strong><br /> </td> 
   <td> Convierte un flotante en un entero<br /> </td> 
   <td> ToInteger(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Trunca decimales de “n1” a “n2”<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Otros {#others}

Esta tabla contiene las funciones restantes disponibles.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Case</strong><br /> </td> 
   <td> Devuelve el valor 1 si la condición está verificada. De lo contrario, devuelve el valor 2<br /> </td> 
   <td> Case(When(&lt;condición&gt;, &lt;valor 1&gt;), Else(&lt;valor 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ClearBit</strong><br /> </td> 
   <td> Elimina el indicador del valor<br /> </td> 
   <td> ClearBit(&lt;identificador&gt;, &lt;indicador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Devuelve el valor 2 si el valor 1 es cero o nulo, de lo contrario devuelve el valor 1<br /> </td> 
   <td> Coalesce(&lt;valor 1&gt;, &lt;valor 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Devuelve el valor 3 si el valor 1 = valor 2; en caso contrario, devuelve el valor 4<br /> </td> 
   <td> Decode(&lt;valor 1&gt;, &lt;valor 2&gt;, &lt;valor 3&gt;, &lt;valor 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Devuelve el valor 1 (solo puede utilizarse como parámetro de la función case)<br /> </td> 
   <td> Else(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetEmailDomain</strong><br /> </td> 
   <td> Extrae el dominio de una dirección de correo electrónico<br /> </td> 
   <td> GetEmailDomain(&lt;valor&gt;)<br /> </td> 
  </tr>
  <tr> 
   <td> <strong>GetMirrorURL</strong><br /> </td> 
   <td> Recupera la URL del servidor de la página espejo<br /> </td> 
   <td> GetMirrorURL(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Devuelve el valor 1 si la expresión es verdadera; en caso contrario, devuelve el valor 2<br /> </td> 
   <td> Iif(&lt;condición&gt;, &lt;valor 1&gt;, &lt;valor 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsBitSet</strong><br /> </td> 
   <td> Indica si el indicador se encuentra en el valor<br /> </td> 
   <td> IsBitSet(&lt;identificador&gt;, &lt;indicador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsEmptyString</strong><br /> </td> 
   <td> Devuelve el valor 2 si la cadena está vacía; en caso contrario, devuelve el valor 3<br /> </td> 
   <td> IsEmptyString(&lt;cadena&gt;, &lt;valor 2&gt;, &lt;valor 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>NoNull</strong><br /> </td> 
   <td> Devuelve la cadena vacía si el argumento es NULL<br /> </td> 
   <td> NoNull(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowId</strong><br /> </td> 
   <td> Devuelve el número de línea<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>SetBit</strong><br /> </td> 
   <td> Fuerza la marca en el valor<br /> </td> 
   <td> SetBit(&lt;identificador&gt;, &lt;indicador&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToBoolean</strong><br /> </td> 
   <td> Convierte un número en Boolean<br /> </td> 
   <td> ToBoolean(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>When</strong><br /> </td> 
   <td> Devuelve el valor 1 si la expresión está verificada. De lo contrario, devuelve el valor 2 (solo puede utilizarse como parámetro de la función case)<br /> </td> 
   <td> When(&lt;condición&gt;, &lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>newUUID</strong><br /> </td> 
   <td> Devuelve un UUID nuevo.<br /> </td> 
   <td> newUUID<br /> </td> 
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
   <td> Indica si todos los parámetros no son nulos y no están vacíos.<br /> </td> 
   <td> AllNonNull2(&lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indica si todos los parámetros no son nulos y no están vacíos.<br /> </td> 
   <td> AllNonNull3(&lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Devuelve el valor ASCII del primer carácter de la cadena<br /> </td> 
   <td> Ascii(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Devuelve el carácter correspondiente al código ASCII “n”.<br /> </td> 
   <td> Char(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Devuelve la posición de la cadena 2 en la cadena 1<br /> </td> 
   <td> Charindex(&lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>DataLength</strong><br /> </td> 
   <td> Devuelve el número de caracteres de una cadena<br /> </td> 
   <td> DataLength(&lt;Cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>GetLine</strong><br /> </td> 
   <td> Muestra la línea nth (de 1 a n) de la cadena.<br /> </td> 
   <td> GetLine(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IfEquals</strong><br /> </td> 
   <td> Devuelve el tercer parámetro si los dos primeros parámetros son iguales; de lo contrario, devuelve el último parámetro<br /> </td> 
   <td> IfEquals(&lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>IsMemoNull</strong><br /> </td> 
   <td> Indica si la nota transferida como parámetro es nula<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords</strong><br /> </td> 
   <td> Concatena las dos cadenas pasadas como parámetros. Se agrega un espacio entre cada cadena en el valor devuelto.<br /> </td> 
   <td> JuxtWords(&lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concatena las tres cadenas pasadas como parámetros. Se agrega un espacio entre cada cadena en el valor devuelto.<br /> </td> 
   <td> JuxtWords3(&lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>LPad</strong><br /> </td> 
   <td> Devuelve la cadena completa a la izquierda<br /> </td> 
   <td> LPad(&lt;cadena&gt;, &lt;número&gt;, &lt;carácter&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Left</strong><br /> </td> 
   <td> Devuelve los primeros “n” caracteres de la cadena<br /> </td> 
   <td> Left(&lt;cadena&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Length</strong><br /> </td> 
   <td> Devuelve la longitud de la cadena<br /> </td> 
   <td> Length(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Devuelve la cadena en minúscula<br /> </td> 
   <td> Lower(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Elimina los espacios a la izquierda de la cadena<br /> </td> 
   <td> Ltrim(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Devuelve una representación hexadecimal de la clave MD5 de una cadena<br /> </td> 
   <td> Md5Digest(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>MemoContains</strong><br /> </td> 
   <td> Especifica si la nota contiene la cadena transferida como parámetro<br /> </td> 
   <td> MemoContains(&lt;Memo&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RPad</strong><br /> </td> 
   <td> Devuelve la cadena completa a la derecha<br /> </td> 
   <td> RPad(&lt;cadena&gt;, &lt;número&gt;, &lt;carácter&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Replace</strong><br /> </td> 
   <td> Reemplaza todas las ocurrencias de un valor de cadena especificado (segundo parámetro) con otro valor de cadena (tercer parámetro) en una cadena (primer parámetro)<br /> </td> 
   <td> Replace(&lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Right</strong><br /> </td> 
   <td> Devuelve los últimos “n” caracteres de la cadena<br /> </td> 
   <td> Right(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Elimina los espacios a la derecha de la cadena<br /> </td> 
   <td> Rtrim(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA256</strong> estándar para una cadena UTF8 determinada<br /> </td> 
   <td> Sha256Digest(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA384</strong> estándar para una cadena UTF8 determinada<br /> </td> 
   <td> Sha384Digest(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calcula el hash <strong>SHA512</strong> estándar para una cadena UTF8 determinada<br /> </td> 
   <td> Sha512Digest(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Smart</strong><br /> </td> 
   <td> Devuelve la cadena con la primera letra de cada palabra en mayúscula<br /> </td> 
   <td> Smart(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Substring</strong><br /> </td> 
   <td> Extrae la subcadena que comienza en el carácter n1 de la cadena con una longitud de n2<br /> </td> 
   <td> Substring(&lt;cadena&gt;, &lt;desajuste&gt;, &lt;longitud&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToIntlString</strong><br /> </td> 
   <td> Convierte el número en una cadena<br /> </td> 
   <td> ToIntlString(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToString</strong><br /> </td> 
   <td> Convierte el número en una cadena<br /> </td> 
   <td> ToString(&lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Upper</strong><br /> </td> 
   <td> Devuelve la cadena en mayúsculas<br /> </td> 
   <td> Upper(&lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLink</strong><br /> </td> 
   <td> Devuelve la clave externa de un vínculo transferido como parámetro si los otros dos parámetros son iguales<br /> </td> 
   <td> VirtualLink(&lt;número&gt;, &lt;número&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>VirtualLinkStr</strong><br /> </td> 
   <td> Devuelve la clave externa (texto) de un enlace transferido como parámetro si los otros dos parámetros son iguales<br /> </td> 
   <td> VirtualLinkStr(&lt;cadena&gt;, &lt;número&gt;, &lt;número&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcDecrypt</strong><br /> </td> 
   <td> Descifra un valor cifrado en formato HEX con el prefijo “<strong>x</strong>” (primer parámetro) utilizando una clave en formato HEX (segundo parámetro) y un vector de inicialización en formato HEX (tercer parámetro)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;cadena&gt;, &lt;cadena&gt;, &lt;cadena&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_aescbcEncrypt</strong><br /> </td> 
   <td> Codifica utilizando el algoritmo AES (modo de bloque CBC) una cadena de caracteres (primer parámetro) con una clave (segundo parámetro) y un vector de inicialización (tercer parámetro). La clave y el vector de inicialización deben proporcionarse en una representación hexadecimal (comenzando por <strong>\x</strong>). El resultado será hexadecimal sin <strong>\x</strong>.<br /> Tenga en cuenta que el tamaño de la clave puede ser de 128 bits, 192 bits, 256 bits (16, 24, 32 caracteres hexadecimales), pero le recomendamos que utilice 256 bits y una IV aleatoria de la misma longitud que la clave.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> Por ejemplo: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Agregados {#aggregates}

Las funciones de agregación solo están disponibles cuando se [agregan datos adicionales](../../automating/using/query.md#enriching-data) desde la actividad **[!UICONTROL Query]** de un flujo de trabajo.

Las funciones agregadas se utilizan para realizar cálculos en un conjunto de valores.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Nombre</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
   <td> <strong>Sintaxis</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avg</strong>, Average<br /> </td> 
   <td> Devuelve el promedio en una columna numérica.<br /> </td> 
   <td> Avg(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Count</strong>, Count (except NULL)<br /> </td> 
   <td> Cuenta los valores no nulos en una columna.<br /> </td> 
   <td> Count(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>CountAll</strong>, Count all<br /> </td> 
   <td> Cuenta todos los valores (incluidos los valores nulos y duplicados).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countdistinct</strong>, Distinct count<br /> </td> 
   <td> Cuenta los distintos valores no nulos en una columna.<br /> </td> 
   <td> Countdistinct(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Max</strong>, Max<br /> </td> 
   <td> Devuelve el valor máximo de una columna numérica, de cadena o de fecha.<br /> </td> 
   <td> Max(&lt;valor&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Devuelve el valor mínimo de una columna numérica, de cadena o de fecha.<br /> </td> 
   <td> Min(&lt;valor&gt;)<br /> </td> 
  </tr>
  <tr>
   <td> <strong>StringAgg</strong>, acumulado de cadenas<br /> </td>
   <td> Devuelve la concatenación de los valores de una columna de tipo cadena, separados por el carácter del segundo argumento (el separador predeterminado es una coma).<br /> </td>
   <td> StringAgg(&lt;string values=""&gt;,&lt;separator&gt;)
  </tr>
  <tr> 
   <td> <strong>Sum</strong>, Sum<br /> </td> 
   <td> Devuelve la suma de los valores de una columna numérica.<br /> </td> 
   <td> Sum(&lt;valor&gt;)<br /> </td> 
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
   <td> Desc(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>OrderBy</strong><br /> </td> 
   <td> Ordena el resultado dentro de la partición<br /> </td> 
   <td> OrderBy(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>PartitionBy</strong><br /> </td> 
   <td> Particiona el resultado de una consulta en una tabla<br /> </td> 
   <td> PartitionBy(&lt;valor 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>RowNum</strong><br /> </td> 
   <td> Genera un número de línea basado en la partición de tabla y en una secuencia de ordenación. Esta función no es compatible con MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;valor 1&gt;), OrderBy(&lt;valor 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>
