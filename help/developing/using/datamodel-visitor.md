---
title: Visitante de DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 40%

---

# Visitante (nms:visitante)

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
        <td>comentario</td>
        <td>Comentario del remitente del reenvío</td>
        <td>cadena (255)</td>
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
        <td>Creada por
</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>delivery (delivery)</td>
        <td>Envío</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID del último envío</td>
        <td>entero </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Descripción</td>
        <td>cadena (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Correo electrónico</td>
        <td>cadena (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>ID externo</td>
        <td>cadena (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Nombre</td>
        <td>cadena (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>URL de reenvío</td>
        <td>cadena (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Unidad geográfica</td>
        <td>vincular </td>
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
        <td>cadena (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Modificado por</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Entidades organizativas</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>origen</td>
        <td>Origen</td>
        <td>enumeración (byte) </td>
        <td>
            <ul>
            <li>Indefinido - indefinido - 0</li>
            <li>VALOR INVÁLIDO - __Valor_no_válido__ - __Valor_no_válido__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinatario (destinatario)</td>
        <td>Perfil identificado</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>ID de perfil</td>
        <td>entero </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Correo electrónico del remitente del reenvío</td>
        <td>cadena (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Nombre del remitente del reenvío</td>
        <td>cadena (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID de referente</td>
        <td>entero </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Apellidos del remitente del reenvío</td>
        <td>cadena (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (destinatario)</td>
        <td>Remitente del reenvío</td>
        <td>vincular </td>
        <td> </td>
    </tr>
    <tr>
        <td>título</td>
        <td>Etiqueta</td>
        <td>cadena (255)</td>
        <td> </td>
    </tr>
</table>

## Filtros

Por apellido, nombre o correo electrónico (por texto)</p>

<table>
        <tr>
        <th>Nombre</th>
        <th>Tipo</th>
        </tr>
        <tr>
        <td>texto</td>
        <td>cadena</td>
        </tr>
    </table>
