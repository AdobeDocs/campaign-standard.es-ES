---
title: Evento de baja de DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 508361d1-6a0b-4476-a058-4162fb3e8d5e
TQID: 'https://experienceleague.adobe.com/VuhZ3s5VTH3MFPuqzr18GBMmyaPxD2uQEdJAsMIOlf0'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '54'
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
