---
title: Programa DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: b05dc67a-6447-4d22-99f2-8a14a0ee46d2
TQID: https://experienceleague.adobe.com/zo3wFxqwI6LIHn4Uolv9oipkW17maikqcO4zExmYQxM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 38%

---

# Programa (nms:program)

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
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>actividades</td>
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
                  <td>fecha </td>
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
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>Identidad</td>
                  <td>cadena (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidades organizativas</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>principal (programBase)</td>
                  <td>Programa principal</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>realtimeReport</td>
                  <td>Informes en tiempo real</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>iniciar</td>
                  <td>Fecha de inicio</td>
                  <td>fecha </td>
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
                  <td>plantilla (programa)</td>
                  <td>Plantilla de programa</td>
                  <td>vínculo </td>
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
                  <td>Programa</td>
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
    <td>estado</td>
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
    <td>fecha</td>
    </tr>
    <tr>
    <td>timePeriod</td>
    <td>cadena</td>
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

Incluir subprogramas (withParent)

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>withParent</td>
        <td>booleano</td>
        </tr>
    </table>

Solo los padres elegibles (EligibleParents)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>programa</td>
    <td>vínculo</td>
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
    <td>fecha</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>fecha</td>
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
