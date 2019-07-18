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
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# List of functions{#list-of-functions}

## About functions {#about-functions}

La herramienta de edición de consultas permite utilizar funciones avanzadas para llevar a cabo filtraciones complejas. To do this, the tool palette contains the **[!UICONTROL Expression]** element that you can use in the workspace. Further information on this element is detailed in a [specific section](../../automating/using/advanced-expression-editing.md).

Este elemento permite introducir las condiciones manualmente. Aquí puede utilizar las funciones definidas en las secciones siguientes.

Hay disponibles varios tipos de funciones, según los resultados deseados y los tipos de datos manipulados:

* Fechas
* Geomarketing
* Valores numéricos
* Otras funciones
* Agrega
* Manipulación de cadenas
* Ordenar

## Dates {#dates}

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
   <td> Adds a number of days to a date<br /> </td> 
   <td> AddDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addhours</strong><br /> </td> 
   <td> Adds a number of hours to a date<br /> </td> 
   <td> AddHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addminutes</strong><br /> </td> 
   <td> Adds a number of minutes to a date<br /> </td> 
   <td> AddMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addmonths</strong><br /> </td> 
   <td> Adds a number of months to a date<br /> </td> 
   <td> AddMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addseconds</strong><br /> </td> 
   <td> Adds a number of seconds to a date<br /> </td> 
   <td> AddSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Addyears</strong><br /> </td> 
   <td> Adds a number of years to a date<br /> </td> 
   <td> AddYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dateonly</strong><br /> </td> 
   <td> Returns the date only (with time at 00:00)<br /> </td> 
   <td> DateOnly(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Día</strong><br /> </td> 
   <td> Returns the number representing the day of the date<br /> </td> 
   <td> Day(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Dayofyear</strong><br /> </td> 
   <td> Returns a number representing the day in the year of the date<br /> </td> 
   <td> DayOfYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysago</strong><br /> </td> 
   <td> Returns the current date minus n days<br /> </td> 
   <td> DaysAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysagoint</strong><br /> </td> 
   <td> Returns the current date minus n days (as an integer yyyymmdd)<br /> </td> 
   <td> DaysAgoInt(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysdiff</strong><br /> </td> 
   <td> Number of days between two dates<br /> </td> 
   <td> DaysDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Daysell</strong><br /> </td> 
   <td> Returns the age in days of a date<br /> </td> 
   <td> DaysOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getdate</strong><br /> </td> 
   <td> Returns the current system date of the server<br /> </td> 
   <td> GetDate()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hora</strong><br /> </td> 
   <td> Returns the hour of the date<br /> </td> 
   <td> Hour(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Hoursdiff</strong><br /> </td> 
   <td> Returns the number of hours between two dates<br /> </td> 
   <td> HoursDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Localtoutc</strong><br /> </td> 
   <td> Converts a local date and time to UTC<br /> </td> 
   <td> LocalToUTC(&lt;date&gt;, &lt;Time Zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minuto</strong><br /> </td> 
   <td> Returns the minutes of the date<br /> </td> 
   <td> Minute(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Minutesdiff</strong><br /> </td> 
   <td> Returns the number of minutes between two dates<br /> </td> 
   <td> MinutesDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mes</strong><br /> </td> 
   <td> Returns the number representing the month of the date<br /> </td> 
   <td> Month(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsago</strong><br /> </td> 
   <td> Returns the date corresponding to the current date minus n months<br /> </td> 
   <td> MonthsAgo(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthsdiff</strong><br /> </td> 
   <td> Returns the number of months between two dates<br /> </td> 
   <td> MonthsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Monthvendido</strong><br /> </td> 
   <td> Returns the age in months of a date<br /> </td> 
   <td> MonthsOld(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Segundo</strong><br /> </td> 
   <td> Returns the seconds of the date<br /> </td> 
   <td> Second(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Más antiguos</strong><br /> </td> 
   <td> Devuelve la fecha más antigua </td> 
   <td> Oldest(&lt;Date&gt;, &lt;Date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Secondsdiff</strong><br /> </td> 
   <td> Returns the number of seconds between two dates<br /> </td> 
   <td> SecondsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subdays</strong><br /> </td> 
   <td> Subtracts a number of days from a date<br /> </td> 
   <td> SubDays(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subhoras</strong><br /> </td> 
   <td> Subtracts a number of hours from a date<br /> </td> 
   <td> SubHours(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subminutes</strong><br /> </td> 
   <td> Subtracts a number of minutes from a date<br /> </td> 
   <td> SubMinutes(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Submeses</strong><br /> </td> 
   <td> Subtracts a number of months from a date<br /> </td> 
   <td> SubMonths(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subseconds</strong><br /> </td> 
   <td> Subtracts a number of seconds from a date<br /> </td> 
   <td> SubSeconds(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subyears</strong><br /> </td> 
   <td> Subtracts a number of years from a date<br /> </td> 
   <td> SubYears(&lt;date&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todate</strong><br /> </td> 
   <td> Converts a date + time as a date<br /> </td> 
   <td> ToDate(&lt;date + time&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetime</strong><br /> </td> 
   <td> Converts a string to a date + time<br /> </td> 
   <td> ToDateTime(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todatetimewithtimezone</strong><br /> </td> 
   <td> Convierte una cadena en una fecha + huso horario.<br /> Ejemplo: Todatetimewithtimezone ("2019-02-19 08:09:00", "Asia/Teherán")<br /> </td> 
   <td> ToDateTimeWithTimezone(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdate</strong><br /> </td> 
   <td> Rounds a date+time to the nearest second<br /> </td> 
   <td> TruncDate(@lastModified, &lt;number of seconds&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncdatetz</strong><br /> </td> 
   <td> Rounds a date + time to a given precision expressed in seconds<br /> </td> 
   <td> TruncDateTZ(&lt;date&gt;, &lt;number of seconds&gt;, &lt;time zone&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncquarter</strong><br /> </td> 
   <td> Rounds a date off to the quarter<br /> </td> 
   <td> TruncQuarter(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunctime</strong><br /> </td> 
   <td> Rounds the time part up to the nearest second<br /> </td> 
   <td> TruncTime(&lt;date&gt;, &lt;number of seconds&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncweek</strong><br /> </td> 
   <td> Rounds a date off to the week<br /> </td> 
   <td> TruncWeek(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Truncyear</strong><br /> </td> 
   <td> Rounds a date + time to January 1st of the year<br /> </td> 
   <td> TruncYear(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Día de la semana</strong><br /> </td> 
   <td> Returns the number representing the day in the week of the date<br /> </td> 
   <td> WeekDay(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Año</strong><br /> </td> 
   <td> Returns the number representing the year of the date<br /> </td> 
   <td> Year(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearand Month</strong><br /> </td> 
   <td> Returns the number representing the year and month of the date<br /> </td> 
   <td> YearAndMonth(&lt;date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsdiff</strong><br /> </td> 
   <td> Returns the number of years between the two dates<br /> </td> 
   <td> YearsDiff(&lt;end date&gt;, &lt;start date&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Yearsell</strong><br /> </td> 
   <td> Returns the age in years of a date<br /> </td> 
   <td> YearsOld(&lt;date&gt;)<br /> </td> 
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
   <td> Returns the distance in kilometers between two points defined by their longitude and latitude (expressed in degrees)<br /> </td> 
   <td> Distance(&lt;Longitude A&gt;, &lt;Latitude A&gt;, &lt;Longitude B&gt;, &lt;Latitude B&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Numerical {#numerical}

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
   <td> Returns the absolute value of a number<br /> </td> 
   <td> Abs(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ceil</strong><br /> </td> 
   <td> Returns the lowest integer greater than or equal to a number<br /> </td> 
   <td> Ceil(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Floor</strong><br /> </td> 
   <td> Returns the greatest integer greater than or equal to a number<br /> </td> 
   <td> Floor(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mayor</strong><br /> </td> 
   <td> Returns the greater of two numbers<br /> </td> 
   <td> Greatest(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Least</strong><br /> </td> 
   <td> Returns the smaller of two numbers<br /> </td> 
   <td> Least(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mod</strong><br /> </td> 
   <td> Returns the remainder of the integer division from n1 by n2<br /> </td> 
   <td> Mod(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Porcentaje</strong><br /> </td> 
   <td> Returns the ratio of two numbers expressed as a percentage<br /> </td> 
   <td> Percent(&lt;number 1&gt;, &lt;number 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Aleatorio</strong><br /> </td> 
   <td> Returns the random value<br /> </td> 
   <td> Random()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Round</strong><br /> </td> 
   <td> Rounds off a number to n decimals<br /> </td> 
   <td> Round(&lt;number&gt;, &lt;number of decimals&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sign</strong><br /> </td> 
   <td> Returns the sign of the number<br /> </td> 
   <td> Sign(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Todouble</strong><br /> </td> 
   <td> Converts an integer to a float<br /> </td> 
   <td> ToDouble(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ToInt64</strong><br /> </td> 
   <td> Converts a float to a 64 bit integer<br /> </td> 
   <td> ToInt64(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointeger</strong><br /> </td> 
   <td> Converts a float to an integer<br /> </td> 
   <td> ToInteger(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Trunc</strong><br /> </td> 
   <td> Truncates n1 to n2 decimals<br /> </td> 
   <td> Trunc(&lt;n1&gt;, &lt;n2&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Others {#others}

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
   <td> Devuelve el valor 1 si se ha verificado la condición. Otherwise, returns value 2<br /> </td> 
   <td> Case(When(&lt;condition&gt;, &lt;value 1&gt;), Else(&lt;value 2&gt;))<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Clearbit</strong><br /> </td> 
   <td> Deletes the Flag in the value<br /> </td> 
   <td> ClearBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Coalesce</strong><br /> </td> 
   <td> Returns value 2 if value 1 is zero or null, otherwise returns value 1<br /> </td> 
   <td> Coalesce(&lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Decode</strong><br /> </td> 
   <td> Returns value 3 is value 1 = value 2, otherwise returns 4<br /> </td> 
   <td> Decode(&lt;value 1&gt;, &lt;value 2&gt;, &lt;value 3&gt;, &lt;value 4&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Else</strong><br /> </td> 
   <td> Returns value 1 (may only be used as a parameter of the case function)<br /> </td> 
   <td> Else(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getemaildomain</strong><br /> </td> 
   <td> Extracts the domain from an email address<br /> </td> 
   <td> GetEmailDomain(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getmirrorurl</strong><br /> </td> 
   <td> Retrieves the URL of the mirror page server<br /> </td> 
   <td> GetMirrorURL(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Iif</strong><br /> </td> 
   <td> Returns value 1 if the expression is true, otherwise returns value 2<br /> </td> 
   <td> Iif(&lt;condition&gt;, &lt;value 1&gt;, &lt;value 2&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isbitset</strong><br /> </td> 
   <td> Indicates whether the Flag is in the value<br /> </td> 
   <td> IsBitSet(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Isemptystring</strong><br /> </td> 
   <td> Returns value 2 if the string is empty, otherwise returns value 3<br /> </td> 
   <td> IsEmptyString(&lt;string&gt;, &lt;value 2&gt;, &lt;value 3&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Nonull</strong><br /> </td> 
   <td> Returns the empty string if the argument is NULL<br /> </td> 
   <td> NoNull(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rowid</strong><br /> </td> 
   <td> Returns the line number<br /> </td> 
   <td> RowId<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Setbit</strong><br /> </td> 
   <td> Forces the Flag in the value<br /> </td> 
   <td> SetBit(&lt;identifier&gt;, &lt;flag&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Setvar</strong><br /> </td> 
   <td> Sets a variable<br /> </td> 
   <td> SetVar(&lt;variable&gt;, &lt;expression&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Toboolean</strong><br /> </td> 
   <td> Converts a number into a Boolean<br /> </td> 
   <td> ToBoolean(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Cuando</strong><br /> </td> 
   <td> Devuelve el valor 1 si la expresión se ha verificado. Otherwise, returns value 2 (may only be used as a parameter of the case function)<br /> </td> 
   <td> When(&lt;condition&gt;, &lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Newuuid</strong><br /> </td> 
   <td> Returns a new UUID.<br /> </td> 
   <td> newUUID<br /> </td> 
  </tr> 
 </tbody> 
</table>

## String {#string}

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
   <td> Indicates if all parameters are non-null and not empty<br /> </td> 
   <td> AllNonNull2(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>AllNonNull3</strong><br /> </td> 
   <td> Indicates if all parameters are non-null and not empty<br /> </td> 
   <td> AllNonNull3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>ASCII</strong><br /> </td> 
   <td> Returns the ASCII value of the first character in the string<br /> </td> 
   <td> Ascii(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Char</strong><br /> </td> 
   <td> Returns the character corresponding to the 'n' ASCII code<br /> </td> 
   <td> Char(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Charindex</strong><br /> </td> 
   <td> Returns the position of string 2 in string 1<br /> </td> 
   <td> Charindex(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Datalength</strong><br /> </td> 
   <td> Returns the number of characters in a string<br /> </td> 
   <td> DataLength(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Getline</strong><br /> </td> 
   <td> Returns the nth (from 1 to n) line of the string<br /> </td> 
   <td> GetLine(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ifequals</strong><br /> </td> 
   <td> Returns the third parameter if the first two parameters are equal otherwise returns the last parameter<br /> </td> 
   <td> IfEquals(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ismemonull</strong><br /> </td> 
   <td> Indicates if the memo passed as a parameter is null<br /> </td> 
   <td> IsMemoNull(&lt;Memo&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Juxtwords</strong><br /> </td> 
   <td> Concatena las dos cadenas pasadas como parámetros. A space is added between each string in the returned value.<br /> </td> 
   <td> JuxtWords(&lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>JuxtWords3</strong><br /> </td> 
   <td> Concatena las tres cadenas pasadas como parámetros. A space is added between each string in the returned value.<br /> </td> 
   <td> JuxtWords3(&lt;string&gt;, &lt;string&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lpad</strong><br /> </td> 
   <td> Returns the completed string on the left<br /> </td> 
   <td> LPad(&lt;string&gt;, &lt;number&gt;, &lt;caractère&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Izquierda</strong><br /> </td> 
   <td> Returns the first n characters of the string<br /> </td> 
   <td> Left(&lt;string&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Longitud</strong><br /> </td> 
   <td> Returns the string length<br /> </td> 
   <td> Length(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Lower</strong><br /> </td> 
   <td> Returns the string in lowercase<br /> </td> 
   <td> Lower(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ltrim</strong><br /> </td> 
   <td> Removes spaces to the left of the string<br /> </td> 
   <td> Ltrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Md5Digest</strong><br /> </td> 
   <td> Returns an hexadecimal representation of the MD5 key of a string<br /> </td> 
   <td> Md5Digest(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Memocontiene</strong><br /> </td> 
   <td> Specifies whether the memo contains the string passed as a parameter<br /> </td> 
   <td> MemoContains(&lt;memo&gt;, &lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rpad</strong><br /> </td> 
   <td> Returns the completed string on the right<br /> </td> 
   <td> RPad(&lt;string&gt;, &lt;number&gt;, &lt;character&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Reemplazar</strong><br /> </td> 
   <td> Replaces all occurrences of a specified string (2nd parameter) value with another string value (3rd parameter) in a string (1st parameter)<br /> </td> 
   <td> Replace(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Derecha</strong><br /> </td> 
   <td> Returns the last n characters of the string<br /> </td> 
   <td> Right(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rtrim</strong><br /> </td> 
   <td> Removes spaces to the right of the string<br /> </td> 
   <td> Rtrim(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha256Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA256</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha256Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha384Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA384</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha384Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Sha512Digest</strong><br /> </td> 
   <td> Calculates the standard <strong>SHA512</strong> hash for a given UTF8 string<br /> </td> 
   <td> Sha512Digest(&lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Inteligente</strong><br /> </td> 
   <td> Returns the string with the first letter of each word in capitals<br /> </td> 
   <td> Smart(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Subcadena</strong><br /> </td> 
   <td> Extracts the sub-string starting at character n1 of the string and with a length of n2<br /> </td> 
   <td> Substring(&lt;string&gt;, &lt;offset&gt;, &lt;length&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tointlstring</strong><br /> </td> 
   <td> Converts the number to a string<br /> </td> 
   <td> ToIntlString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Tostring</strong><br /> </td> 
   <td> Converts the number to a string<br /> </td> 
   <td> ToString(&lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Superior</strong><br /> </td> 
   <td> Returns the string in capitals<br /> </td> 
   <td> Upper(&lt;string&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallink</strong><br /> </td> 
   <td> Returns the foreign key of a link passed as a parameter if the other two parameters are equal<br /> </td> 
   <td> VirtualLink(&lt;number&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Virtuallinkstr</strong><br /> </td> 
   <td> Returns the foreign (text) key of a link passed as a parameter if the other two parameters are equal<br /> </td> 
   <td> VirtualLinkStr(&lt;string&gt;, &lt;number&gt;, &lt;number&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcdecrypt</strong><br /> </td> 
   <td> Decrypts an encrypted value in HEX format with "<strong>x</strong>" prefix (1st parameter) using a key in HEX format (2nd parameter) and an initialization vector in HEX format (3rd parameter)<br /> </td> 
   <td> encryption_aescbcDecrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>encryption_ aescbcencrypt</strong><br /> </td> 
   <td> Codifica el uso de algoritmo AES (modo bloque CBC) una cadena de caracteres (primer parámetro) con una clave (2. º parámetro) y un vector de inicialización (tercer parámetro). The key and the initialization vector must be given in a hexadecimal representation (starting with <strong>\x</strong>). The result will be in hexadecimal without the <strong>\x</strong>.<br /> Tenga en cuenta que el tamaño de la clave puede ser de 128 bits, 192 bits, 256 bits (16, 24, 32 caracteres hexadecimales) pero le recomendamos que utilice 256 bits y un IV aleatorizado de la misma longitud que la clave.<br /> </td> 
   <td> encryption_aescbcEncrypt(&lt;String&gt;, &lt;String&gt;, &lt;String&gt;)<br /> For example: encryption_aescbcEncrypt(johndoe@example.com, "<strong>\x0123456789ABCDEF0123456789ABCDEF</strong>", "<strong>\x0123456789ABCDEFFEDCBA9876543210</strong>")<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Aggregates {#aggregates}

The aggregation functions are only available when [adding additional data](../../automating/using/query.md#enriching-data) from a workflow's **[!UICONTROL Query]** activity.

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
   <td> Returns the average in a numerical column.<br /> </td> 
   <td> Avg(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Recuento</strong>, Recuento (excepto NULL)<br /> </td> 
   <td> Counts the non-null values in a column.<br /> </td> 
   <td> Count(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Countall</strong>, Count all<br /> </td> 
   <td> Counts all of the values (including null values and duplicates).<br /> </td> 
   <td> CountAll()<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Recuento distinto y</strong>diferenciado<br /> </td> 
   <td> Counts the non-null, distinct values in a column.<br /> </td> 
   <td> Countdistinct(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Máx</strong>., Máx.<br /> </td> 
   <td> Returns the maximum value in a numerical, string, or date column.<br /> </td> 
   <td> Max(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Min</strong>, Min<br /> </td> 
   <td> Returns the minimum value in a numerical, string, or date column.<br /> </td> 
   <td> Min(&lt;value&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Suma</strong>, suma<br /> </td> 
   <td> Returns the sum of the values in a numerical column.<br /> </td> 
   <td> Sum(&lt;value&gt;)<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Representation {#representation}

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
   <td> Applies a descending sort<br /> </td> 
   <td> Desc(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Orderby</strong><br /> </td> 
   <td> Sorts the result within the partition<br /> </td> 
   <td> OrderBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Partitionby</strong><br /> </td> 
   <td> Partitions the result of a query on a table<br /> </td> 
   <td> PartitionBy(&lt;value 1&gt;)<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Rownum</strong><br /> </td> 
   <td> Genera un número de línea basado en la partición de tabla y en una secuencia de orden. This function is not supported for MySQL<br /> </td> 
   <td> RowNum(PartitionBy(&lt;value 1&gt;), OrderBy(&lt;value 1&gt;))<br /> </td> 
  </tr> 
 </tbody> 
</table>

