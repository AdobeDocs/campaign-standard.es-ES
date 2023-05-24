---
title: Entrega de modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: aea3e72d-8e89-46c7-a796-bf856414c654
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 29%

---

# Envío (nms:delivery)

## Descripción del objeto

<table>
               <tr>
                  <th>Nombre</th>
                  <th>Etiqueta</th>
                  <th>Tipo (longitud)</th>
                  <th>Valores de enumeración</th>
               </tr>
               <tr>
                  <td>FCP</td>
                  <td>Prueba</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID del recurso principal</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Pruebas A/B</td>
                  <td>elemento </td>
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
                  <td>elemento </td>
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
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>alertMode</td>
                  <td>Tipo de advertencia</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>accesorio</td>
                  <td>Archivos adjuntos</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>personalización de marca (brandingBase)</td>
                  <td>Marca</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
                  <td>Registros de envío</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>builtIn</td>
                  <td>Objeto de aplicación integrado</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>campaign (campaignBase)</td>
                  <td>Campaña</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>cuenta de Adobe Experience Manager</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>comandos</td>
                  <td>Comandos</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>content</td>
                  <td>Contenido</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Fuente de contenido</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaign - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>contextResourceType</td>
                  <td>Tipo de recurso</td>
                  <td>cadena </td>
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
                  <td>Creada por
</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Modo de envío</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Entrega a granel - a granel - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Descripción: descriptivo - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                        <li>Externo - externo - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Enrutamiento</td>
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
                  <td>emailPreview</td>
                  <td>Previsualización de correo electrónico</td>
                  <td>elemento </td>
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
                  <td>Parámetros de ejecución del envío</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Tipo de ejecución</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Único - oneTime - 0</li>
                        <li>Continuo - continuo - 1</li>
                        <li>Message Center - messageCenter - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
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
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>hasAttachments</td>
                  <td>Agregar archivos adjuntos</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>icono</td>
                  <td>Icono</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Correo electrónico transaccional - emailLightning - 60</li>
                        <li>Fax - fax - 4</li>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico recurrente: emailRefresh - 30</li>
                        <li>Correo directo - papel - 3</li>
                        <li>Teléfono - teléfono - 2</li>
                        <li>Otros - otros - 120</li>
                        <li>SMS recurrente: smsRefresh: 31</li>
                        <li>Aplicación móvil: pushNotification - 40</li>
                        <li>SMS transaccional - smsLightning - 61</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
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
                  <td>Principal</td>
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
                  <td>iteraciones</td>
                  <td>Envíos</td>
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
                  <td>Registros</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>kpi</td>
                  <td>Indicadores</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Etiqueta</td>
                  <td>cadena (128)</td>
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
                  <td>mailParameters</td>
                  <td>Parámetros de encabezado de correo electrónico</td>
                  <td>elemento </td>
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
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>maestro (deliveryBase)</td>
                  <td>Instancia maestra</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>masterKpi</td>
                  <td>Indicadores maestros</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - fax - 4</li>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>Teléfono - teléfono - 2</li>
                        <li>Correo directo - papel - 3</li>
                        <li>Aplicación móvil: pushNotification - 40</li>
                        <li>Otros - otros - 120</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>cadena (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>offerManagement</td>
                  <td>Administración de ofertas</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidades organizativas</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principal (deliveryBase)</td>
                  <td>Envío de página principal</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prioridad</td>
                  <td>Prioridad de envío</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programa</td>
                  <td>vincular </td>
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
                  <td>Previsualización de notificación push</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushnotificationParameters</td>
                  <td>Parámetros de PushNotification</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Informes en tiempo real</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versión del medio</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ribbonMessage</td>
                  <td>Mensaje de cinta</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>escenario</td>
                  <td>Parámetros de la plantilla de envíos</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>programación</td>
                  <td>Programación de envío</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsParameters</td>
                  <td>Parámetros de SMS</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>smsPreview</td>
                  <td>Previsualización de SMS</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>Estado</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Comienzo pendiente - startPending - 51</li>
                        <li>Listo para ser entregado - listo - 45</li>
                        <li>Reintento pendiente: retryPending: 61</li>
                        <li>Reintento en curso: retryInProgress: 62</li>
                        <li>Error - error - 87</li>
                        <li>En curso - iniciado - 55</li>
                        <li>Segmentación pendiente: targetPrepPending: 11</li>
                        <li>Personalización pendiente: messagePrepPending: 21</li>
                        <li>En pausa: en pausa: 75</li>
                        <li>Edición - edición - 0</li>
                        <li>Terminado - terminado - 95</li>
                        <li>Recuento en curso - targetSelection - 12</li>
                        <li>Mensaje finalizado - messageReady - 25</li>
                        <li>Error de personalización o recuento - preparationError - 37</li>
                        <li>Detenido - cancelado - 85</li>
                        <li>Personalización en curso: messagePreparation: 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                        <li>Arbitraje en curso - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>objetivos</td>
                  <td>Población de público objetivo de los envíos</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>plantilla (deliveryTemplateSummary)</td>
                  <td>Plantilla de envíos</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura del envío</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Envío</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>seguimiento</td>
                  <td>Parámetros de seguimiento</td>
                  <td>elemento </td>
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
                  <td>triggerMessage</td>
                  <td>Parámetros del mensaje transaccional</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipología (typologyBase)</td>
                  <td>Tipología</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>flujo de trabajo (workflowBase)</td>
                  <td>Flujo de trabajo de direccionamiento</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Estado del flujo de trabajo</td>
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
            </table>

## Filtros

Por tipo de canal (por canal)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>canal</td>
    <td>enumeración</td>
    </tr>
</table>

Por tipo de ejecución (byExecutionType)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>executionType</td>
    <td>enumeración</td>
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
    <tr>
    <td>mc</td>
    <td>cadena</td>
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
    <td>cadena</td>
    </tr>
</table>

Por período (byStartPeriod)

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
    <td>cadena</td>
    </tr>
</table>

Por estado de publicación (byPublicationStatus)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>pStatus</td>
    <td>enumeración</td>
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

Incluir envíos avanzados (con Advanced)

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

Planificado durante el período determinado (por planificación)

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

Presente durante un período determinado (por calendario)

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

Mostrar de forma predeterminada (showOob)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>bobalicón</td>
    <td>booleano</td>
    </tr>
</table>
