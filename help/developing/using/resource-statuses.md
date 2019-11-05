---
title: Estados de recursos
description: Descubrir los distintos estados de recursos según su estado de publicación.
page-status-flag: nunca activado
uuid: 215c0a2e-27ec-43f3-baac-1eaac7640784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: desarrollo
content-type: referencia
topic-tags: about-custom-resources
discoiquuid: 85516477-1b95-4273-a0a7-d2cbb9950afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Estados de recursos{#resource-statuses}

Los recursos pueden tener distintos estados según su estado de publicación o activación.

Hay dos columnas dedicadas a mostrar estos estados en la **[!UICONTROL Custom resources]** pantalla.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de ser creado o rediseñado. Para crear las tablas de base de datos y las API correspondientes, el recurso debe volver a publicarse. Si se está rediseñando un recurso, se procesa automáticamente como inactivo tras el paso de publicación.
* **Nuevo borrador** pendiente: se volvió a redactar el recurso. El proceso de re-borrador se producirá durante la próxima publicación. La nueva redacción es irreversible. Varios mensajes de advertencia advierten al usuario de este hecho tanto al volver a redactar como al prepararse para publicar.

   Para obtener más información sobre cómo volver a redactar, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >La **[!UICONTROL Cancel re-draft]** opción está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado "Publicado". Esta opción le permite revertir el proceso de "reborrador". Los recursos personalizados volverán a sus estados originales.

* **Publicado**: el recurso se ha publicado. Si el recurso se modifica después de la última fecha de modificación, aparece un mensaje en el que se solicita al usuario que vuelva a publicar para tener en cuenta las últimas modificaciones.

El **[!UICONTROL Do not publish latest modifications]** campo impide que se tengan en cuenta las modificaciones en futuras publicaciones.

Este campo se puede configurar en la definición de recurso personalizada.
