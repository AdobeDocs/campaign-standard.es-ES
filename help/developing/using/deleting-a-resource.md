---
title: Eliminación de un recurso
description: Obtenga información sobre cómo eliminar un recurso
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
TQID: https://experienceleague.adobe.com/cDShxyrLISaGidkLNnhtMwZHbo8SlRie6DTV0yVR6IY
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 251
ht-degree: 15%

---

# Eliminación de un recurso{#deleting-a-resource}

Para eliminar un recurso, este debe ser un **[!UICONTROL Draft]**. El recurso se encuentra en estado **[!UICONTROL Draft]** si:

* Acaba de crearse y aún no se ha publicado.
* Si ya se ha publicado, el recurso debe volver a redactarse.

>[!IMPORTANT]
>
>Volver a redactar y eliminar un recurso personalizado son operaciones delicadas que pueden afectar a otros recursos. Estas acciones solo las debe realizar un usuario experto.

Para volver a redactar y eliminar un recurso publicado:

1. Seleccione el recurso que desea volver a redactar.
1. Haga clic en el botón **[!UICONTROL Re-draft]** de la barra de acciones.

   ![](assets/schema_extension_uc26.png)

1. Haga clic **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta acción es definitiva: la tabla o columnas de la base de datos del recurso y sus datos se eliminarán permanentemente cuando se publique la modificación, lo que puede provocar la rotura de vínculos de otros recursos personalizados. Solo la definición del recurso permanecerá disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vuelve a redactar una extensión del recurso predeterminado **Perfiles (perfil)**, también debe volver a redactar cualquier extensión de **perfil de prueba (seedMember)** que haya definido. Para obtener más información sobre cómo ampliar el recurso de perfil, consulte [esta sección](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publicar el recurso. Para ver los pasos más detallados, consulte [Publicación de un recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   A continuación, el recurso pasa al modo **Draft** y su estado de activación es **[!UICONTROL Inactive]**.

1. En el modo **[!UICONTROL List]**, compruebe el recurso que desea eliminar y haga clic en el icono ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

El recurso se eliminará del modelo de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado utilizado en un evento, se cancela la publicación del evento correspondiente de manera automática. Consulte [Cancelar la publicación de un evento transaccional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
