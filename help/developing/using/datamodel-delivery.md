---
title: Entrega del modelo de datos
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
ht-degree: 15%

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
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>abTesting</td>
                  <td>Pruebas A/B</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>avanzado</td>
                  <td>Entrega avanzada</td>
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
                  <td>archivo</td>
                  <td>Archivos adjuntos</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>promoción de la marca (brandingBase)</td>
                  <td>Marca</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>broadLogs</td>
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
                  <td>campaign (campaignBase)</td>
                  <td>Campaña</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cmsAccount (extAccountAEMBase)</td>
                  <td>Cuenta de Adobe Experience Manager</td>
                  <td>vínculo </td>
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
                  <td>Contenido</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>contentSource</td>
                  <td>Fuente de contenido</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Adobe Experience Manager - aem - 1</li>
                        <li>Adobe Campaign - campaña - 0</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>deliveryMode</td>
                  <td>Modo de envío</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Entrega masiva: masiva - 1</li>
                        <li>Mid-sourcing - midSourcing - 4</li>
                        <li>Descripción - descriptivo - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Externo - externo - 0</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>deliveryProvider (extAccountBase)</td>
                  <td>Enrutamiento</td>
                  <td>vínculo </td>
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
                  <td>Vista previa del correo electrónico</td>
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
                  <td>execution</td>
                  <td>Parámetros de ejecución de entrega</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>executionType</td>
                  <td>Tipo de ejecución</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Único - una vez - 0</li>
                        <li>Continuo - continuo - 1</li>
                        <li>Centro de mensajes - messageCenter - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>vínculo </td>
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
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Correo electrónico transaccional - emailLightning - 60</li>
                        <li>Fax - 4</li>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>Correo electrónico recurrente - emailRefresh - 30</li>
                        <li>Correo postal: papel - 3</li>
                        <li>Teléfono - teléfono - 2</li>
                        <li>Los demás - otros - 120</li>
                        <li>SMS recurrente - smsRefresh - 31</li>
                        <li>Aplicación móvil - pushNotification - 40</li>
                        <li>SMS transaccional - smsLightning - 61</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
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
                  <td>Registros</td>
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
                  <td>enumeración (cadena) (255)</td>
                  <td>
                     <ul>
                        <li>In progress - started - started</li>
                        <li>Edición: edición</li>
                        <li>Finalizado: terminado</li>
                        <li>Advertencia - advertencia - advertencia</li>
                        <li>Error: error</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
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
                  <td>mapping (deliveryMapping)</td>
                  <td>Asignación de destino</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>master (deliveryBase)</td>
                  <td>Instancia maestra</td>
                  <td>vínculo </td>
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
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Fax - 4</li>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>Teléfono - teléfono - 2</li>
                        <li>Correo postal: papel - 3</li>
                        <li>Aplicación móvil - pushNotification - 40</li>
                        <li>Los demás - otros - 120</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>modificado por</td>
                  <td>vínculo </td>
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
                  <td>Entidades organizativas</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>parent (deliveryBase)</td>
                  <td>Entrega principal</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>priority</td>
                  <td>Prioridad de entrega</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Alto - alto - 20</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Normal - normal - 10</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programa</td>
                  <td>vínculo </td>
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
                  <td>Vista previa de notificaciones push</td>
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
                  <td>informe en tiempo real</td>
                  <td>Informes en tiempo real</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>resourceVersion</td>
                  <td>Versión del recurso</td>
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
                  <td>Parámetros de plantilla de entrega</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>programación</td>
                  <td>Programación de entregas</td>
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
                  <td>Vista previa del SMS</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>state</td>
                  <td>Estado</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Inicio pendiente - startPending - 51</li>
                        <li>Listo para entregar - listo - 45</li>
                        <li>Reintento pendiente - retryPending - 61</li>
                        <li>Reintento en curso - retryInProgress - 62</li>
                        <li>Fallido - error - 87</li>
                        <li>En curso - Comenzado - 55</li>
                        <li>Segmentación pendiente - targetPrepPending - 11</li>
                        <li>Personalización pendiente - messagePrepPending - 21</li>
                        <li>En pausa - en pausa - 75</li>
                        <li>Edición - edición - 0</li>
                        <li>Finalizado - terminado - 95</li>
                        <li>Recuento en curso - targetSelection - 12</li>
                        <li>Mensaje finalizado - messageReady - 25</li>
                        <li>Error de personalización o recuento - error de preparación - 37</li>
                        <li>Detenido - cancelado - 85</li>
                        <li>Personalización en curso - messagePreparation - 22</li>
                        <li>Target ready - targetReady - 15</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                        <li>Arbitraje en curso - targetArbitration - 13</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>targets</td>
                  <td>Público destinatario de la entrega</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (deliveryTemplateSummary)</td>
                  <td>Plantilla de envío</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura de entrega</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Entrega</td>
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
                  <td>triggerMessage</td>
                  <td>Parámetros del mensaje transaccional</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipología (typologyBase)</td>
                  <td>Tipología</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflowBase)</td>
                  <td>Flujo de trabajo de direccionamiento</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflowStatus</td>
                  <td>Estado del flujo de trabajo</td>
                  <td>enumeración (cadena) (255)</td>
                  <td>
                     <ul>
                        <li>In progress - started - started</li>
                        <li>Edición: edición</li>
                        <li>Finalizado: terminado</li>
                        <li>Advertencia - advertencia - advertencia</li>
                        <li>Error: error</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
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

Por nombre o etiqueta (byText)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>text</td>
    <td>string</td>
    </tr>
    <tr>
    <td>mc</td>
    <td>string</td>
    </tr>
</table>

Por periodo (por periodo)

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

Por periodo (byStartPeriod)

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

Por estado (byState)

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
    <td>secundario</td>
    <td>booleano</td>
    </tr>
</table>

Incluir envíos avanzados (conAdvanced)

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

Incluir envíos continuos de una lista heterogénea (con Continuous)

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

Planificado durante el periodo determinado (byPlanning)

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

Presente durante un periodo determinado (por calendario)

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

Mostrar predeterminado (showOob)

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
