---
solution: Campaign Standard
product: campaign
title: Conceptos del modelo de datos
description: Obtenga información sobre el modelo de datos de Adobe Campaign y cómo modificarlo.
audience: developing
content-type: reference
topic-tags: about-custom-resources
context-tags: cusResource,overview;eventCusResource,overview
feature: Modelo de datos
role: Desarrollador
level: Con experiencia
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 78%

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
>Solo los [administradores](../../administration/using/users-management.md#functional-administrators) funcionales con la función **[!UICONTROL Administration]** y acceso a **Todas las unidades** pueden acceder a registros de envío, registros de mensajes, registros de seguimiento, registros de exclusión o de suscripción. Un usuario no administrador puede segmentar estos registros, pero comenzando en una tabla vinculada (perfiles, envío).
