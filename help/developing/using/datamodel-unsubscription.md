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
source-wordcount: '53'
ht-degree: 16%

---


# Evento baja (nms:rtEvent)

## Descripción del objeto

<table>
               <tr>
                  <th>Name</th>
                  <th>Sólo lectura</th>
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
                  <td>lista desglosada</td>
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
    <th>Name</th>
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
        <th>Name</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>status</td>
        <td>lista desglosada</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>