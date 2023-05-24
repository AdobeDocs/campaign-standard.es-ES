---
title: Conceptos del modelo de datos
description: Obtenga información sobre el modelo de datos de Adobe Campaign y cómo modificarlo.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Data Model
role: Developer
level: Experienced
exl-id: 6e9e016a-473b-4a51-8bd6-c23c7b3d3610
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 79%

---

# Conceptos del modelo de datos{#data-model-concepts}

Adobe Campaign viene con un modelo de datos predefinido. Este modelo de datos lo pueden modificar los [administradores](../../administration/using/users-management.md#functional-administrators), que pueden añadir nuevos recursos o extensiones a los recursos existentes.

>[!CAUTION]
>
>La creación y modificación de recursos son operaciones sensibles que deben realizar únicamente los usuarios expertos.

El menú **[!UICONTROL Administration]** > **[!UICONTROL Development]** , al que se accede mediante el logotipo de Adobe Campaign, le permite administrar los **recursos personalizados**, **publicarlos** y **acceder a las herramientas de diagnóstico**.

Los datos que usa Adobe Campaign se definen a través de diferentes recursos. Puede **enriquecer la plantilla de datos** proporcionada creando sus propios recursos personalizados, como tablas de productos o de compras.

Los recursos integrados (como campañas, correos electrónicos o audiencias) no se pueden modificar. Sin embargo, los recursos personalizados se pueden ampliar para añadir nuevos campos.

Los campos de extensión se generan con un prefijo para que nunca entren en conflicto con los campos integrados.

>[!NOTE]
>
>Puede encontrar una representación de modelo de datos para los recursos integrados en [esta página](../../developing/using/datamodel-introduction.md).

También puede [configurar la navegación](configuring-the-screen-definition.md) en las pantallas correspondientes al recurso creado.

Es posible **exportar e importar** recursos personalizados, por ejemplo, del desarrollo al entorno de producción. Para obtener más información al respecto consulte este [caso de uso paso a paso](../../automating/using/exporting-importing-custom-resources.md).

>[!CAUTION]
>
>Solo funcional [administradores](../../administration/using/users-management.md#functional-administrators), con **[!UICONTROL Administration]** función y acceso a **Todo** las unidades pueden acceder a los registros de envío, los registros de mensajes, los registros de seguimiento y los registros de exclusión o suscripción. Un usuario no administrador puede dirigirse a estos registros empezando por una tabla vinculada (perfiles, envío).
