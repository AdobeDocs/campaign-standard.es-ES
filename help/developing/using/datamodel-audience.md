---
title: Audiencia de modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 53da6c4e-d4fb-4677-acff-744e3eb10960
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 40%

---

# Audience (nms:audience)

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
                  <td>aamMappingId</td>
                  <td>ID de asignación de Audience Manager</td>
                  <td>cadena (100)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>amcDataSource (amcDataSourceBase)</td>
                  <td>Fuente de datos AMC</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceData</td>
                  <td>Previsualizar la población seleccionada</td>
                  <td>colección </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceDataSchema</td>
                  <td>Esquema de datos</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>audienceMetadata</td>
                  <td>AudienceMetadata</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>collectLineNumber</td>
                  <td>Usar un número de línea como identificador</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>count</td>
                  <td>Recuento</td>
                  <td>entero </td>
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
                  <td>elemento </td>
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
                  <td>doNotPersist</td>
                  <td>No historiar este trabajo</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>errorLimit</td>
                  <td>Errores antes de anular</td>
                  <td>entero </td>
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
                  <td>vincular </td>
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
                  <td>rejectFilename</td>
                  <td>Archivo de rechazo</td>
                  <td>cadena </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sharedAudience</td>
                  <td>Nombre de la audiencia compartida</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>origen</td>
                  <td>Fuente</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sourceId</td>
                  <td>ID de origen</td>
                  <td>entero </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>título</td>
                  <td>Audiencia</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>tipo</td>
                  <td>Tipo</td>
                  <td>enumeración (cadena) (100)</td>
                  <td>
                     <ul>
                        <li>Query - query - query</li>
                        <li>Lista - lista - lista</li>
                        <li>Archivo - archivo - archivo</li>
                        <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>donde</td>
                  <td>Definición de consulta</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>workflow (workflow)</td>
                  <td>Flujo de trabajo</td>
                  <td>vincular </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Mediante dimensión de filtrado (byFilteringResource)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>filteringResource</td>
    <td>cadena</td>
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

Por tipo (por tipo)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>tipo</td>
    <td>enumeración</td>
    </tr>
    <tr>
    <td>isAMC</td>
    <td>cadena</td>
    </tr>
</table>
