---
title: Evento de suscripción de modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: cf0fac4e-59fd-4d6e-a411-41361f45938d
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 30%

---

# Evento de suscripción (nms:rtEvent)

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
