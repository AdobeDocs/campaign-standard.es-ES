---
solution: Campaign Standard
product: campaign
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Modelo de datos
role: Desarrollador
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 13%

---


# Campaña (nms:campaign)

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
                  <td>ID del recurso principal</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>actividades</td>
                  <td>Actividades</td>
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
                  <td>desc</td>
                  <td>Descripción</td>
                  <td>string (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>duration</td>
                  <td>Duración de la campaña</td>
                  <td>number </td>
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
                  <td>vínculo </td>
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
                  <td>modifiedBy (userBase)</td>
                  <td>Modificado por</td>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Unidad organizativa</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programa</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>informe en tiempo real</td>
                  <td>Informes en tiempo real</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Fecha de inicio</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Estado</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Inicio - Inicio - 1</li>
                        <li>Edición - edición - 0</li>
                        <li>Finalizado - Finalizado - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>plantilla (campaña)</td>
                  <td>Plantilla de campaña</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniatura</td>
                  <td>Miniatura</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Campaña</td>
                  <td>string (255)</td>
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
</table>

Por periodo (por periodo)

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

Planificado para el periodo determinado (byPlanning)

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