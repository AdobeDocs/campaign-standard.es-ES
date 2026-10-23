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
TQID: 'https://experienceleague.adobe.com/f0ihge9X4opmgRRdswkBt7yMWSmJc36viZKWXPoQCe4'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 1%
---
# Estados de recursos{#resource-statuses}

Según su estado de publicación o activación, los recursos pueden tener diferentes estados.

Hay dos columnas dedicadas a mostrar estos estados en la pantalla **[!UICONTROL Custom resources]**.

![](assets/schema_colonne_1.png)

**Estados de publicación**

* **Borrador**: el recurso acaba de ser creado o vuelto a redactar. Para crear las tablas de base de datos y las API correspondientes, el recurso debe volver a publicarse. Si se vuelve a redactar un recurso, queda inactivo automáticamente después del paso de publicación.
* **Borrador pendiente**: el recurso se ha vuelto a redactar. El proceso de nuevo borrador se producirá durante la siguiente publicación. La nueva redacción es irreversible. Se muestran varios mensajes de advertencia para informar al usuario, tanto al volver a redactar como al prepararse para publicar.

  Para obtener más información sobre cómo volver a redactar, consulte [Eliminación de un recurso](../../developing/using/deleting-a-resource.md).

  >[!NOTE]
  >
  >La opción **[!UICONTROL Cancel re-draft]** está disponible cuando el recurso que desea volver a redactar aún contiene vínculos a través de otros recursos con el estado &quot;Publicado&quot;. Esta opción le permite revertir el proceso de &quot;nuevo borrador&quot;. Los recursos personalizados vuelven a su estado original.

* **Publicado**: el recurso se ha publicado. Si el recurso se modifica después de la última fecha de modificación, se muestra un mensaje para invitarle a volver a publicar el recurso a fin de tener en cuenta las últimas modificaciones.

El campo **[!UICONTROL Do not publish latest modifications]** evita que se tengan en cuenta las modificaciones durante futuras publicaciones.

Este campo se puede configurar en la definición de recurso personalizada.
