---
solution: Campaign Standard
product: campaign
title: Estados de recursos
description: Descubrir los distintos estados de recursos según su estado de publicación.
audience: developing
content-type: reference
topic-tags: about-custom-resources
translation-type: tm+mt
source-git-commit: 2729852365a2e74d2a603d95f75285fe54313e71
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# Estados de recursos{#resource-statuses}

Según el estado de publicación o activación, los recursos pueden tener distintos estados.

Hay dos columnas dedicadas a mostrar estos estados en la pantalla **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de ser creado o rediseñado. Para crear las tablas de base de datos, así como las API correspondientes, el recurso debe volver a publicarse. Si se está rediseñando un recurso, automáticamente se desactiva tras el paso de publicación.
* **Nuevo borrador** pendiente: se volvió a redactar el recurso. El proceso de re-borrador se producirá durante la próxima publicación. La nueva redacción es irreversible. Se muestran varios mensajes de advertencia para informar al usuario, tanto al volver a redactar como al prepararse para la publicación.

   Para obtener más información acerca de la nueva redacción, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >La opción **[!UICONTROL Cancel re-draft]** está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado &quot;Publicado&quot;. Esta opción le permite revertir el proceso de &quot;reborrador&quot;. Los recursos personalizados volverán a sus estados originales.

* **Publicado**: el recurso se ha publicado. Si el recurso se modifica después de la última fecha de modificación, se muestra un mensaje para invitarle a volver a publicar el recurso para tener en cuenta las últimas modificaciones.

El campo **[!UICONTROL Do not publish latest modifications]** impide que se tengan en cuenta las modificaciones en futuras publicaciones.

Este campo se puede configurar en la definición de recurso personalizada.
