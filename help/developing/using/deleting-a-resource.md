---
title: Eliminación de un recurso
description: 'Obtenga información sobre cómo eliminar un recurso '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
feature: Data Model
role: Developer
level: Experienced
exl-id: 4ddfdbcc-a154-4c10-a97e-73ad888d1f1f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 14%

---

# Eliminación de un recurso{#deleting-a-resource}

Para eliminar un recurso, el recurso en cuestión debe ser **[!UICONTROL Draft]**. El recurso está en estado **[!UICONTROL Draft]** si:

* Acaba de crearse y aún no se ha publicado.
* Si ya se ha publicado, el recurso debe volver a redactarse.

>[!IMPORTANT]
>
>La nueva redacción y la eliminación de un recurso personalizado son operaciones delicadas que pueden afectar a otros recursos. Estas acciones deben realizarlas únicamente usuarios expertos.

Para volver a redactar y eliminar un recurso publicado:

1. Seleccione el recurso que desea volver a redactar.
1. Haga clic en el botón **[!UICONTROL Re-draft]** de la barra de acciones.

   ![](assets/schema_extension_uc26.png)

1. Haga clic en **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta acción es definitiva: la tabla o las columnas de la base de datos del recurso y sus datos se eliminarán de forma permanente cuando se publique la modificación, lo que puede provocar la ruptura de los vínculos de otros recursos personalizados. Solo permanecerá disponible la definición del recurso.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vuelve a redactar una extensión del recurso predeterminado **Profiles (profile)** , también debe volver a redactar cualquier extensión **Test profile (seedMember)** que haya definido. Para obtener más información sobre la ampliación del recurso de perfil, consulte [esta sección](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique el recurso. Para ver los pasos más detallados, consulte [Publicación de un recurso personalizado](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   A continuación, el recurso entra en modo **Borrador** y su estado de activación es **[!UICONTROL Inactive]**.

1. En el modo **[!UICONTROL List]**, compruebe el recurso que desea eliminar y haga clic en el icono ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]**.

   ![](assets/schema_extension_uc28.png)

El recurso se elimina del modelo de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado utilizado en un evento, se cancela la publicación del evento correspondiente de manera automática. Consulte [Cancelación de la publicación de un evento transaccional](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
