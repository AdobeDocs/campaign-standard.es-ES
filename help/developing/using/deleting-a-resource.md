---
title: Eliminación de un recurso
description: 'Obtenga información sobre cómo eliminar un recurso '
page-status-flag: never-activated
uuid: 5de27589-6fa5-412c-8e5a-a4976de05715
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 0130733d-4e3f-40cd-b959-56381f2c8f44
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f7f4f3d81f4e6a540b3317f283c1e2311ccc65a

---


# Eliminación de un recurso{#deleting-a-resource}

Para eliminar un recurso, el recurso en cuestión debe ser un **[!UICONTROL Draft]**. El recurso está en**[!UICONTROL Draft]** estado si:

* Se acaba de crear y todavía no se ha publicado.
* Si ya se ha publicado, el recurso tiene que volver a redactarse.

>[!CAUTION]
>
>Volver a redactar y eliminar un recurso personalizado son operaciones delicadas que pueden afectar a otros recursos. Estas acciones deben ser realizadas únicamente por un usuario experto.

Para volver a redactar y eliminar un recurso publicado:

1. Seleccione el recurso que desee volver a redactar.
1. Haga clic en el **[!UICONTROL Re-draft]**botón de la barra de acciones.

   ![](assets/schema_extension_uc26.png)

1. Haga clic **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta acción es definitiva: la tabla o columnas de la base de datos del recurso y sus datos se eliminarán de forma permanente cuando se publique la modificación, lo que puede generar vínculos rotos desde otros recursos personalizados. Sólo la definición del recurso permanecerá disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vuelve a redactar una extensión del recurso **Perfiles (perfil)** incorporado, también debe volver a redactar cualquier extensión de perfil **de prueba (miembroDeinicialización)** que haya definido. Para obtener más información sobre cómo ampliar el recurso de perfil, consulte [esta sección](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique el recurso. Para obtener pasos más detallados, consulte [Publicación de un recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

   A continuación, el recurso pasa al modo **Borrador** y su estado de activación es **[!UICONTROL Inactive]**.

1. En **[!UICONTROL List]**modo, compruebe el recurso que desea eliminar y, a continuación, haga clic en el![](assets/delete_darkgrey-24px.png)icono**[!UICONTROL Delete element]** .

   ![](assets/schema_extension_uc28.png)

El recurso se elimina del modelo de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado utilizado en un evento, el evento correspondiente se cancelará automáticamente la publicación. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

