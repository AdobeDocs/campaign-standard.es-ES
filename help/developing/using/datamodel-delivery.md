---
solution: Campaign Standard
product: campaign
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 10%

---


# Envío (nms:envío)

## Descripción del objeto

<table>
               <tr>
                  <th>Name</th>
                  <th>Etiqueta</th>
                  <th>Tipo (longitud)</th>
                  <th>Valores de lista desglosada</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Prueba</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID de recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Prueba A/B</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avanzado</td>
                  <td>Envío avanzado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>advancedParameters</td>
                  <td>Parámetros avanzados</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aemContents</td>
                  <td>Contenido de Adobe Experience Manager</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMessage</td>
                  <td>Mensaje de advertencia</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo de advertencia</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>archivo adjunto</td>
                  <td>Archivos adjuntos</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marca (brandingBase)</td>
                  <td>Marca</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>wideLogs</td>
                  <td>Registros de entregas</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>Objeto de aplicación integrado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaña (campaignBase)</td>
                  <td>Campaña</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Cuenta de Adobe Experience Manager</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandos</td>
                  <td>Comandos</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>Content</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Fuente de contenido</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaña - 0</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo de recurso</td>
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
                  <td>deliveryMode</td>
                  <td>Modo envío</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Envío masivo - masivo - 1</li>
                        <li>Intermediaria - midSourcing - 4</li>
                        <li>Descripción - descriptiva - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                        <li>Externo - externo - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Enrutamiento</td>
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
                  <td>emailPreview</td>
                  <td>Previsualización de correo electrónico</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>excludeLogs</td>
                  <td>Registros de exclusión</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>exclusiones</td>
                  <td>Causas de exclusión</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ejecución</td>
                  <td>Parámetros de ejecución de envío</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executeType</td>
                  <td>Tipo de ejecución</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Único - una vez - 0</li>
                        <li>Continuo - continuo - 1</li>
                        <li>Centro de mensajes - messageCenter - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>forecastLogs</td>
                  <td>ForecastLog</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidad geográfica</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Añadir archivos adjuntos</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icono</td>
                  <td>Icono</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Correo electrónico transaccional - emailLightning - 60</li>
                        <li>Fax: 4</li>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico recurrente - emailRefresh - 30</li>
                        <li>Correo postal - papel - 3</li>
                        <li>Teléfono - Teléfono - 2</li>
                        <li>Otros - otros - 120</li>
                        <li>SMS recurrentes - smsRefresh - 31</li>
                        <li>Aplicación móvil - pushNotification - 40</li>
                        <li>SMS transaccional - smsLightning - 61</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
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
                  <td>isMaster</td>
                  <td>Maestro</td>
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
                  <td>iteraciones</td>
                  <td>Entregas</td>
                  <td>colección </td>
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
                  <td>kpis</td>
                  <td>Indicadores</td>
                  <td>item </td>
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
                  <td>mailParameters</td>
                  <td>Parámetros de encabezado de correo electrónico</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Fecha</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>asignación (deliveryMapping)</td>
                  <td>Asignación de destino</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Instancia maestra</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpis</td>
                  <td>Indicadores maestros</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Fax: 4</li>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>Teléfono - Teléfono - 2</li>
                        <li>Correo postal - papel - 3</li>
                        <li>Aplicación móvil - pushNotification - 40</li>
                        <li>Otros - otros - 120</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
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
                  <td>offerManagement</td>
                  <td>Administración de ofertas</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unidad organizativa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Envío principal</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prioridad</td>
                  <td>Prioridad de envío</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Alta - alta - 20</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>programa (programBase)</td>
                  <td>Programa</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pruebas</td>
                  <td>Pruebas</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotificationPreview</td>
                  <td>Previsualización de notificaciones push</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parámetros de PushNotification</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Informes en tiempo real</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versión de recurso</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Mensaje de cinta</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>escenario</td>
                  <td>Parámetros de Plantilla de envíos</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>programar</td>
                  <td>Programación de envíos</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parámetros de SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>PREVISUALIZACIÓN SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>Estado</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Inicio pendiente - startPendiente - 51</li>
                        <li>Listo para ser entregado - listo - 45</li>
                        <li>Reintentar pendiente - reintentar pendiente - 61</li>
                        <li>Reintentar en curso - reintentarEnCurso - 62</li>
                        <li>Fallido - error - 87</li>
                        <li>En curso - iniciado - 55</li>
                        <li>Objetivo pendiente - targetPrepPendiente - 11</li>
                        <li>Personalización pendiente - messagePrepPendiente - 21</li>
                        <li>En pausa - en pausa - 75</li>
                        <li>Edición - edición - 0</li>
                        <li>Finalizado - terminado - 95</li>
                        <li>Recuento en curso - targetSelection - 12</li>
                        <li>Mensaje finalizado - messageReady - 25</li>
                        <li>Error de personalización o recuento - error de preparación - 37</li>
                        <li>Detenido - cancelado - 85</li>
                        <li>Personalización en curso - messagePreparation - 22</li>
                        <li>Destinatario listo - targetReady - 15</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                        <li>Arbitraje en curso - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>destinatarios</td>
                  <td>Población de destinatario de envío</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Plantilla de envíos</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>Miniatura de envío</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Envío</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>seguimiento</td>
                  <td>Parámetros de seguimiento</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingLogs</td>
                  <td>Registros de seguimiento</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>trackingUrls</td>
                  <td>Direcciones URL rastreadas</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desencadenadorMensaje</td>
                  <td>Parámetros del mensaje transaccional</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipología (typologyBase)</td>
                  <td>Tipología</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Flujo de trabajo de objetivos</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Estado del flujo de trabajo</td>
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
            </table>

## Filtros

Por tipo de canal (byChannel)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>canal</td>
    <td>lista desglosada</td>
    </tr>
</table>

Por tipo de ejecución (byExecutionType)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>executeType</td>
    <td>lista desglosada</td>
    </tr>
</table>

Por estado lógico (byLogicalStatus)

<table>
    <tr>
    <th>Nombre</th>
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
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>texto</td>
    <td>string</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Por período (por período)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Por punto (byStartPeriod)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>string</td>
    </tr>
</table>

Por estado de publicación (porPublicationStatus)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>lista desglosada</td>
    </tr>
</table>

Por estado (byState)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>state</td>
    <td>lista desglosada</td>
    </tr>
</table>

Mensajes de seguimiento (showFollowup)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>seguimiento</td>
    <td>booleano</td>
    </tr>
</table>

Incluir envíos avanzados (conAvanzado)

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

Incluir envíos continuos de una lista heterogénea (conContinuo)

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

Incluir pruebas (con FCP)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>withFCP</td>
    <td>booleano</td>
    </tr>
</table>

Planificado durante el período determinado (porPlanning)

<table>
    <tr>
    <th>Nombre</th>
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

Presente durante un período determinado (porCalendario)

<table>
    <tr>
    <th>Nombre</th>
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

Mostrar lista para usar (showOob)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>obturador</td>
    <td>booleano</td>
    </tr>
</table>