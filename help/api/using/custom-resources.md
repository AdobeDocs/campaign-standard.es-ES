---
solution: Campaign Standard
product: campaign
title: Recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Ingeniero de datos
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 6%

---


# Recursos personalizados {#custom-resources}

Adobe Campaign incluye un modelo de datos predefinido, en el que los datos se definen a través de distintos recursos. Puede enriquecer el modelo de datos que se proporciona ampliando los recursos para agregar sus propios campos personalizados o tablas personalizadas, como tablas de productos o de compras.

Se puede acceder a los recursos personalizados mediante API que utilizan el extremo **/profileAndServicesExt** y el nombre del recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para los recursos que no están listos para usar, utilice siempre el prefijo <b>&quot;cus&quot;</b> antes del nombre del recurso.

Puede realizar cualquier operación con recursos personalizados, siempre que estén vinculados a la tabla Perfil . Por ejemplo, consideremos la estructura de las tablas a continuación:

![texto alternativo](assets/cusresources.png)

En ese caso, todos los recursos de las tablas **Transaction**, **TransactionDetails** y **Product** están disponibles siempre que estén vinculados a la tabla **Profile**.

<br/>

***Solicitud de ejemplo***

Solicitud de GET de ejemplo para acceder al recurso profileAndServicesExt extendido.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/\
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
```

Devuelve la lista de todos los recursos personalizados vinculados. A continuación, puede utilizar las URL de recursos para realizar cualquier tarea de API descrita en esta documentación.

```
{
"apiName": "resourceType",
"cusProduct": {
        "content": ...,
        "data": "/profileAndServicesExt/cusProduct/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusProduct/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
"cusTransaction": {
        "content": ...,
        "data": "/profileAndServicesExt/cusTransaction/",
        "help": "Product",
        "href": "https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/cusTransaction/metadata",
        "name": "cusProduct",
        "type": "collection"
    },
    ...
}
```

Para obtener más información sobre la extensión del modelo de datos, consulte la documentación de Campaign:

* [Conceptos del modelo de datos](../../developing/using/data-model-concepts.md)
* [Ampliación de la API](../../developing/using/about-extending-the-api.md)
* [Definición de vínculos con otros recursos](https://helpx.adobe.com/campaign/standard/developing/using/configuring-the-resource-s-data-structure.html#defining-links-with-other-resources)
