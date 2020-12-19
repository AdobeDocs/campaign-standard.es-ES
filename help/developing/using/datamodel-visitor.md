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
source-wordcount: '144'
ht-degree: 13%

---


# Visitante (nms:visitante)

## Descripción del objeto

<table>
    <tr>
        <th>Name</th>
        <th>Etiqueta</th>
        <th>Tipo (longitud)</th>
        <th>Valores de lista desglosada</th>
    </tr>
    <tr>
        <td>PKey</td>
        <td>ID de recurso principal</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>comment</td>
        <td>Comentario de remitente del reenvío</td>
        <td>string (255)</td>
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
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>envío (envío)</td>
        <td>Entrega</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID del último envío</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Descripción</td>
        <td>string (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Correo electrónico</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>ID externa</td>
        <td>string (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Nombre</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>Dirección URL de reenvío</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Unidad geográfica</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Última modificación</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Apellido</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Modificado por</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Unidad organizativa</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>origen</td>
        <td>Origen</td>
        <td>lista desglosada (byte) </td>
        <td>
            <ul>
            <li>Sin definir - sin definir - 0</li>
            <li>VALOR NO VÁLIDO - __Invalid_value_ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatario (destinatario)</td>
        <td>Perfil identificado</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>destinationId</td>
        <td>ID de perfil</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Correo electrónico del remitente del reenvío</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nombre del remitente del reenvío</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID de remitente del reenvío</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Apellido del remitente del reenvío</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (destinatario)</td>
        <td>Remitente del reenvío</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>título</td>
        <td>Etiqueta</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
</table>

## Filtros

Por apellido, nombre o correo electrónico (porTexto)</p>

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>texto</td>
        <td>string</td>
        </tr>
    </table>