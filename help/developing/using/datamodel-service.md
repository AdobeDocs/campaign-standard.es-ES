---
title: Servicio DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 37%

---

# Servicio (nms:service)

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
                  <td>builtIn</td>
                  <td>Objeto de aplicación integrado</td>
                  <td>booleano </td>
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
                  <td>cusPrice</td>
                  <td>Precio</td>
                  <td>entero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descripción</td>
                  <td>cadena (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fin</td>
                  <td>Fecha de finalización</td>
                  <td>fecha </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidad geográfica</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>historia</td>
                  <td>Historial de suscripciones</td>
                  <td>colección </td>
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
                  <td>limitedDuration</td>
                  <td>Duración limitada</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Fecha</td>
                  <td>fecha (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Móvil (SMS) - sms - 1</li>
                        <li>Correo electrónico - correo electrónico - 0</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modo</td>
                  <td>Modo</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Viral - viral - 1</li>
                        <li>Newsletter - Newsletter - 0</li>
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
                  <td>publicLabel</td>
                  <td>Etiqueta de servicio</td>
                  <td>cadena (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Fecha de inicio</td>
                  <td>fecha </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Página de aterrizaje de suscripción</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmación de suscripción</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>suscripciones</td>
                  <td>Suscripciones</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>Dimensión de segmentación</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>plantilla (servicio)</td>
                  <td>Plantilla de servicio</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Servicio</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Página de aterrizaje de baja</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmación de baja</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>Duración de validez</td>
                  <td>número </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Disponible durante el período determinado (por planificación)

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
