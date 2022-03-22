---
title: Perfil del modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 652c22a5-7fff-4d08-9396-f0b292aaca76
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1249'
ht-degree: 8%

---

# Perfil (nms:recipient)

## Descripción del objeto

<table>
               <tr>
                  <th>Nombre</th>
                  <th>Etiqueta</th>
                  <th>Tipo (longitud)</th>
                  <th>Valores de enumeración</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID del recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>age</td>
                  <td>Edad</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>appSubscription</td>
                  <td>Suscripciones a una aplicación</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>birthDate</td>
                  <td>Fecha de nacimiento</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackList</td>
                  <td>Ya no se puede contactar (por ningún canal)</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListEmail</td>
                  <td>Ya no se puede contactar por correo electrónico</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListFax</td>
                  <td>Ya no se puede contactar por fax</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListMobile</td>
                  <td>Ya no se puede contactar por SMS</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPhone</td>
                  <td>Ya no se puede contactar por teléfono</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPostalMail</td>
                  <td>Ya no se puede contactar por correo postal</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>blackListPushnotification</td>
                  <td>Ya no se puede contactar con la notificación push</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>país (países)</td>
                  <td>País</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>created</td>
                  <td>Creado</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>createdBy (userBase)</td>
                  <td>Creado por</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cryptedId</td>
                  <td>ID cifrado</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusHobbieslink (cusHobbies)</td>
                  <td>CusHobbieslink</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusLastTransactionDate</td>
                  <td>Última fecha de transacción</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusTransactionslink</td>
                  <td>Transacciones</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>domain</td>
                  <td>Dominio de correo electrónico</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Correo electrónico</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Formato del correo electrónico</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Texto - texto - 1</li>
                        <li>HTML - html - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Desconocido - desconocido - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>emailStatus (addressStatus)</td>
                  <td>Información sobre el correo electrónico</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Registros de exclusión</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>externalId</td>
                  <td>ID de recurso externo</td>
                  <td>string(100) </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>firstName</td>
                  <td>Nombre</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>gender</td>
                  <td>Sexo</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>No especificado - desconocido - 0</li>
                        <li>Hombre - Hombre - 1</li>
                        <li>Mujer - mujer - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Es un recurso externo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Última modificación</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastName</td>
                  <td>Apellido</td>
                  <td>string (50)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ubicación</td>
                  <td>Ubicación</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>logs</td>
                  <td>Registros de entregas</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>middleName</td>
                  <td>Segundo nombre</td>
                  <td>string (30)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Móvil</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>modificado por</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>Teléfono</td>
                  <td>string (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>places</td>
                  <td>Ubicaciones</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>postalAddress</td>
                  <td>Dirección postal</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>salutation</td>
                  <td>Título</td>
                  <td>string (20)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (estado)</td>
                  <td>Estado</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subHisto</td>
                  <td>Historial de suscripciones</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>suscripciones</td>
                  <td>Suscripciones</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>timeZone</td>
                  <td>Zona horaria</td>
                  <td>enumeración (cadena) (64)</td>
                  <td>
                     <ul>
                        <li>(GMT-02:00) Atlántico Central - Atlántico Sur_Georgia - Atlántico/Sur_Georgia</li>
                        <li>(GMT+02:00) Ammán - Asia_Ammán - Asia/Ammán</li>
                        <li>(GMT-03:00) Brasi - America_Sao_Paulo - América/São Paulo</li>
                        <li>(GMT+06:00) Astana, Daca - Asia_Dhaka - Asia/Daca</li>
                        <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Asia/Novosibirsk</li>
                        <li>(GMT+02:00) Windhoek - Africa_Windhoek - África/Windhoek</li>
                        <li>(GMT+04:00) Cáucaso, Erevan - Asia_Ereván - Asia/Ereván</li>
                        <li>(GMT-04:00) Manaus - America_Manaus - America/Manaus</li>
                        <li>(GMT+03:30) Teherán - Asia_Teherán - Asia/Teherán</li>
                        <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacific/Auckland</li>
                        <li>(GMT+02:00) Jerusalén - Asia_Jerusalén - Asia/Jerusalén</li>
                        <li>(GMT+03:00) Moscú, San Petersburgo, Volgogrado - Europa_Moscú - Europa/Moscú</li>
                        <li>(GMT+09:30) Adelaïde - Australia_Adelaida - Australia/Adelaida</li>
                        <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
                        <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
                        <li>(GMT+09:00) Yakoutsk - Asia_Yakutsk - Asia/Yakutsk</li>
                        <li>(GMT-10:00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
                        <li>(GMT+04:00) Bakú - Asia_Baku - Asia/Bakú</li>
                        <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
                        <li>(GMT+09:00) Seúl - Asia_Seúl - Asia/Seúl</li>
                        <li>(GMT+01:00) Sarajevo, Skoplje, Sofía, Varsovia, Zagreb - Europa_Sarajevo - Europa/Sarajevo</li>
                        <li>(GMT+04:00) Abu Dhabi, Mascate - Asia_Mascat - Asia/Mascate</li>
                        <li>(GMT+08:00) Kuala Lumpur, Singapur - Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
                        <li>(GMT+09:00) Osaka, Sapporo, Tokio - Asia_Tokio - Asia/Tokio</li>
                        <li>(GMT+10:00) Brisbane - Australia_Brisbane - Australia/Brisbane</li>
                        <li>(GMT+05:30) Sri Jayawardenepura - Asia_Colombo - Asia/Colombo</li>
                        <li>(GMT+02:00) Harare, Pretoria - Africa_Harare - África/Harare</li>
                        <li>(GMT+08:00) Oulan-Bator - Asia_Ulan_Bator - Asia/Ulan_Bator</li>
                        <li>(GMT-02:00) Hora media de Greenwich menos 2 horas - Gmt_m2 - Etc/GMT+2</li>
                        <li>(GMT-03:00) Hora media de Greenwich menos 3 horas - Gmt_m3 - Etc/GMT+3</li>
                        <li>(GMT-01:00) Hora media de Greenwich menos 1 hora - Gmt_m1 - Etc/GMT+1</li>
                        <li>(GMT-06:00) Hora media de Greenwich menos 6 horas - Gmt_m6 - Etc/GMT+6</li>
                        <li>(GMT-07:00) Hora media de Greenwich menos 7 horas - Gmt_m7 - Etc/GMT+7</li>
                        <li>(GMT-04:00) Hora media de Greenwich menos 4 horas - Gmt_m4 - Etc/GMT+4</li>
                        <li>(GMT) Casablanca - Africa_Casablanca - África/Casablanca</li>
                        <li>(GMT+05:30) Calcuta, Chennai, Mumbai, Nueva Delhi - Asia_Calcuta - Asia/Calcuta</li>
                        <li>(GMT-11:00) Hora media de Greenwich menos 11 horas - Gmt_m11 - Etc/GMT+11</li>
                        <li>(GMT-09:00) Hora media de Greenwich menos 9 horas - Gmt_m9 - Etc/GMT+9</li>
                        <li>(GMT-03:30) Terranova - America_St_Johns - América/St_Johns</li>
                        <li>(GMT+03:00) Hora media de Greenwich más 3 horas - Gmt_p3 - Etc/GMT-3</li>
                        <li>(GMT-04:30) Caracas - América_Caracas - América/Caracas</li>
                        <li>(GMT+01:00) Amsterdam, Berlín, Berna, Roma, Estocolmo, Viena - Europa_Berlín - Europa/Berlín</li>
                        <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - América/Chihuahua</li>
                        <li>(GMT+03:00) Nairobi - África_Nairobi - África/Nairobi</li>
                        <li>(GMT-04:00) Asunción - América-Asunción - América/Asunción</li>
                        <li>(GMT+03:00) Bagdad - Asia_Bagdad - Asia/Bagdad</li>
                        <li>(GMT-10:00) Hora media de Greenwich menos 10 horas - Gmt_m10 - Etc/GMT+10</li>
                        <li>(GMT-03:00) Groenlandia - America_Godthab - Estados Unidos/Godthab</li>
                        <li>(GMT+02:00) Damas - Asia_Damasco - Asia/Damasco</li>
                        <li>(GMT-11:00) Samoa - Pacífico/Samoa</li>
                        <li>(GMT-05:00) Bogotá, Lima, Quito - America_Bogotá - América/Bogotá</li>
                        <li>(GMT+01:00) Bruselas, Copenhague, Madrid, París - Europa_París - Europa/París</li>
                        <li>(GMT+08:00) Pekín, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
                        <li>(GMT+12:00) Fidji - Pacific_Fiji - Pacific/Fiji</li>
                        <li>(GMT+02:00) Atenas, Estambul, Minsk - Europa_Atenas - Europa/Atenas</li>
                        <li>(GMT+04:00) Tiflis - Asia-Tiflis - Asia/Tiflis</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>(GMT+05:45) Katmandú - Asia_Katmandú - Asia/Katmandú</li>
                        <li>(GMT-05:00) Indiana (Este) - América_Indianápolis - Estados Unidos/Indianápolis</li>
                        <li>(GMT-01:00) Islas Cabo Verde - Atlantic_Cape_Verde - Atlantic/Cabo_Verde</li>
                        <li>(GMT+04:00) Puerto Louis - India_Mauricio - India/Mauricio</li>
                        <li>(GMT+08:00) Taipei - Asia_Taipei - Asia/Taipei</li>
                        <li>(GMT+06:30) Rangún - Asia_Rangún - Asia/Rangún</li>
                        <li>(GMT+11:00) Magadán, Islas Salomón, Nueva Caledonia - Pacific_Guadalcanal - Pacífico/Guadalcanal</li>
                        <li>(GMT+02:00) El Cairo - África_El Cairo - África/El Cairo</li>
                        <li>(GMT+05:00) Iekaterinburg - Asia_Yekaterinburg - Asia/Ekaterimburgo</li>
                        <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
                        <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacific/Guam</li>
                        <li>(GMT-04:00) Hora estándar del Atlántico (Canadá) - América_Halifax - América/Halifax</li>
                        <li>(GMT) Hora media de Greenwich - GMT - GMT</li>
                        <li>Predeterminado - ninguno</li>
                        <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
                        <li>(GMT-06:00) Guadalajara, México, Monterrey - América_Ciudad_México - América/Ciudad_México</li>
                        <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
                        <li>(GMT-05:00) Este (Estados Unidos y Canadá) - América_Nueva_York - América/Nueva_York</li>
                        <li>(GMT-05:00) Hora media de Greenwich menos 5 horas - Gmt_m5 - Etc/GMT+5</li>
                        <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
                        <li>(GMT+03:00) Koweït, Riyad - Asia_Riad - Asia/Riad</li>
                        <li>(GMT-08:00) Hora media de Greenwich menos 8 horas - Gmt_m8 - Etc/GMT+8</li>
                        <li>(GMT-01:00) Las Azores - Atlantic_Azores - Atlantic/Azores</li>
                        <li>(GMT+07:00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
                        <li>(GMT) Monrovia - Africa_Monrovia - África/Monrovia</li>
                        <li>(GMT-09:00) Alaska - America_Anchorage - América/Anchorage</li>
                        <li>(GMT+01:00) Belgrado, Bratislava, Budapest, Liubliana, Praga - Europa_Belgrado - Europa/Belgrado</li>
                        <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
                        <li>(GMT+02:00) Bucarest - Europe_Bucarest - Europe/Bucarest</li>
                        <li>(GMT+05:00) Hora media de Greenwich más 5 horas - Gmt_p5 - Etc/GMT-5</li>
                        <li>(GMT+04:00) Hora media de Greenwich más 4 horas - Gmt_p4 - Etc/GMT-4</li>
                        <li>(GMT+07:00) Hora media de Greenwich más 7 horas - Gmt_p7 - Etc/GMT-7</li>
                        <li>(GMT+06:00) Hora media de Greenwich más 6 horas - Gmt_p6 - Etc/GMT-6</li>
                        <li>(GMT+01:00) Hora media de Greenwich más 1 hora - Gmt_p1 - Etc/GMT-1</li>
                        <li>(GMT-08:00) Pacífico (Estados Unidos y Canadá) - América_Los_Angeles - Estados Unidos/Los_Ángeles</li>
                        <li>(GMT+02:00) Hora media de Greenwich más 2 horas - Gmt_p2 - Etc/GMT-2</li>
                        <li>(GMT+07:00) Krasnoïarsk - Asia_Krasnoyarsk - Asia/Krasnoyarsk</li>
                        <li>(GMT+09:00) Hora media de Greenwich más 9 horas - Gmt_p9 - Etc/GMT-9</li>
                        <li>(GMT+08:00) Hora media de Greenwich más 8 horas - Gmt_p8 - Etc/GMT-8</li>
                        <li>(GMT+10:00) Hobart - Australia_Hobart - Australia/Hobart</li>
                        <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacific/Tongatapu</li>
                        <li>(GMT-06:00) América Central - America_Regina - América/Regina</li>
                        <li>(GMT-03:00) Buenos Aires, Cayena, Fortaleza - América_Buenos Aires - América/Buenos Aires</li>
                        <li>(GMT-07:00) Montañas Rocosas (Estados Unidos y Canadá) - América_Denver - América/Denver</li>
                        <li>(GMT+01:00) África Central - Oeste - África_Luanda - África/Luanda</li>
                        <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofía, Tallin, Vilnius - Europe_Helsinki - Europe/Helsinki</li>
                        <li>(GMT) Hora media de Greenwich: Dublín, Edimburgo, Lisboa, Londres - Europa_Londres - Europa/Londres</li>
                        <li>(GMT-07:00) Arizona - America_Phoenix - América/Phoenix</li>
                        <li>(GMT+02:00) Beirut - Asia_Beirut - Asia/Beirut</li>
                        <li>(GMT+04:30) Kabul - Asia_Kabul - Asia/Kabul</li>
                        <li>(GMT-06:00) Centro (Estados Unidos y Canadá) - América_Chicago - América/Chicago</li>
                        <li>(GMT+11:00) Hora media de Greenwich más 11 horas - Gmt_p11 - Etc/GMT-11</li>
                        <li>(GMT+10:00) Hora media de Greenwich más 10 horas - Gmt_p10 - Etc/GMT-10</li>
                        <li>(GMT+13:00) Hora media de Greenwich más 13 horas - Gmt_p13 - Etc/GMT-13</li>
                        <li>(GMT+12:00) Hora media de Greenwich más 12 horas - Gmt_p12 - Etc/GMT-12</li>
                        <li>(GMT-04:00) Santiago - América_Santiago - América/Santiago</li>
                        <li>(GMT-03:00) Montevideo - America_Montevideo - América/Montevideo</li>
                        <li>(GMT-04:00) Cuiaba - America_Cuiaba - América/Cuiaba</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Perfil</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>seguimiento</td>
                  <td>Registros de seguimiento</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
            </table>


## Filtros


Cumpleaños (cumpleaños)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>includeStart</td>
<td>booleano</td>
</tr>
<tr>
<td>previousUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>nextUnitsValue</td>
<td>integer</td>
</tr>
<tr>
<td>endDay</td>
<td>date</td>
</tr>
<tr>
<td>precisión</td>
<td>enumeración</td>
</tr>
<tr>
<td>relationValue</td>
<td>string</td>
</tr>
<tr>
<td>mes</td>
<td>date</td>
</tr>
<tr>
<td>operador</td>
<td>enumeración</td>
</tr>
<tr>
<td>includeEnd</td>
<td>booleano</td>
</tr>
<tr>
<td>endMonth</td>
<td>date</td>
</tr>
<tr>
<td>type</td>
<td>enumeración</td>
</tr>
<tr>
<td>day</td>
<td>date</td>
</tr>
</table>

Por correo electrónico (por correo electrónico)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>email</td>
<td>string</td>
</tr>
</table>

Por claves (byKeysProfile)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>email</td>
<td>string</td>
</tr>
</table>

Por nombre o correo electrónico (byText)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>text</td>
<td>string</td>
</tr>
</table>

Por audiencia estática (byStaticAudience)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>audiencia</td>
<td>vínculo</td>
</tr>
</table>

Clic (hasClickedDelivery)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>vínculo</td>
</tr>
</table>

Abierto (hasOpenedDelivery)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>vínculo</td>
</tr>
</table>

Perfil (perfil)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>perfil</td>
<td>vínculo</td>
</tr>
</table>

Recibido (hasReceivedDelivery)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>entrega</td>
<td>vínculo</td>
</tr>
</table>

Suscriptores (suscriptores)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>service</td>
<td>vínculo</td>
</tr>
</table>
