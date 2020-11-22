---
solution: Campaign Standard
product: campaign
title: Eliminación de un recurso
description: 'Obtenga información sobre cómo eliminar un recurso '
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 14%

---


# Eliminación de un recurso{#deleting-a-resource}

Para eliminar un recurso, el recurso en cuestión debe ser un **[!UICONTROL Draft]**. El recurso está en **[!UICONTROL Draft]** estado si:

* Se acaba de crear y todavía no se ha publicado.
* Si ya se ha publicado, el recurso tiene que volver a redactarse.

>[!IMPORTANT]
>
>Volver a redactar y eliminar un recurso personalizado son operaciones delicadas que pueden afectar a otros recursos. Estas acciones deben ser realizadas únicamente por un usuario experto.

Para volver a redactar y eliminar un recurso publicado:

1. Seleccione el recurso que desee volver a redactar.
1. Haga clic en el botón **[!UICONTROL Re-draft]** de la barra de acciones.

   ![](assets/schema_extension_uc26.png)

1. Haga clic en **[!UICONTROL Ok]**.

   >[!IMPORTANT]
   >
   >Esta acción es definitiva: la tabla o columnas de la base de datos del recurso y sus datos se eliminarán de forma permanente cuando se publique la modificación, lo que puede generar vínculos rotos desde otros recursos personalizados. Solo la definición del recurso permanecerá disponible.

   ![](assets/schema_extension_uc27.png)

   >[!NOTE]
   >
   >Si vuelve a redactar una extensión del recurso de **Perfiles (perfil)** lista para usar, también debe volver a redactar cualquier extensión de perfil **de prueba (miembroDeSemilla)** que haya definido. For more on extending the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

1. Publique el recurso. Para obtener pasos más detallados, consulte [Publicación de un recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

   A continuación, el recurso pasa al modo **Borrador** y su estado de activación es **[!UICONTROL Inactive]**.

1. En **[!UICONTROL List]** modo, compruebe el recurso que desea eliminar y, a continuación, haga clic en el ![](assets/delete_darkgrey-24px.png) icono **[!UICONTROL Delete element]** .

   ![](assets/schema_extension_uc28.png)

El recurso se elimina del modelo de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado utilizado en un evento, se cancela la publicación del evento correspondiente de manera automática. See [Configuring transactional messaging](../../administration/using/configuring-transactional-messaging.md).

