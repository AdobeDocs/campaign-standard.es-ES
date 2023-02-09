---
title: Evento de cancelación de suscripción del modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 60%

---

# Evento de cancelación de suscripción (nms:rtEvent)

## Descripción del objeto

<table>
               <tr>
                  <th>Nombre</th>
                  <th>Solo lectura</th>
                  <th>Tipo</th>
                  <th>Obligatorio</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Falso</td>
                  <td>cadena</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Falso</td>
                  <td>elemento</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Falso</td>
                  <td>cadena</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Falso</td>
                  <td>enumeración</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Falso</td>
                  <td>cadena</td>
                  <td>Falso</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>Verdadero</td>
                  <td>cadena</td>
                  <td>Falso</td>
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
    <td>cadena</td>
    </tr>
</table>

byStatusOrType

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>estado</td>
        <td>enumeración</td>
        </tr>
        <tr>
        <td>tipo</td>
        <td>cadena</td>
        </tr>
    </table>
