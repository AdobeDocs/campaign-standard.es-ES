---
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# Servicio (nms:service)

## Descripción del objeto

<table>
               <tr>
                  <th>Name</th>
                  <th>Etiqueta</th>
                  <th>Tipo (longitud)</th>
                  <th>Valores de enumeración</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID de recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>buildIn</td>
                  <td>Objeto de aplicación integrado</td>
                  <td>booleano </td>
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
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>cusPrice</td>
                  <td>Precio</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>desc</td>
                  <td>Descripción</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>end</td>
                  <td>Fecha final</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidad geográfica</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>history</td>
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
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
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
                        <li>Newsletter - newsletter - 0</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
                  <td> link </td>
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
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Etiqueta de servicio</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Fecha de inicio</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Página de aterrizaje de suscripción</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmación de suscripción</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>string </td>
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
                  <td>Dimensiones de objetivo</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>plantilla (servicio)</td>
                  <td>Plantilla de servicio</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>thumbnail</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Servicio</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Cancelar la suscripción de la página de aterrizaje</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Confirmación de cancelación de suscripción</td>
                  <td> link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validDuration</td>
                  <td>Duración de validez</td>
                  <td>number </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Disponible durante el período determinado (porPlanning)

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

Por tipo de canal (byChannel)

<table>
<tr>
<th>Name</th>
<th>Tipo</th>
</tr>
<tr>
<td>channel</td>
<td>enumeración</td>
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