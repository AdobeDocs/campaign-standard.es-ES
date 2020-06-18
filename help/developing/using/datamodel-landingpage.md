---
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
page-status-flag: never-activated
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
context-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '1727'
ht-degree: 2%

---


# landingPage (nms:landingPage)

## Descripción del objeto

<table>
      <tr>
         <th>Name</th>
         <th>Etiqueta</th>
         <th>Tipo (longitud)</th>
         <th>Valores de Lista desglosada</th>
      </tr>
      <tr>
         <td>PKey</td>
         <td>ID de recurso principal</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>extraData</td>
         <td>Datos adicionales</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>adicionalLanguages</td>
         <td>Otros idiomas</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizar visitantes no identificados</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>marca (brandingBase)</td>
         <td>Marca</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>buildIn</td>
         <td>Objeto de aplicación integrado</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>caché</td>
         <td>Caché</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaña (campaignBase)</td>
         <td>Campaña</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>closeLog</td>
         <td>Registro 'Página de aterrizaje cerrada'</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>string </td>
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
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>Clave de cifrado AES</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Idioma predeterminado</td>
         <td>lista desglosada (cadena) (255)</td>
         <td>
            <ul>
               <li>Griego - el - el</li>
               <li>Inglés - en - en</li>
               <li>Chino - zh - zh</li>
               <li>Francés (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portugués (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandés (Bélgica) - nl_BE - nl_BE</li>
               <li>Noruego (Noruega) - no_NO - no_NO</li>
               <li>Holandés (Países Bajos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglés (Estados Unidos) - en_US - en_US</li>
               <li>Irlandés - ga - ga</li>
               <li>Checo - cs - cs</li>
               <li>Estonio - et - et</li>
               <li>Indonesio - id - id</li>
               <li>Español - es - es</li>
               <li>Ruso - ru - ru</li>
               <li>Holandés - nl - nl</li>
               <li>Valón - wa - wa</li>
               <li>Portugués - pt - pt</li>
               <li>Francés (Bélgica) - fr_BE - fr_BE</li>
               <li>Letón - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Inglés (Reino Unido) - en_GB - en_GB</li>
               <li>Francés - fr - fr</li>
               <li>Portugués (Brasil) - pt_BR - pt_BR</li>
               <li>Alemán - de - de</li>
               <li>Danés - da - da</li>
               <li>Finés - fi - fi</li>
               <li>Húngaro - hu - hu</li>
               <li>Sueco (Finlandia) - sv_FI - sv_FI</li>
               <li>Japonés - ja - ja</li>
               <li>Hebreo - él - él</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suecia (sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltés - mt - mt</li>
               <li>Italiano (Suiza) - it_CH - it_CH</li>
               <li>Polaco - pl - pl</li>
               <li>Esloveno - sl - sl</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (envío)</td>
         <td>Fuente de tráfico</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Descripción</td>
         <td>string (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Lenguaje de diseño</td>
         <td>lista desglosada (cadena) (255)</td>
         <td>
            <ul>
               <li>Griego - el - el</li>
               <li>Inglés - en - en</li>
               <li>Chino - zh - zh</li>
               <li>Francés (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portugués (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandés (Bélgica) - nl_BE - nl_BE</li>
               <li>Noruego (Noruega) - no_NO - no_NO</li>
               <li>Holandés (Países Bajos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglés (Estados Unidos) - en_US - en_US</li>
               <li>Irlandés - ga - ga</li>
               <li>Checo - cs - cs</li>
               <li>Estonio - et - et</li>
               <li>Indonesio - id - id</li>
               <li>Español - es - es</li>
               <li>Ruso - ru - ru</li>
               <li>Holandés - nl - nl</li>
               <li>Valón - wa - wa</li>
               <li>Portugués - pt - pt</li>
               <li>Francés (Bélgica) - fr_BE - fr_BE</li>
               <li>Letón - lv - lv</li>
               <li>Lituano - lt - lt</li>
               <li>Thai - th - th</li>
               <li>Inglés (Reino Unido) - en_GB - en_GB</li>
               <li>Francés - fr - fr</li>
               <li>Portugués (Brasil) - pt_BR - pt_BR</li>
               <li>Alemán - de - de</li>
               <li>Danés - da - da</li>
               <li>Finés - fi - fi</li>
               <li>Húngaro - hu - hu</li>
               <li>Sueco (Finlandia) - sv_FI - sv_FI</li>
               <li>Japonés - ja - ja</li>
               <li>Hebreo - él - él</li>
               <li>Coreano - ko - ko</li>
               <li>Sueco - sv - sv</li>
               <li>Suecia (sueco) - sv_SE - sv_SE</li>
               <li>Eslovaco - sk - sk</li>
               <li>Maltés - mt - mt</li>
               <li>Italiano (Suiza) - it_CH - it_CH</li>
               <li>Polaco - pl - pl</li>
               <li>Esloveno - sl - sl</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>dynamicService</td>
         <td>Servicio dinámico</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>end</td>
         <td>Fecha de caducidad</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Página de error</td>
         <td>item </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Unidad geográfica</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Páginas</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificaciónPorUrlParam</td>
         <td>Identificación por parámetros de URL</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirect</td>
         <td>URL de redirección</td>
         <td>string (4096)</td>
         <td> </td>
      </tr>
      <tr>
         <td>isExternal</td>
         <td>Es un recurso externo</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>isTemplate</td>
         <td>Template</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trabajo</td>
         <td>Trabajo</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>jobLogs</td>
         <td>“Logs”</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>label</td>
         <td>Etiqueta</td>
         <td>string (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Última modificación</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Cargando clave</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilterMapping</td>
         <td>Parámetros de la clave de carga</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>logicalStatus</td>
         <td>Estado de ejecución</td>
         <td>lista desglosada (cadena) (255)</td>
         <td>
            <ul>
               <li>En curso - iniciado - iniciado</li>
               <li>Edición: edición</li>
               <li>Finalizado - terminado - terminado</li>
               <li>Advertencia - advertencia - advertencia</li>
               <li>Erróneo - error - error</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Inicio enviando mensaje</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Mensaje transaccional</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>Modificado por</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>ID</td>
         <td>string (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Unidad organizativa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>prefill</td>
         <td>Carga previa de datos de visitante</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>programa (programBase)</td>
         <td>Programa</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL pública</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Fecha de publicación</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>completionFilter (queryFilterBase)</td>
         <td>Clave de reconciliación</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>completionFilterMapping</td>
         <td>Parámetros de Clave de reconciliación</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>completionUpdateStrategy</td>
         <td>Actualizar estrategia</td>
         <td>lista desglosada (byte) </td>
         <td>
            <ul>
               <li>Actualización - updateTarget - 1</li>
               <li>No autorizado - no autorizado - 0</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Servicio de suscripción</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Acción específica</td>
         <td>lista desglosada (byte) </td>
         <td>
            <ul>
               <li>Lista de bloqueos - blockList - 3</li>
               <li>Sin acción específica - ninguno - 0</li>
               <li>Baja - baja - 2</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
               <li>Suscripción - suscripción - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>inicio</td>
         <td>Fecha de implementación</td>
         <td>date </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>Estado</td>
         <td>lista desglosada (byte) </td>
         <td>
            <ul>
               <li>Edición - editar - 0</li>
               <li>Error al publicar: error - 99</li>
               <li>Cerrado - cerrado - 20</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
               <li>En línea - abierto - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimensión de segmentación</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>template (landingPage)</td>
         <td>Plantilla de Página de aterrizaje</td>
         <td>link </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>Probar URL</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>thumbnail</td>
         <td>Miniatura</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>timezone</td>
         <td>Zona horaria</td>
         <td>lista desglosada (cadena) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Atlántico Central - Atlántico_Sur_Georgia - Atlántico/Sur_Georgia</li>
               <li>(GMT+02:00) Ammán - Asia_Ammán - Asia/Ammán</li>
               <li>(GMT-03:00) Brasi - América_São Paulo - América/São Paulo</li>
               <li>(GMT+06:00) Astana, Daca - Asia_Dhaka - Asia/Dhaka</li>
               <li>(GMT+06:00) Novossibirsk - Asia_Novosibirsk - Asia/Novosibirsk</li>
               <li>(GMT+02:00) Windhoek - Africa_Windhoek - África/Windhoek</li>
               <li>(GMT+04:00) Cáucaso, Erevan - Asia_Ereván - Asia/Ereván</li>
               <li>(GMT-04:00) Manaus - Estados Unidos-Manaus - Estados Unidos/Manaus</li>
               <li>(GMT+03:30) Teherán - Asia_Teherán - Asia/Teherán</li>
               <li>(GMT+12:00) Auckland, Wellington - Pacific_Auckland - Pacífico/Auckland</li>
               <li>(GMT+02:00) Jerusalén - Asia_Jerusalén - Asia/Jerusalén</li>
               <li>(GMT+03:00) Moscú, San Petersburgo, Volgogrado - Europa_Moscú - Europa/Moscú</li>
               <li>(GMT+09:30) Adelaïde - Australia_Adelaide - Australia/Adelaida</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sydney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth - Australia_Perth - Australia/Perth</li>
               <li>(GMT+09:00) Yakoutsk - Asia_Yakutsk - Asia/Yakutsk</li>
               <li>(GMT-10:00) Hawai - Pacific_Honolulu - Pacific/Honolulu</li>
               <li>(GMT+04:00) Bakú - Asia_Bakú - Asia/Bakú</li>
               <li>(GMT+10:00) Vladivostok - Asia_Vladivostok - Asia/Vladivostok</li>
               <li>(GMT+09:00) Seúl - Asia_Seúl - Asia/Seúl</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofía, Varsovia, Zagreb - Europa_Sarajevo - Europa/Sarajevo</li>
               <li>Zona horaria del servidor - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Mascate - Asia_Mascate - Asia/Mascate</li>
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
               <li>(GMT-07:00) Hora del meridiano de Greenwich menos 7 horas - Gmt_m7 - Etc/GMT+7</li>
               <li>(GMT-04:00) Hora media de Greenwich menos 4 horas - Gmt_m4 - Etc/GMT+4</li>
               <li>(GMT) Casablanca - Africa_Casablanca - África/Casablanca</li>
               <li>(GMT+05:30) Calcuta, Chennai, Mumbai, Nueva Delhi - Asia_Calcuta - Asia/Calcuta</li>
               <li>(GMT-11:00) Hora media de Greenwich menos 11 horas - Gmt_m11 - Etc/GMT+11</li>
               <li>(GMT-09:00) Hora media de Greenwich menos 9 horas - Gmt_m9 - Etc/GMT+9</li>
               <li>(GMT-03:30) Terranova - América_St_Johns - América/St_Johns</li>
               <li>Predeterminado - _inherit_ - _inherit_</li>
               <li>(GMT+03:00) Hora media de Greenwich más 3 horas - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - América_Caracas - América/Caracas</li>
               <li>(GMT+01:00) Amsterdam, Berlín, Berna, Roma, Estocolmo, Viena - Europa_Berlín - Europa/Berlín</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlan - America_Chihuahua - América/Chihuahua</li>
               <li>(GMT+03:00) Nairobi - África_Nairobi - África/Nairobi</li>
               <li>(GMT-04:00) Asunción - América_Asunción - América/Asunción</li>
               <li>(GMT+03:00) Bagdad - Asia_Bagdad - Asia/Bagdad</li>
               <li>(GMT-10:00) Hora media de Greenwich menos 10 horas - Gmt_m10 - Etc/GMT+10</li>
               <li>(GMT-03:00) Groenlandia - América_Godthab - América/Godthab</li>
               <li>(GMT+02:00) Damas - Asia_Damasco - Asia/Damasco</li>
               <li>(GMT-11:00) Samoa - Pacífico-Samoa - Pacífico/Samoa</li>
               <li>(GMT-05:00) Bogotá, Lima, Quito - América_Bogotá - América/Bogotá</li>
               <li>(GMT+01:00) Bruselas, Copenhague, Madrid, París - Europa_París - Europa/París</li>
               <li>(GMT+08:00) Pekín, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacífico_Fiyi - Pacífico/Fiyi</li>
               <li>(GMT+02:00) Atenas, Estambul, Minsk - Europa_Atenas - Europa/Atenas</li>
               <li>(GMT+04:00) Tiflis - Asia-Tiflis - Asia/Tiflis</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
               <li>(GMT+05:45) Katmandú - Asia_Katmandú - Asia/Katmandú</li>
               <li>(GMT-05:00) Indiana (Este) - América_Indianápolis - Estados Unidos/Indianápolis</li>
               <li>(GMT-01:00) Islas de Cabo Verde - Atlantic_Cape_Verde - Atlantic/Cape_Verde</li>
               <li>(GMT+04:00) Port Louis - Indian_Mauricio - Indian/Mauricio</li>
               <li>(GMT+08:00) Taipei - Asia_Taipei - Asia/Taipei</li>
               <li>Zona horaria de la base de datos - _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangún - Asia_Rangún - Asia/Rangún</li>
               <li>(GMT+11:00) Magadán, Islas Salomón, Nueva Caledonia - Pacific_Guadalcanal - Pacífico/Guadalcanal</li>
               <li>(GMT+02:00) El Cairo - África_El Cairo - África/El Cairo</li>
               <li>(GMT+05:00) Iekaterinburg - Asia_Ekaterinburgo - Asia/Ekaterimburgo</li>
               <li>(GMT+08:00) Irkoutsk - Asia_Irkutsk - Asia/Irkutsk</li>
               <li>(GMT+10:00) Guam, Port Moresby - Pacific_Guam - Pacífico/Guam</li>
               <li>(GMT-04:00) Hora estándar del Atlántico (Canadá) - América_Halifax - América/Halifax</li>
               <li>(GMT) Hora media de Greenwich - GMT - GMT</li>
               <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
               <li>Zona horaria del operador - _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, México, Monterrey - América_Ciudad_México - América/Ciudad_México</li>
               <li>(GMT+09:30) Darwin - Australia_Darwin - Australia/Darwin</li>
               <li>(GMT-05:00) Este (Estados Unidos y Canadá) - América_Nueva_York - América/Nueva_York</li>
               <li>(GMT-05:00) Hora del meridiano de Greenwich menos 5 horas - Gmt_m5 - Etc/GMT+5</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent - Asia_Karachi - Asia/Karachi</li>
               <li>(GMT+03:00) Koweït, Riyad - Asia_Riyadh - Asia/Riad</li>
               <li>(GMT-08:00) Hora media de Greenwich menos 8 horas - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) Las Azores - Atlantic_Azores - Atlantic/Azores</li>
               <li>(GMT+07:00) Bangkok, Hanoi, Djakarta - Asia_Bangkok - Asia/Bangkok</li>
               <li>(GMT) Monrovia - Africa_Monrovia - África/Monrovia</li>
               <li>(GMT-09:00) Alaska - America_Anchorage - América/Anchorage</li>
               <li>(GMT+01:00) Belgrado, Bratislava, Budapest, Liubliana, Praga - Europa_Belgrado - Europa/Belgrado</li>
               <li>(GMT) Reykjavik - Atlantic_Reykjavik - Atlantic/Reykjavik</li>
               <li>(GMT+02:00) Bucarest - Europe_Bucarest - Europa/Bucarest</li>
               <li>(GMT+05:00) Hora media de Greenwich más 5 horas - Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00) Hora media de Greenwich más 4 horas - Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00) Hora media de Greenwich más 7 horas - Gmt_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00) Hora media de Greenwich más 6 horas - Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00) Hora media de Greenwich más 1 hora - Gmt_p1 - Etc/GMT-1</li>
               <li>(GMT-08:00) Pacífico (Estados Unidos y Canadá) - América_Los_Ángeles - América/Los_Ángeles</li>
               <li>(GMT+02:00) Hora media de Greenwich más 2 horas - Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00) Krasnoïarsk - Asia_Krasnoyarsk - Asia/Krasnoyarsk</li>
               <li>(GMT+09:00) Hora media de Greenwich más 9 horas - Gmt_p9 - Etc/GMT-9</li>
               <li>(GMT+08:00) Hora media de Greenwich más 8 horas - Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00) Hobart - Australia_Hobart - Australia/Hobart</li>
               <li>(GMT+13:00) Nuku'alofa - Pacific_Tongatapu - Pacífico/Tongatapu</li>
               <li>(GMT-06:00) América Central - América_Regina - América/Regina</li>
               <li>(GMT-03:00) Buenos Aires, Cayena, Fortaleza - América_Buenos Aires - América/Buenos Aires</li>
               <li>(GMT-07:00) Montañas Rocosas (Estados Unidos y Canadá) - América_Denver - América/Denver</li>
               <li>(GMT+01:00) África Central - Oeste - Africa_Luanda - África/Luanda</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofía, Tallin, Vilnius - Europe_Helsinki - Europa/Helsinki</li>
               <li>(GMT) Hora del meridiano de Greenwich: Dublín, Edimburgo, Lisboa, Londres - Europa_Londres - Europa/Londres</li>
               <li>(GMT-07:00) Arizona - America_Phoenix - América/Phoenix</li>
               <li>(GMT+02:00) Beirut - Asia_Beirut - Asia/Beirut</li>
               <li>(GMT+04:30) Kabul - Asia_Kabul - Asia/Kabul</li>
               <li>(GMT-06:00) Centro (Estados Unidos y Canadá) - América_Chicago - América/Chicago</li>
               <li>(GMT+11:00) Hora media de Greenwich más 11 horas - Gmt_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00) Hora media de Greenwich más 10 horas - Gmt_p10 - Etc/GMT-10</li>
               <li>(GMT+13:00) Hora media de Greenwich más 13 horas - Gmt_p13 - Etc/GMT-13</li>
               <li>(GMT+12:00) Hora media de Greenwich más 12 horas - Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00) Santiago - América_Santiago - América/Santiago</li>
               <li>(GMT-03:00) Montevideo - América_Montevideo - América/Montevideo</li>
               <li>(GMT-04:00) Cuiaba - America_Cuiaba - América/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>título</td>
         <td>Página de aterrizaje</td>
         <td>string (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingEnabled</td>
         <td>Respuestas al registro</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>trackingUrlName</td>
         <td>Nombre de URL de seguimiento</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>type</td>
         <td>Tipo</td>
         <td>lista desglosada (byte) </td>
         <td>
            <ul>
               <li>Genérico - genérico - 0</li>
               <li>Baja de un servicio - baja - 3</li>
               <li>Lista de bloqueos - blockList - 4</li>
               <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
               <li>Adquisición - adquisición - 1</li>
               <li>Suscripción a un servicio - suscripción - 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID de seguridad</td>
         <td>string </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Habilitar el seguimiento web</td>
         <td>booleano </td>
         <td> </td>
      </tr>
   </table>

## Filtros

Por estado lógico (byLogicalStatus)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>lista desglosada</td>
    </tr>
</table>

Por nombre o etiqueta (byText)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>texto</td>
    <td>string</td>
    </tr>
</table>

Por estado (byState)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>lista desglosada</td>
    </tr>
</table>

Mediante el recurso de segmentación (byTargetResource)

<table>
<tr>
<th>Name</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>

Incluir páginas de aterrizaje avanzadas (conAvanzado)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzado</td>
    <td>booleano</td>
    </tr>
</table>

Incluir envíos continuos de una lista heterogénea (conContinuo)

<table>
        <tr>
        <th>Name</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>booleano</td>
        </tr>
    </table>

Presente durante un período determinado (porCalendario)

<table>
        <tr>
        <th>Name</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>date</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>date</td>
        </tr>
    </table>

Publicado durante un período determinado (porPlanning)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>
