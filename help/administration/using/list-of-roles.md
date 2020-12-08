---
solution: Campaign Standard
product: campaign
title: Lista de funciones
description: Descubra la lista de funciones que puede asignar a los usuarios.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: role,overview;role,main
translation-type: tm+mt
source-git-commit: 2c15273c7614204300f615e9060f29c93a4f8481
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 84%

---


# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign ofrece un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios.

Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Para obtener más información, consulte la [tabla de funciones y permisos](/help/administration/using/assets/acs_rights.pdf) que detalla las funciones disponibles en la interfaz según las autorizaciones seleccionadas.

[![imagen](assets/user_management_3.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf?lang=en)

Las funciones se pueden administrar desde el menú **[!UICONTROL Administration > Users & Security > Roles]**.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**: Derecho de administración genérico.

   >[!NOTE]
   >
   >Si necesita crear activadores, necesitará el **[!UICONTROL Administration]** para poder acceder al menú Desencadenadores. Para obtener más información sobre los activadores, consulte esta [página](../../integrating/using/about-adobe-experience-cloud-triggers.md).

* **[!UICONTROL Datamodel]**: Derecho para ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Generic import]**: Derecho para ejecutar una importación genérica de datos. Para que esto funcione, debe vincular la función **[!UICONTROL Generic import]** a la función **[!UICONTROL Workflow]**.
* **[!UICONTROL Prepare deliveries]**: Derecho a crear, modificar, preparar y eliminar entregas. Los usuarios con esta función pueden preparar la entrega pero no enviarla.
* **[!UICONTROL Start deliveries]**: Derecho para crear, modificar, preparar, enviar y eliminar entregas.
* **[!UICONTROL Workflow]**: Derecho para gestionar la ejecución de flujos de trabajo (inicio, parada, pausa, etc.). Los usuarios con esta función no pueden enviar una entrega ni siquiera en un flujo de trabajo.

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
