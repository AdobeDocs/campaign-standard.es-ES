---
title: Control de cambios en el modelo de datos
description: Obtenga información sobre cómo diagnosticar el modelo de datos de Adobe Campaign.
audience: developing
content-type: reference
topic-tags: about-custom-resources
feature: Data Model
role: Developer
level: Experienced
exl-id: ced9a897-47e9-4128-84fb-35660c553cd4
source-git-commit: 5fef74296a4790102c75e609c270e52d5ead1d58
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 8%

---

# Control de cambios en el modelo de datos{#monitoring-data-model-changes}

Desde el **[!UICONTROL Diagnosis]** , puede ver los objetos técnicos generados por la aplicación para analizarlos.

>[!NOTE]
>
>Las pantallas de este menú son de solo lectura.

![](assets/diagnostic.png)

Puede ver los siguientes tipos de objetos:

* Esquemas de datos
* Páginas web
* Filtros
* Navegación
* Componentes
* Trabajos por lotes

Puede cambiar la configuración de la lista:

* Puede añadir y quitar columnas.
* Puede definir los nombres de las columnas.
* Puede definir el orden de visualización de las columnas en la lista.
* Puede elegir el orden de los valores en la lista.

Puede filtrar la lista:

* Puede incluir o excluir esquemas de datos nativos, páginas web, filtros y objetos de navegación.
* Puede buscar objetos por su nombre.
* Puede filtrar los trabajos por lotes según su estado, fecha de inicio y fecha de finalización.

Puede descargar la lista mostrada en un archivo en formato TXT con valores separados por comas.

Puede ver los detalles del objeto seleccionado.

Por ejemplo, puede utilizar esta función para ver los criterios de filtrado de los filtros predeterminados. Este ejemplo muestra el código que se muestra para los criterios de filtrado de un filtro predeterminado:

```xml
<where displayFilter="Has clicked an offer">
  <condition boolOperator="AND" enabledIf="$(offer) != ''" expr="trackingLog" internalId="1" setOperator="EXISTS">
    <condition boolOperator="AND" expr="[url/offer] = $RestKey(offer)" internalId="2"/>
    <condition boolOperator="AND" expr="[@url-id] != 1" internalId="3"/>
  </condition>
</where>
```

![](assets/diagnosis_filter_criteria.png)