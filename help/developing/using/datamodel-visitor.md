---
solution: Campaign Standard
product: campaign
title: Modelo de datos
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 13%

---


# Visitante (nms:visitor)

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
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>comment</td>
        <td>Comentario del referente</td>
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
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>entrega (entrega)</td>
        <td>Envío</td>
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID de la última entrega</td>
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
        <td>ID externo</td>
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
        <td>vínculo </td>
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
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Unidad organizativa</td>
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>origin</td>
        <td>Origen</td>
        <td>enumeration (byte) </td>
        <td>
            <ul>
            <li>Sin definir - Sin definir - 0</li>
            <li>VALOR NO VÁLIDO - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatario (destinatario)</td>
        <td>Perfil identificado</td>
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>ID de perfil</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Correo electrónico del referente</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nombre del referente</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID de referente</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Apellido del referente</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (destinatario)</td>
        <td>Referente</td>
        <td>vínculo </td>
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

Por apellido, nombre o correo electrónico (byText)</p>

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>text</td>
        <td>string</td>
        </tr>
    </table>