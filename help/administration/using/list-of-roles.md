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
source-git-commit: 88d0f67683c5209ccf25d1ceae1ab23b3ac14e06

---


# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign ofrece un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios.

Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones.

Para obtener más información sobre esto, consulte la tabla [](/help/administration/using/assets/acs_rights.pdf)Funciones y permisos, que detalla las funciones disponibles en la interfaz en función de las autorizaciones seleccionadas.

![](assets/user_management_3.png)

Las funciones se pueden administrar desde el **[!UICONTROL Administration > Users & Security > Roles]** menú.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**:: Derechos de administración genéricos.
* **[!UICONTROL Datamodel]**:: Derecho a ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Export]**: derecho para exportar datos.
* **[!UICONTROL Generic import]**:: Derecho a ejecutar una importación genérica de datos. Para que esto funcione, debe vincular la **[!UICONTROL Generic import]** función a la **[!UICONTROL Workflow]** función.
* **[!UICONTROL Prepare deliveries]**:: Derecho a crear, modificar, preparar y eliminar entregas. Los usuarios con esta función pueden preparar la entrega pero no enviarla.
* **[!UICONTROL Start deliveries]**:: Derecho a crear, modificar, preparar, enviar y eliminar entregas.
* **[!UICONTROL Workflow]**:: Derecho a administrar la ejecución de flujos de trabajo (inicio, parada, pausa, etc.). Los usuarios con esta función no pueden enviar una entrega ni siquiera en un flujo de trabajo.

>[!IMPORTANT]
>
>Las funciones **[!UICONTROL Deliverability]**, **[!UICONTROL Command execution]**, **[!UICONTROL Export]**, **[!UICONTROL File access]** y **[!UICONTROL Message Center push]** son solo para uso interno de los administradores de Adobe. No deben concederse a un usuario.

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)
