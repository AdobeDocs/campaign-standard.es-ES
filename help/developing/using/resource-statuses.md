---
title: Estados de recursos
description: Descubrir los distintos estados de recursos según su estado de publicación.
page-status-flag: never-activated
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 1%

---


# Estados de recursos{#resource-statuses}

Según el estado de publicación o activación, los recursos pueden tener distintos estados.

Hay dos columnas dedicadas a mostrar estos estados en la **[!UICONTROL Custom resources]** pantalla.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de ser creado o rediseñado. Para crear las tablas de base de datos y las API correspondientes, el recurso debe volver a publicarse. Si se está rediseñando un recurso, automáticamente se desactiva tras el paso de publicación.
* **Nuevo borrador** pendiente: se volvió a redactar el recurso. El proceso de re-borrador se producirá durante la próxima publicación. La nueva redacción es irreversible. Se muestran varios mensajes de advertencia para informar al usuario, tanto al volver a redactar como al prepararse para la publicación.

   Para obtener más información sobre cómo volver a redactar, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >La **[!UICONTROL Cancel re-draft]** opción está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado &quot;Publicado&quot;. Esta opción le permite revertir el proceso de &quot;reborrador&quot;. Los recursos personalizados volverán a sus estados originales.

* **Publicado**: el recurso se ha publicado. Si el recurso se modifica después de la última fecha de modificación, se muestra un mensaje para invitarle a volver a publicar el recurso para tener en cuenta las últimas modificaciones.

El **[!UICONTROL Do not publish latest modifications]** campo impide que se tengan en cuenta las modificaciones en futuras publicaciones.

Este campo se puede configurar en la definición de recurso personalizada.
