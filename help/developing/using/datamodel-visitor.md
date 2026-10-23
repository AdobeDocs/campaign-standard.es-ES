---
title: Visitante de DataModel
description: Obtenga información sobre el modelo de datos
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
TQID: 'https://experienceleague.adobe.com/jzmKAer7SITNpxJRT1CsPf-LWW-bglgNhDl5NKP6mzU'
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
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 42%
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
        <td>fecha </td>
        <td> </td>
    </tr>
    <tr>
        <td>createdBy (userBase)</td>
        <td>Creado por</td>
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>delivery (delivery)</td>
        <td>Envío</td>
        <td>vínculo </td>
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
        <td>correo electrónico</td>
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
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Última modificación</td>
        <td>fecha </td>
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
        <td>vínculo </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Entidades organizativas</td>
        <td>vínculo </td>
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
        <td>vínculo </td>
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
        <td>vínculo </td>
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
