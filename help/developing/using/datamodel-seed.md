---
title: Miembro semilla de DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 9b522c84-e296-47c7-9588-2e5ed08ab631
TQID: https://experienceleague.adobe.com/lfD2ncth570TSScQZE3UiO3ikqqxpjf4CVd7PvuAFXs
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 182
ht-degree: 46%

---

# Miembro semilla (nms:seedMember)

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
                  <td>país (países)</td>
                  <td>País</td>
                  <td>vínculo </td>
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
                  <td>correo electrónico</td>
                  <td>Correo electrónico</td>
                  <td>cadena (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>emailRendering</td>
                  <td>Representación de correo electrónico</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>fax</td>
                  <td>Fax</td>
                  <td>cadena (32)</td>
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
                  <td>lastModified</td>
                  <td>Última modificación</td>
                  <td>fecha </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>ubicación</td>
                  <td>Ubicación</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>marketingCloudId</td>
                  <td>MARKETING CLOUD ID</td>
                  <td>cadena (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobileApp</td>
                  <td>Aplicación móvil</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Móvil</td>
                  <td>cadena (32)</td>
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
                  <td>Identidad</td>
                  <td>cadena (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_recipient</td>
                  <td>Perfil</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>nms_rtEvent</td>
                  <td>Evento</td>
                  <td>elemento </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Entidades organizativas</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>phone</td>
                  <td>Teléfono</td>
                  <td>cadena (32)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>prueba</td>
                  <td>Prueba</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>pushNotification</td>
                  <td>Notificación push</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>registrationToken</td>
                  <td>Token de registro</td>
                  <td>cadena (256)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sampleData</td>
                  <td>Datos de muestra</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>sms</td>
                  <td>Móvil</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>stateLink (estado)</td>
                  <td>Estado</td>
                  <td>vínculo </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetData</td>
                  <td>Extensión</td>
                  <td>cadena </td>
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
                  <td>Perfil de prueba</td>
                  <td>cadena (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>atrapar</td>
                  <td>Reventar</td>
                  <td>booleano </td>
                  <td> </td>
               </tr>
            </table>

## Filtros

Por tipo de evento (byEventType)

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>eventType</td>
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

Por uso (byUsage)

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>atrapar</td>
        <td>booleano</td>
        </tr>
        <tr>
        <td>emailRendering</td>
        <td>booleano</td>
        </tr>
        <tr>
        <td>prueba</td>
        <td>booleano</td>
        </tr>
    </table>

Perfil de prueba (perfil)

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>seedMember</td>
    <td>vínculo</td>
    </tr>
</table>
