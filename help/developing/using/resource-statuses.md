---
title: Estados de recursos
seo-title: Estados de recursos
description: Estados de recursos
seo-description: Descubrir los distintos estados de recursos según su estado de publicación.
page-status-flag: no activado nunca
uuid: 215 c 0 a 2 e -27 ec -43 f 3-baac -1 eaac 7640784
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: acerca de los recursos personalizados
discoiquuid: 85516477-1 b 95-4273-a 0 a 7-d 2 cbb 9950 afd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Resource statuses{#resource-statuses}

Los recursos pueden tener distintos estados según su publicación o estado de activación.

There are two columns dedicated to displaying these statuses in the **[!UICONTROL Custom resources]** screen.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: El recurso acaba de crearse o reescribirse. Para crear las tablas de base de datos y las API correspondientes, es necesario volver a publicar el recurso. Si se vuelve a redactar un recurso, se desactiva automáticamente después del paso de publicación.
* **Nuevo borrador pendiente**: se volvió a redactar el recurso. El proceso de reborrador se producirá durante la próxima publicación. Volver a crear la redacción no es posible. Varios mensajes de advertencia avisan al usuario de este hecho tanto cuando vuelve a crear la redacción como cuando se prepare para publicar.

   For more on re-drafting, see [Deleting a resource](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >The **[!UICONTROL Cancel re-draft]** option is available when the resource that you want to re-draft still contains links through other resources with the "Published" status. Esta opción le permite revertir el proceso "re-draft". Los recursos personalizados regresarán a sus estados originales.

* **Publicado**: el recurso se publicó. Si el recurso se modifica después de la última fecha de modificación, aparece un mensaje pidiéndole que vuelva a publicar para tener en cuenta las últimas modificaciones.

The **[!UICONTROL Do not publish latest modifications]** field prevents modifications from being taken into account during future publications.

Este campo se puede configurar en la definición de recursos personalizados.
