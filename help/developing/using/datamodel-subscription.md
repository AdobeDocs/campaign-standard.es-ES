---
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

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
        <td>ID de recurso principal</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>ctx</td>
        <td>Contexto del evento</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Correo electrónico</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>Formato de correo electrónico</td>
        <td>enumeración (byte) </td>
        <td>
            <ul>
            <li>Texto - texto - 1</li>
            <li>HTML - html - 2</li>
            <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            <li>Desconocido - desconocido - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>ID del evento archivado</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Número de móvil</td>
        <td>string (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filtros

Por correo electrónico (por correo electrónico)

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

Por estado o tipo (byStatusOrType)

<table>
        <tr>
        <th>Name</th>
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