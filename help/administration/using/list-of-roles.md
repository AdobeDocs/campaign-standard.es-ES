---
title: Lista de funciones
seo-title: Lista de funciones
description: Lista de funciones
seo-description: Descubra la lista de funciones que puede asignar a los usuarios.
page-status-flag: nunca activado
uuid: 128aaf9b-9b7d-49f3-9e1f-72e79a29baa0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: usuarios y seguridad
discoiquuid: ceaa3c94-9e1a-4271-b443-b00b4068929f
context-tags: función,descripción general;función,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c331937dcfef849798f1a5ed693da5f01759a1b8

---


# Lista de funciones{#list-of-roles}

De forma predeterminada, Adobe Campaign ofrece un conjunto de funciones que le permiten definir autorizaciones unitarias asignadas a usuarios y grupos de usuarios. Combinadas con las unidades organizativas, las funciones proporcionan a los usuarios una vista filtrada de la interfaz y definen su acceso a las diferentes funciones. Para obtener más información sobre esto, consulte la tabla [Funciones y permisos](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

[![imagen](/help/administration/using/assets/user_management_3.png)](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf)

Las funciones se pueden administrar desde el **[!UICONTROL Administration > Users & Security > Roles]** menú.

Los derechos predeterminados son:

* **[!UICONTROL Administration]**:: Derecho de administración genérico.
* **[!UICONTROL Datamodel]**:: Derecho a ejecutar publicaciones y crear recursos personalizados.
* **[!UICONTROL Export]**: derecho para exportar datos.
* **[!UICONTROL Generic import]**:: Derecho a ejecutar una importación genérica de datos. Para que esto funcione, debe vincular la **[!UICONTROL Generic import]** función a la **[!UICONTROL Workflow]** función.
* **[!UICONTROL Prepare deliveries]**:: Derecho a crear, modificar, preparar y eliminar entregas. Los usuarios con esta función pueden preparar la entrega pero no enviarla.
* **[!UICONTROL Start deliveries]**:: Derecho a crear, modificar, preparar, enviar y eliminar entregas.
* **[!UICONTROL Workflow]**:: Derecho a crear, modificar, iniciar y eliminar flujos de trabajo. Los usuarios con esta función no pueden enviar una entrega ni siquiera en un flujo de trabajo.

>[!CAUTION]
>
>Las funciones **[!UICONTROL Deliverability]**, **[!UICONTROL Command execution]**, **[!UICONTROL Export]**, **[!UICONTROL File access]** y **[!UICONTROL Message Center push]** son solo para uso interno de los administradores de Adobe. No deben concederse a un usuario.

**Temas relacionados:**

* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
* [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md)

