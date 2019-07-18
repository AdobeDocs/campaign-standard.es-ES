---
title: Eliminación de un recurso
seo-title: Eliminación de un recurso
description: Eliminación de un recurso
seo-description: 'Cómo eliminar un recurso '
page-status-flag: no activado nunca
uuid: 5 de 27589-6 fa 5-412 c -8 e 5 a-a 4976 de 05715
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 0130733 d -4 e 3 f -40 cd-b 959-56381 f 2 c 8 f 44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Deleting a resource{#deleting-a-resource}

To delete a resource, the resource in question must be a **[!UICONTROL Draft]**. The resource is in **[!UICONTROL Draft]** status if:

* Acaba de crearse y aún no se ha publicado.
* Si ya se ha publicado, es necesario volver a diseñar el recurso.

>[!CAUTION]
>
>Volver a diseñar y eliminar un recurso personalizado son operaciones sensibles que pueden afectar a otros recursos. Estas acciones deben ser efectuadas únicamente por un usuario experto.

Para volver a crear un borrador y eliminar un recurso publicado:

1. Seleccione el recurso que desee volver a crear.
1. Click the **[!UICONTROL Re-draft]** button in the action bar.

   ![](assets/schema_extension_uc26.png)

1. Click **[!UICONTROL Ok]**.

   >[!CAUTION]
   >
   >Esta acción es definitiva: la tabla o los colums de la base de datos del recurso y sus datos se eliminarán de forma permanente cuando se publique la modificación, lo que puede generar vínculos rotos de otros recursos personalizados. Solo la definición de recurso seguirá estando disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >If you re-draft an extension of the out-of-the-box **Profiles (profile)** resource, you must also re-draft any **Test profile (seedMember)** extension you may have defined. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique el recurso. For more detailed steps, refer to [Publishing a custom resource](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).

   The resource then goes into **Draft** mode and its activation status is **[!UICONTROL Inactive]**.

1. In **[!UICONTROL List]** mode, check the resource to delete then click the ![](assets/delete_darkgrey-24px.png) **[!UICONTROL Delete element]** icon.

   ![](assets/schema_extension_uc28.png)

El recurso se elimina del modelo de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado en un evento, el evento correspondiente se cancelará automáticamente. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

