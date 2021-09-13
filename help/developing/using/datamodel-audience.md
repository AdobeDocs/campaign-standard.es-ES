---
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 14%

---

# Audiencia (nms:audience)

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
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>aamMappingId</td>
                  <td>ID de asignación de Audience Manager</td>
                  <td>string (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>Fuente de datos AMC</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>Vista previa de la población seleccionada</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>Esquema de datos</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Usar un número de línea como ID</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Recuento</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countDate</td>
                  <td>Fecha de recuento</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>countPreview</td>
                  <td>CountPreview</td>
                  <td>item </td>
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
                  <td>doNotPersist</td>
                  <td>No histórico este trabajo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Errores antes de cancelar</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>expirationDate</td>
                  <td>Caduca el</td>
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
                  <td>hasSchema</td>
                  <td>HasSchema</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isAMC</td>
                  <td>Audiencia de Adobe Marketing Cloud</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Es un recurso externo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>jobLogs</td>
                  <td>Registros</td>
                  <td>colección </td>
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
                  <td>rejectFilename</td>
                  <td>Archivo de rechazo</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Nombre de la audiencia compartida</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>source</td>
                  <td>Fuente</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>ID de origen</td>
                  <td>integer </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Audiencia</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>type</td>
                  <td>Tipo</td>
                  <td>enumeración (cadena) (100)</td>
                  <td>
                     <ul>
                        <li>Consulta - consulta - consulta</li>
                        <li>Lista - lista - lista</li>
                        <li>Archivo - archivo - archivo</li>
                        <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>donde</td>
                  <td>Definición de consulta</td>
                  <td>item </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>flujo de trabajo (flujo de trabajo)</td>
                  <td>Flujo de trabajo</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Por dimensión de filtrado (byFilteringResource)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>string</td>
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

Por tipo (byType)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>type</td>
    <td>enumeración</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>string</td>
    </tr>
</table>
