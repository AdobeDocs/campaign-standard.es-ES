---
title: Evento de baja de DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
TQID: https://experienceleague.adobe.com/VuhZ3s5VTH3MFPuqzr18GBMmyaPxD2uQEdJAsMIOlf0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 54
ht-degree: 59%

---

# Evento de baja (nms:rtEvent)

## Descripción del objeto

<table>
               <tr>
                  <th>Name</th>
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
                  <td>correo electrónico</td>
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

por correo electrónico

<table>
    <tr>
    <th>Nombre</th>
    <th>Tipo</th>
    </tr>
    <tr>
    <td>correo electrónico</td>
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
