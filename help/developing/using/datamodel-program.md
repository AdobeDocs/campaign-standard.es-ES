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
source-wordcount: '222'
ht-degree: 13%

---


# Programa (nms:programa)

## Descripción del objeto

<table>
               <tr>
                  <th>Name</th>
                  <th>Etiqueta</th>
                  <th>Tipo (longitud)</th>
                  <th>Valores de lista desglosada</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>ID de recurso principal</td>
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
                  <td>end</td>
                  <td>Fecha final</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidad geográfica</td>
                  <td>link </td>
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
                  <td>parent (programBase)</td>
                  <td>Programa principal</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Informes en tiempo real</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>inicio</td>
                  <td>Fecha de inicio</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>status</td>
                  <td>Estado</td>
                  <td>lista desglosada (byte) </td>
                  <td>
                     <ul>
                        <li>Comenzado - Comenzado - 1</li>
                        <li>Edición - edición - 0</li>
                        <li>Finalizado - terminado - 2</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>plantilla (programa)</td>
                  <td>Plantilla de programa</td>
                  <td>link </td>
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
                  <td>Programa</td>
                  <td>string (255)</td>
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

Por período (por período)

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
    <td>timePeriod</td>
    <td>string</td>
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

Incluir subprogramas (conParent)

<table>
        <tr>
        <th>Name</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>booleano</td>
        </tr>
    </table>

Únicamente los padres con derecho a ello (padres con derecho a ello)

<table>
    <tr>
    <th>Name</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>programa</td>
    <td>link</td>
    </tr>
</table>

Planificado para el período determinado (porPlanning)

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