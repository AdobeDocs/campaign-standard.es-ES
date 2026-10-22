---
title: Lista de funciones
description: Descubra la lista de funciones que puede asignar a los usuarios
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
TQID: 'https://experienceleague.adobe.com/HvLFiLS2GV0iJODsGL3AMMWd-lXbvDXYyLSJ8Mj20-w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: e3988c18-3cfa-4f16-b812-ac2d2b1056fa
    internal-label: Permissions
  - id: efa38731-2723-4334-8d8b-a778af834835
    internal-label: Access management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 75%
---
# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign ofrece un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios.

Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Las funciones se pueden administrar desde el menú **[!UICONTROL Administration > Users & Security > Roles]**.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**: Derecho de administración genérico.

  >[!NOTE]
  >
  >Si trabaja con Déclencheur de Experience Cloud, necesita el derecho de **[!UICONTROL Administration]** para poder acceder al menú Déclencheur de Experience Cloud. Para obtener más información sobre los Déclencheur de Experience Cloud, consulte esta [página](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Derecho para ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Generic import]**: Derecho para ejecutar una importación genérica de datos. Para que esto funcione, debe vincular el rol **[!UICONTROL Generic import]** al rol **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: Derecho a crear, modificar, preparar y eliminar entregas. Los usuarios con esta función pueden preparar la entrega pero no enviarla.
* **[!UICONTROL Start deliveries]**: Derecho para crear, modificar, preparar, enviar y eliminar entregas.
* **[!UICONTROL Workflow]**: Derecho para gestionar la ejecución de flujos de trabajo (inicio, parada, pausa, etc.). Los usuarios con esta función no pueden enviar una entrega ni siquiera en un flujo de trabajo.

Para obtener más información, consulte la [tabla de funciones y permisos](/help/administration/using/assets/acs_rights.pdf) que detalla las funciones disponibles en la interfaz según las autorizaciones seleccionadas.

[![imagen](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
