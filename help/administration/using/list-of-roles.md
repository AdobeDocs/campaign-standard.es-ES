---
title: Lista de funciones
description: Descubra la lista de funciones que puede asignar a los usuarios
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 00714c80-bdaf-4241-bf2f-51498ca1dbef
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 77%

---

# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign ofrece un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios.

Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Las funciones se pueden administrar desde el menú **[!UICONTROL Administration > Users & Security > Roles]**.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**: Derecho de administración genérico.

   >[!NOTE]
   >
   >Si trabaja con Déclencheur Experience Cloud, necesita el **[!UICONTROL Administration]** derecho para acceder al menú Déclencheur del Experience Cloud. Para obtener más información sobre los Déclencheur de Experience Cloud, consulte esta sección [página](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Derecho para ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Generic import]**: Derecho para ejecutar una importación genérica de datos. Para que esto funcione, debe vincular la variable **[!UICONTROL Generic import]** función a la **[!UICONTROL Workflow]** función.
* **[!UICONTROL Prepare deliveries]**: Derecho a crear, modificar, preparar y eliminar entregas. Los usuarios con esta función pueden preparar la entrega pero no enviarla.
* **[!UICONTROL Start deliveries]**: Derecho para crear, modificar, preparar, enviar y eliminar entregas.
* **[!UICONTROL Workflow]**: Derecho para gestionar la ejecución de flujos de trabajo (inicio, parada, pausa, etc.). Los usuarios con esta función no pueden enviar una entrega ni siquiera en un flujo de trabajo.

Para obtener más información, consulte la [tabla de funciones y permisos](/help/administration/using/assets/acs_rights.pdf) que detalla las funciones disponibles en la interfaz según las autorizaciones seleccionadas.

[![imagen](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
