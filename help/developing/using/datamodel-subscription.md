---
title: Evento de suscripción de modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
TQID: https://experienceleague.adobe.com/XssYu0sntbeCRq1uNe6MhztLtISXoJiOefIOnjqIaoQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 81
ht-degree: 33%

---

# Evento de suscripción (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contexto del evento</td>
        <td>elemento </td>
        <td> </td>
    </tr>
    <tr>
        <td>correo electrónico</td>
        <td>Correo electrónico</td>
        <td>cadena (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>Formato del correo electrónico</td>
        <td>enumeración (byte) </td>
        <td>
            <ul>
            <li>Texto - texto - 1</li>
            <li>HTML - html - 2</li>
            <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
            <li>Desconocido - desconocido - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>ID de evento archivado</td>
        <td>entero </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Número de móvil</td>
        <td>cadena (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>cadena </td>
        <td> </td>
    </tr>
</table>

## Filtros

Por correo electrónico (por correo electrónico)

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

Por estado o tipo (byStatusOrType)

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
