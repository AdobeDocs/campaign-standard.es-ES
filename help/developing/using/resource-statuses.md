---
title: Estados de recursos
description: Descubra los distintos estados de recursos según su estado de publicación.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: 7290ebc5-8a58-4b7f-99bf-d942e37c944e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---

# Estados de recursos{#resource-statuses}

Según su estado de publicación o activación, los recursos pueden tener diferentes estados.

Hay dos columnas dedicadas a mostrar estos estados en la variable **[!UICONTROL Custom resources]** pantalla.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de crearse o de volverse a redactar. Para crear las tablas de base de datos y las API correspondientes, el recurso debe volver a publicarse. Si se vuelve a redactar un recurso, queda inactivo automáticamente después del paso de publicación.
* **Nueva redacción pendiente**: el recurso se ha vuelto a redactar. El proceso de nuevo borrador se producirá durante la siguiente publicación. La nueva redacción es irreversible. Se muestran varios mensajes de advertencia para informar al usuario, tanto al volver a redactar como al prepararse para publicar.

  Para obtener más información sobre la nueva redacción, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

  >[!NOTE]
  >
  >El **[!UICONTROL Cancel re-draft]** está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado &quot;Publicado&quot;. Esta opción le permite revertir el proceso de &quot;nuevo borrador&quot;. Los recursos personalizados vuelven a su estado original.

* **Publicado**: se ha publicado el recurso. Si el recurso se modifica después de la última fecha de modificación, se muestra un mensaje para invitarle a volver a publicar el recurso a fin de tener en cuenta las últimas modificaciones.

El **[!UICONTROL Do not publish latest modifications]** Este campo evita que las modificaciones se tengan en cuenta en futuras publicaciones.

Este campo se puede configurar en la definición de recurso personalizada.
