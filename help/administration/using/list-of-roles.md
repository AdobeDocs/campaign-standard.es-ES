---
title: Lista de funciones
description: Descubra la lista de funciones que puede asignar a los usuarios.
page-status-flag: never-activated
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: role,overview;role,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 395791e69d0c4c8a888829539338e338387294de
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 7%

---


# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign oferta un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios.

Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Para obtener más información sobre esto, consulte la tabla [](/help/administration/using/assets/acs_rights.pdf)Funciones y permisos, que detalla las funciones disponibles en la interfaz en función de las autorizaciones seleccionadas.

[![imagen](assets/user_management_3.png)](https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/users-and-security/assets/acs_rights.pdf)

Las funciones se pueden administrar desde el **[!UICONTROL Administration > Users & Security > Roles]** menú.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**:: Derechos de administración genéricos.
* **[!UICONTROL Datamodel]**:: Derecho a ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Generic import]**:: Derecho a ejecutar una importación genérica de datos. Para que esto funcione, debe vincular la **[!UICONTROL Generic import]** función a la **[!UICONTROL Workflow]** función.
* **[!UICONTROL Prepare deliveries]**:: Derecho a crear, modificar, preparar y eliminar envíos. Los usuarios con esta función pueden preparar el envío pero no enviarlo.
* **[!UICONTROL Start deliveries]**:: Derecho a crear, modificar, preparar, enviar y eliminar envíos.
* **[!UICONTROL Workflow]**:: Derecho a gestionar la ejecución de flujos de trabajo (inicio, parada, pausa, etc.). Los usuarios con esta función no pueden enviar un envío ni siquiera en un flujo de trabajo.

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
