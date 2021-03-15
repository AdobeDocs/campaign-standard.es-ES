---
solution: Campaign Standard
product: campaign
title: Estados de recursos
description: Descubra los distintos estados de recursos según su estado de publicación.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Modelo de datos
role: Desarrollador
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 1%

---


# Estados de recursos{#resource-statuses}

Según su estado de publicación o activación, los recursos pueden tener diferentes estados.

Hay dos columnas dedicadas a mostrar estos estados en la pantalla **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de crearse o de redactarse de nuevo. Para crear las tablas de la base de datos, así como las API correspondientes, se debe volver a publicar el recurso. Si se vuelve a redactar un recurso, este se desactiva automáticamente tras el paso de publicación.
* **Recambio pendiente**: se ha reformulado el recurso. El proceso de nuevo borrador se producirá durante la siguiente publicación. La nueva redacción es irreversible. Se muestran varios mensajes de advertencia para informar al usuario, tanto al volver a redactar como al prepararse para publicar.

   Para obtener más información sobre la nueva redacción, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

   >[!NOTE]
   >
   >La opción **[!UICONTROL Cancel re-draft]** está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado &quot;Publicado&quot;. Esta opción le permite revertir el proceso de &quot;nuevo borrador&quot;. A continuación, los recursos personalizados vuelven a sus estados originales.

* **Publicado**: el recurso se ha publicado. Si el recurso se modifica después de la última fecha de modificación, aparece un mensaje que le invita a volver a publicar el recurso para tener en cuenta las últimas modificaciones.

El campo **[!UICONTROL Do not publish latest modifications]** evita que se tengan en cuenta las modificaciones durante publicaciones futuras.

Este campo se puede configurar en la definición de recurso personalizada.
