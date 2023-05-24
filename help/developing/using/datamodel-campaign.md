---
title: Campaña del modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a63fe730-a6b2-4ae0-93da-9f8ee7824c9f
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 35%

---

# Campaign (nms:campaign)

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
                  <td>Actividades</td>
                  <td>Actividades</td>
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
                  <td>desc</td>
                  <td>Descripción</td>
                  <td>cadena (512)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>duration</td>
                  <td>Duración de la campaña</td>
                  <td>número </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fin</td>
                  <td>Fecha de finalización</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Unidad geográfica</td>
                  <td>vincular </td>
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
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidades organizativas</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>program (programBase)</td>
                  <td>Programa</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Informes en tiempo real</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Fecha de inicio</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>estado</td>
                  <td>Estado</td>
                  <td>enumeración (byte) </td>
                  <td>
                     <ul>
                        <li>Iniciado - iniciado - 1</li>
                        <li>Edición - edición - 0</li>
                        <li>Terminado - terminado - 2</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>plantilla (campaña)</td>
                  <td>Plantilla de campaña</td>
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
                  <td>Campaña</td>
                  <td>cadena (255)</td>
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

Por período (por período)

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

Planificado para el período determinado (por planificación)

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
