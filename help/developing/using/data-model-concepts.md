---
title: Conceptos del modelo de datos
description: Obtenga información sobre el modelo de datos de Adobe Campaign y cómo modificarlo.
page-status-flag: never-activated
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3895755aa2eeceb837f78f591bb6504d3eadec1f
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 84%

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
>Solo [los administradores](../../administration/using/users-management.md#functional-administrators)funcionales, con **[!UICONTROL Administration]** función y acceso a **todas** las unidades, pueden acceder al envío de registros, registros de mensajes, registros de seguimiento, registros de exclusión o de suscripción. Un usuario no administrador puede destinatario estos registros, pero puede comenzar en una tabla vinculada (perfiles, envío).
