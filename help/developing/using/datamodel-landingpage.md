---
title: Página de aterrizaje del modelo de datos
description: Obtenga información sobre el modelo de datos
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: Data Model
role: Developer
level: Experienced
exl-id: bd12a214-5998-4fb9-9f54-0c886067b58b
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '1817'
ht-degree: 7%

---

# landingPage (nms:landingPage)

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
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalData</td>
         <td>Datos adicionales</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>additionalLanguages</td>
         <td>Otros idiomas</td>
         <td>elemento </td>
         <td> </td>
      </tr>
      <tr>
         <td>allowNonIdentifiedTarget</td>
         <td>Autorizar visitantes no identificados</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>personalización de marca (brandingBase)</td>
         <td>Marca</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>builtIn</td>
         <td>Objeto de aplicación integrado</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>escondrijo</td>
         <td>Caché</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>campaign (campaignBase)</td>
         <td>Campaña</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>closedLog</td>
         <td>Registro "Página de aterrizaje cerrada"</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>contextResourceType</td>
         <td>ContextResourceType</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>created</td>
         <td>Creado</td>
         <td>fecha </td>
         <td> </td>
      </tr>
      <tr>
         <td>createdBy (userBase)</td>
         <td>Creado por</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>cryptKey</td>
         <td>Clave de cifrado AES</td>
         <td>cadena (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>defaultLanguage</td>
         <td>Idioma predeterminado</td>
         <td>enumeración (cadena) (255)</td>
         <td>
            <ul>
               <li>Griego - el - el</li>
               <li>Inglés - en - en</li>
               <li>Chino: zh: zh</li>
               <li>Francés (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portugués (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandés (Bélgica) - nl_BE - nl_BE</li>
               <li>Noruego (Noruega) - no_NO - no_NO</li>
               <li>Neerlandés (Países Bajos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglés (Estados Unidos) - en_US - en_US</li>
               <li>Irlandés - ga - ga</li>
               <li>Checo - cs - cs</li>
               <li>Estonio - et - et</li>
               <li>Indonesio - id - id</li>
               <li>Español - es - es</li>
               <li>Ruso - ru - ru</li>
               <li>Neerlandés - nl - nl</li>
               <li>Valón - wa - wa</li>
               <li>Portugués - pt - pt</li>
               <li>Francés (Bélgica) - fr_BE - fr_BE</li>
               <li>Letón: lv: lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandés: th - th</li>
               <li>Inglés (Reino Unido) - en_GB - en_GB</li>
               <li>Francés - fr - fr</li>
               <li>Portugués (Brasil) - pt_BR - pt_BR</li>
               <li>Alemán - de - de</li>
               <li>Danés: da: da</li>
               <li>Finés - fi - fi</li>
               <li>Húngaro: hu - hu</li>
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
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>defaultOrigin (envío)</td>
         <td>Fuente de tráfico</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>desc</td>
         <td>Descripción</td>
         <td>cadena (512)</td>
         <td> </td>
      </tr>
      <tr>
         <td>designLanguage</td>
         <td>Lenguaje de diseño</td>
         <td>enumeración (cadena) (255)</td>
         <td>
            <ul>
               <li>Griego - el - el</li>
               <li>Inglés - en - en</li>
               <li>Chino: zh: zh</li>
               <li>Francés (Francia) - fr_FR - fr_FR</li>
               <li>Vietnamita - vi - vi</li>
               <li>Portugués (Portugal) - pt_PT - pt_PT</li>
               <li>Italiano (Italia) - it_IT - it_IT</li>
               <li>Italiano - it - it</li>
               <li>Holandés (Bélgica) - nl_BE - nl_BE</li>
               <li>Noruego (Noruega) - no_NO - no_NO</li>
               <li>Neerlandés (Países Bajos) - nl_NL - nl_NL</li>
               <li>Árabe - ar - ar</li>
               <li>Inglés (Estados Unidos) - en_US - en_US</li>
               <li>Irlandés - ga - ga</li>
               <li>Checo - cs - cs</li>
               <li>Estonio - et - et</li>
               <li>Indonesio - id - id</li>
               <li>Español - es - es</li>
               <li>Ruso - ru - ru</li>
               <li>Neerlandés - nl - nl</li>
               <li>Valón - wa - wa</li>
               <li>Portugués - pt - pt</li>
               <li>Francés (Bélgica) - fr_BE - fr_BE</li>
               <li>Letón: lv: lv</li>
               <li>Lituano - lt - lt</li>
               <li>Tailandés: th - th</li>
               <li>Inglés (Reino Unido) - en_GB - en_GB</li>
               <li>Francés - fr - fr</li>
               <li>Portugués (Brasil) - pt_BR - pt_BR</li>
               <li>Alemán - de - de</li>
               <li>Danés: da: da</li>
               <li>Finés - fi - fi</li>
               <li>Húngaro: hu - hu</li>
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
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
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
         <td>fin</td>
         <td>Fecha de vencimiento</td>
         <td>fecha </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorContextResourceType</td>
         <td>ErrorContextResourceType</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>errorPage</td>
         <td>Página de error</td>
         <td>elemento </td>
         <td> </td>
      </tr>
      <tr>
         <td>geoUnit (geoUnitBase)</td>
         <td>Unidad geográfica</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>htmlPage</td>
         <td>Páginas</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>identificationByUrlParam</td>
         <td>Identificación por parámetros de URL</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>inactiveUrlRedirection</td>
         <td>URL de redirección</td>
         <td>cadena (4096)</td>
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
         <td>Plantilla</td>
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
         <td>Registros</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>etiqueta</td>
         <td>Etiqueta</td>
         <td>cadena (128)</td>
         <td> </td>
      </tr>
      <tr>
         <td>lastModified</td>
         <td>Última modificación</td>
         <td>fecha </td>
         <td> </td>
      </tr>
      <tr>
         <td>loadingFilter (queryFilterBase)</td>
         <td>Cargando clave</td>
         <td>vincular </td>
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
         <td>enumeración (cadena) (255)</td>
         <td>
            <ul>
               <li>En curso: iniciado, iniciado</li>
               <li>Edición - edición - edición</li>
               <li>Finalizado - terminado - terminado</li>
               <li>Advertencia: advertencia: advertencia</li>
               <li>Erróneo: error: error</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>messageAction</td>
         <td>Iniciar el envío del mensaje</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>messageActionDelivery (deliveryMCTemplateBase)</td>
         <td>Mensaje transaccional</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>modifiedBy (userBase)</td>
         <td>Modificado por</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>name</td>
         <td>Identificación</td>
         <td>cadena (64)</td>
         <td> </td>
      </tr>
      <tr>
         <td>orgUnit (orgUnitBase)</td>
         <td>Entidades organizativas</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>prerrellenar</td>
         <td>Precargar datos de visitantes</td>
         <td>booleano </td>
         <td> </td>
      </tr>
      <tr>
         <td>program (programBase)</td>
         <td>Programa</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicUrl</td>
         <td>URL pública</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>publicationDate</td>
         <td>Fecha de publicación</td>
         <td>fecha </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilter (queryFilterBase)</td>
         <td>Clave de conciliación</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationFilterMapping</td>
         <td>Parámetros clave de reconciliación</td>
         <td>colección </td>
         <td> </td>
      </tr>
      <tr>
         <td>reconciliationUpdateStrategy</td>
         <td>Actualizar estrategia</td>
         <td>enumeración (byte) </td>
         <td>
            <ul>
               <li>Actualizar - updateTarget - 1</li>
               <li>No autorizado - no autorizado - 0</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>service (serviceBase)</td>
         <td>Servicio de suscripción</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>specificAction</td>
         <td>Acción específica</td>
         <td>enumeración (byte) </td>
         <td>
            <ul>
               <li>Lista negra - 3</li>
               <li>Sin acción específica - ninguna - 0</li>
               <li>Baja - baja - 2</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
               <li>Suscripción - suscripción - 1</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>start</td>
         <td>Fecha de implementación</td>
         <td>fecha </td>
         <td> </td>
      </tr>
      <tr>
         <td>state</td>
         <td>Estado</td>
         <td>enumeración (byte) </td>
         <td>
            <ul>
               <li>Edición - editar - 0</li>
               <li>Error de publicación - error - 99</li>
               <li>Cerrado - cerrado - 20</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
               <li>Online - abierto - 10</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>targetResource</td>
         <td>Dimensión de segmentación</td>
         <td>cadena (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>plantilla (landingPage)</td>
         <td>Plantilla de página de aterrizaje</td>
         <td>vincular </td>
         <td> </td>
      </tr>
      <tr>
         <td>testUrl</td>
         <td>URL de prueba</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>miniatura</td>
         <td>Miniatura</td>
         <td>cadena (255)</td>
         <td> </td>
      </tr>
      <tr>
         <td>timezone</td>
         <td>Zona horaria</td>
         <td>enumeración (cadena) (64)</td>
         <td>
            <ul>
               <li>(GMT-02:00) Atlántico Central (Atlántico_Sur_Georgia) (Atlántico/Georgia_del_Sur)</li>
               <li>(GMT+02:00) Amán (Asia_Amán) (Asia/Amán)</li>
               <li>(GMT-03:00) Brasi (América_São_Paulo) (América/São_Paulo)</li>
               <li>(GMT+06:00) Astana, Daca (Asia_Daca), Asia/Daca</li>
               <li>(GMT+06:00) Novossibirsk (Asia_Novosibirsk) (Asia/Novosibirsk)</li>
               <li>(GMT+02:00) Windhoek (África_Windhoek) (África/Windhoek)</li>
               <li>(GMT+04:00) Cáucaso, Ereván (Asia_Ereván) (Asia/Ereván)</li>
               <li>(GMT-04:00) Manaos (América_Manaos) (América/Manaos)</li>
               <li>(GMT+03:30) Teherán (Asia_Teherán) Asia/Teherán</li>
               <li>(GMT+12:00) Auckland, Wellington (Pacífico_Auckland) - Pacífico/Auckland</li>
               <li>(GMT+02:00) Jerusalén - Asia_Jerusalén - Asia/Jerusalén</li>
               <li>(GMT+03:00) Moscú, San Petersburgo, Volgogrado - Europa_Moscú - Europa/Moscú</li>
               <li>(GMT+09:30) Adelaïde (Australia_Adelaida) (Australia/Adelaida)</li>
               <li>(GMT+10:00) Canberra, Melbourne, Sídney - Australia_Canberra - Australia/Canberra</li>
               <li>(GMT+08:00) Perth (Australia_Perth) - Australia/Perth</li>
               <li>(GMT+09:00) Yakutsk (Asia_Yakutsk) (Asia/Yakutsk)</li>
               <li>(GMT-10:00) Hawái - Pacífico_Honolulu - Pacífico/Honolulu</li>
               <li>(GMT+04:00) Bakú (Asia_Bakú) - Asia/Bakú</li>
               <li>(GMT+10:00) Vladivostok (Asia_Vladivostok) (Asia/Vladivostok)</li>
               <li>(GMT+09:00) Seúl (Asia_Seúl) - Asia/Seúl</li>
               <li>(GMT+01:00) Sarajevo, Skoplje, Sofía, Varsovia, Zagreb - Europa_Sarajevo - Europa/Sarajevo</li>
               <li>Zona horaria del servidor - _server_ - _server_</li>
               <li>(GMT+04:00) Abu Dhabi, Mascate (Asia_Mascate), Asia/Mascate</li>
               <li>(GMT+08:00) Kuala Lumpur, Singapur - Asia_Kuala_Lumpur - Asia/Kuala_Lumpur</li>
               <li>(GMT+09:00) Osaka, Sapporo, Tokio - Asia_Tokio - Asia/Tokio</li>
               <li>(GMT+10:00) Brisbane (Australia_Brisbane) Australia/Brisbane</li>
               <li>(GMT+05:30) Sri Jayawardenepura (Asia_Colombo), Asia/Colombo</li>
               <li>(GMT+02:00) Harare, Pretoria - África_Harare - África/Harare</li>
               <li>(GMT+08:00) Oulan-Bator - Asia_Ulán_Bator - Asia/Ulán_Bator</li>
               <li>(GMT-02:00) Hora de Greenwich menos 2 horas - Gmt_m2 - Etc/GMT+2</li>
               <li>(GMT-03:00) Hora de Greenwich menos 3 horas (Gmt_m3 - Etc/GMT+3)</li>
               <li>(GMT-01:00) Hora de Greenwich menos 1 hora (Gmt_m1 - Etc/GMT+1)</li>
               <li>(GMT-06:00) Hora de Greenwich (Greenwich Mean Time) menos 6 horas (Gmt_m6) (Etc/GMT+6)</li>
               <li>(GMT-07:00) Hora de Greenwich (Greenwich Mean Time) menos 7 horas (Gmt_m7) (Etc/GMT+7)</li>
               <li>(GMT-04:00) Hora de Greenwich (Greenwich Mean Time) menos 4 horas (Gmt_m4) (Etc/GMT+4)</li>
               <li>(GMT) Casablanca - África_Casablanca - África/Casablanca</li>
               <li>(GMT+05:30) Calcuta, Chennai, Bombay, Nueva Delhi (Asia_Calcuta - Asia/Calcuta)</li>
               <li>(GMT-11:00) Hora de Greenwich menos 11 horas (Gmt_m11 - Etc/GMT+11)</li>
               <li>(GMT-09:00) Hora de Greenwich (Greenwich Mean Time) menos 9 horas (Gmt_m9) (Etc/GMT+9)</li>
               <li>(GMT-03:30) Terranova - América_St_Johns - América/St_Johns</li>
               <li>Predeterminado - _inherit_ - _inherit_</li>
               <li>(GMT+03:00) Hora de Greenwich más 3 horas - Gmt_p3 - Etc/GMT-3</li>
               <li>(GMT-04:30) Caracas - América_Caracas - América/Caracas</li>
               <li>(GMT+01:00) Ámsterdam, Berlín, Berna, Roma, Estocolmo, Viena - Europa_Berlín - Europa/Berlín</li>
               <li>(GMT-07:00) Chihuahua, La Paz, Mazatlán - América_Chihuahua - América/Chihuahua</li>
               <li>(GMT+03:00) Nairobi (África_Nairobi) (África/Nairobi)</li>
               <li>(GMT-04:00) Asunción - América_Asunción - América/Asunción</li>
               <li>(GMT+03:00) Bagdad (Asia_Bagdad) (Asia/Bagdad)</li>
               <li>(GMT-10:00) Hora de Greenwich menos 10 horas (Gmt_m10) (Etc/GMT+10)</li>
               <li>(GMT-03:00) Groenlandia (América_Godthab) (América/Godthab)</li>
               <li>(GMT+02:00) Damas (Asia_Damasco) (Asia/Damasco)</li>
               <li>(GMT-11:00) Samoa - Pacífico_Samoa - Pacífico/Samoa</li>
               <li>(GMT-05:00) Bogotá, Lima, Quito - América_Bogotá - América/Bogotá</li>
               <li>(GMT+01:00) Bruselas, Copenhague, Madrid, París - Europa_París - Europa/París</li>
               <li>(GMT+08:00) Pekín, Chongqing, Hong Kong, Urumqi - Asia_Shanghai - Asia/Shanghai</li>
               <li>(GMT+12:00) Fidji - Pacífico_Fiji - Pacífico/Fiji</li>
               <li>(GMT+02:00) Atenas, Estambul, Minsk - Europa_Atenas - Europa/Atenas</li>
               <li>(GMT+04:00) Tiflis (Asia_Tiflis) (Asia/Tiflis)</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
               <li>(GMT+05:45) Katmandú (Asia_Katmandú) (Asia/Katmandú)</li>
               <li>(GMT-05:00) Indiana (Este) - América_Indianápolis - América/Indianápolis</li>
               <li>(GMT-01:00) Islas de Cabo Verde - Atlántico_Cabo_Verde - Atlántico/Cabo_Verde</li>
               <li>(GMT+04:00) Port Louis (Índico_Mauricio) (Índico/Mauricio)</li>
               <li>(GMT+08:00) Taipéi (Asia_Taipéi) (Asia/Taipéi)</li>
               <li>Zona horaria de la base de datos: _wdbc_ - _wdbc_</li>
               <li>(GMT+06:30) Rangún (Asia_Rangún) (Asia/Rangún)</li>
               <li>(GMT+11:00) Magadán, Islas Salomón, Nueva Caledonia - Pacífico_Guadalcanal - Pacífico/Guadalcanal</li>
               <li>(GMT+02:00) El Cairo (África_Cairo) (África/El_Cairo)</li>
               <li>(GMT+05:00) Iekaterinburgo (Asia_Ekaterinburgo) Asia/Ekaterinburgo</li>
               <li>(GMT+08:00) Irkoutsk (Asia_Irkutsk) (Asia/Irkutsk)</li>
               <li>(GMT+10:00) Guam, Puerto Moresby - Pacífico_Guam - Pacífico/Guam</li>
               <li>(GMT-04:00) Hora Estándar del Atlántico (Canadá) - América_Halifax - América/Halifax</li>
               <li>(GMT) Hora de Greenwich (GMT) - GMT</li>
               <li>(GMT-04:00) La Paz - América_La_Paz - América/La_Paz</li>
               <li>Zona horaria del operador: _login_ - _login_</li>
               <li>(GMT-06:00) Guadalajara, México, Monterrey - América_Ciudad_de_México - América/Ciudad_de_México</li>
               <li>(GMT+09:30) Darwin (Australia_Darwin) (Australia/Darwin)</li>
               <li>(GMT-05:00) Est (Estados Unidos y Canadá) - América_Nueva_York - América/Nueva_York</li>
               <li>(GMT-05:00) Hora de Greenwich menos 5 horas (Gmt_m5, Etc/GMT+5)</li>
               <li>(GMT+05:00) Islamabad, Karachi, Tachkent (Asia_Karachi), Asia/Karachi</li>
               <li>(GMT+03:00) Koweït, Riad (Asia_Riad), Asia/Riad</li>
               <li>(GMT-08:00) Hora de Greenwich menos 8 horas - Gmt_m8 - Etc/GMT+8</li>
               <li>(GMT-01:00) Azores - Azores_Atlánticas - Atlántico/Azores</li>
               <li>(GMT+07:00) Bangkok, Hanói, Yakarta (Asia_Bangkok), Asia/Bangkok</li>
               <li>(GMT) Monrovia - África_Monrovia - África/Monrovia</li>
               <li>(GMT-09:00) Alaska (América_Anchorage) (América/Anchorage)</li>
               <li>(GMT+01:00) Belgrado, Bratislava, Budapest, Ljubljana, Praga - Europa_Belgrado - Europa/Belgrado</li>
               <li>(GMT) Reikiavik - Atlántico_Reikiavik - Atlántico/Reikiavik</li>
               <li>(GMT+02:00) Bucarest (Europa_Bucarest) - Europa/Bucarest</li>
               <li>(GMT+05:00) Hora de Greenwich más 5 horas - Gmt_p5 - Etc/GMT-5</li>
               <li>(GMT+04:00) Hora de Greenwich más 4 horas - Gmt_p4 - Etc/GMT-4</li>
               <li>(GMT+07:00) Hora de Greenwich más 7 horas - Gmt_p7 - Etc/GMT-7</li>
               <li>(GMT+06:00) Hora de Greenwich más 6 horas - Gmt_p6 - Etc/GMT-6</li>
               <li>(GMT+01:00) Hora de Greenwich más 1 hora (Gmt_p1 - Etc/GMT-1)</li>
               <li>(GMT-08:00) Pacífico (Estados Unidos y Canadá) - América_Los_Ángeles - América/Los_Ángeles</li>
               <li>(GMT+02:00) Hora de Greenwich más 2 horas - Gmt_p2 - Etc/GMT-2</li>
               <li>(GMT+07:00) Krasnoïarsk (Asia_Krasnoyarsk) (Asia/Krasnoyarsk)</li>
               <li>(GMT+09:00) Hora de Greenwich más 9 horas - Gmt_p9 - Etc/GMT-9</li>
               <li>(GMT+08:00) Hora de Greenwich más 8 horas - Gmt_p8 - Etc/GMT-8</li>
               <li>(GMT+10:00) Hobart (Australia_Hobart) (Australia/Hobart)</li>
               <li>(GMT+13:00) Nuku'alofa - Pacífico_Tongatapu - Pacífico/Tongatapu</li>
               <li>(GMT-06:00) América Central (América_Regina) (América/Regina)</li>
               <li>(GMT-03:00) Buenos Aires, Cayena, Fortaleza - América_Buenos_Aires - América/Buenos_Aires</li>
               <li>(GMT-07:00) Montañas Rocosas (Estados Unidos y Canadá) - América_Denver - América/Denver</li>
               <li>(GMT+01:00) África Central (Oeste) (África_Luanda) (África/Luanda)</li>
               <li>(GMT+02:00) Helsinki, Kiev, Riga, Sofía, Tallin, Vilna - Europe_Helsinki - Europe/Helsinki</li>
               <li>(GMT) Hora de Greenwich: Dublín, Edimburgo, Lisboa, Londres - Europa_Londres - Europa/Londres</li>
               <li>(GMT-07:00) Arizona (América_Phoenix) (América/Phoenix)</li>
               <li>(GMT+02:00) Beirut - Asia_Beirut - Asia/Beirut</li>
               <li>(GMT+04:30) Kabul - Asia_Kabul - Asia/Kabul</li>
               <li>(GMT-06:00) Centro (Estados Unidos y Canadá) - América_Chicago - América/Chicago</li>
               <li>(GMT+11:00) Hora de Greenwich más 11 horas - Gmt_p11 - Etc/GMT-11</li>
               <li>(GMT+10:00) Hora de Greenwich más 10 horas (Gmt_p10) (Etc/GMT-10)</li>
               <li>(GMT+13:00) Hora de Greenwich más 13 horas (Gmt_p13) (Etc/GMT-13)</li>
               <li>(GMT+12:00) Hora de Greenwich más 12 horas - Gmt_p12 - Etc/GMT-12</li>
               <li>(GMT-04:00) Santiago - América_Santiago - América/Santiago</li>
               <li>(GMT-03:00) Montevideo - América_Montevideo - América/Montevideo</li>
               <li>(GMT-04:00) Cuiaba (América_Cuiaba)/América/Cuiaba</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>título</td>
         <td>Página de aterrizaje</td>
         <td>cadena (255)</td>
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
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>tipo</td>
         <td>Tipo</td>
         <td>enumeración (byte) </td>
         <td>
            <ul>
               <li>Genérico - genérico - 0</li>
               <li>Baja de un servicio: baja - 3</li>
               <li>Lista negra - blackList - 4</li>
               <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
               <li>Adquisición - Adquisición - 1</li>
               <li>Suscripción a un servicio: suscripción: 2</li>
            </ul>
         </td>
      </tr>
      <tr>
         <td>uuid</td>
         <td>ID de seguridad</td>
         <td>cadena </td>
         <td> </td>
      </tr>
      <tr>
         <td>webTrackingEnabled</td>
         <td>Habilitar seguimiento web</td>
         <td>booleano </td>
         <td> </td>
      </tr>
   </table>

## Filtros

Por estado lógico (byLogicalStatus)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeración</td>
    </tr>
</table>

Por nombre o etiqueta (por texto)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>texto</td>
    <td>cadena</td>
    </tr>
</table>

Por estado (por estado)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>enumeración</td>
    </tr>
</table>

Por recurso de destino (byTargetResource)

<table>
<tr>
<th>Nombre</th>
<th>Tipo</th>
</tr>
<tr>
<td>targetResource</td>
<td>cadena</td>
</tr>
</table>

Incluir páginas de aterrizaje avanzadas (con Avanzadas)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>avanzado</td>
    <td>booleano</td>
    </tr>
</table>

Incluir envíos continuos de una lista heterogénea (con Continuo)

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withContinuous</td>
        <td>booleano</td>
        </tr>
    </table>

Presente durante un período determinado (por calendario)

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>startDate</td>
        <td>fecha</td>
        </tr>
        <tr>
        <td>endDate</td>
        <td>fecha</td>
        </tr>
    </table>

Publicado durante un período determinado (por Planning)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>fecha</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>fecha</td>
    </tr>
</table>
