---
title: Recursos personalizados
description: Obtenga más información sobre la administración de recursos personalizados con API/
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: d7b2231d-46ff-4966-9ea7-27a775e5236b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 5%

---

# Recursos personalizados {#custom-resources}

Adobe Campaign incluye un modelo de datos predefinido, en el que los datos se definen a través de distintos recursos. Puede enriquecer el modelo de datos que se proporciona ampliando los recursos para agregar sus propios campos personalizados o tablas personalizadas, como tablas de productos o de compras.

Los recursos personalizados son accesibles a través de las API que usan la variable **/profileAndServicesExt** y el nombre del recurso personalizado.

`https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/`

>[!NOTE]
>
>Para los recursos que no están listos para usar, utilice siempre la variable <b>&quot;cus&quot;</b> antes del nombre del recurso.

Puede realizar cualquier operación con recursos personalizados, siempre que estén vinculados a la tabla Perfil . Por ejemplo, consideremos la estructura de las tablas a continuación:

![texto alternativo](assets/cusresources.png)

En ese caso, todos los recursos de la **Transacción**, **Detalles de transacción** y **Product** las tablas están disponibles siempre que estén vinculadas al **Perfil** tabla.

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
