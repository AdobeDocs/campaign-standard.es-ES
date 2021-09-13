---
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 16%

---

# Evento de cancelación de suscripción (nms:rtEvent)

## Descripción del objeto

<table>
               <tr>
                  <th>Nombre</th>
                  <th>Solo lectura</th>
                  <th>Tipo</th>
                  <th>Requerido</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>False</td>
                  <td>string</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>False</td>
                  <td>item</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>False</td>
                  <td>string</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>False</td>
                  <td>enumeración</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>False</td>
                  <td>string</td>
                  <td>False</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>True</td>
                  <td>string</td>
                  <td>False</td>
               </tr>
            </table>

## Filtros

byEmail

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>email</td>
    <td>string</td>
    </tr>
</table>

byStatusOrType

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>status</td>
        <td>enumeración</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>
