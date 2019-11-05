---
title: Conceptos del modelo de datos
description: Obtenga información sobre el modelo de datos de Adobe Campaign y cómo modificarlo.
page-status-flag: nunca activado
uuid: cacd563f-6936-4b3e-83e3-5d4ae31d44e8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: desarrollo
content-type: referencia
topic-tags: about-custom-resources
discoiquuid: 4e0468da-3052-4ce5-8174-45aba1f5c4ed
context-tags: cusResource,overview;eventCusResource,información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Conceptos del modelo de datos{#data-model-concepts}

Adobe Campaign incluye un modelo de datos predefinido. Este modelo de datos puede ser modificado por [administradores](../../administration/using/users-management.md#functional-administrators) que pueden agregar nuevos recursos o extensiones a los recursos existentes.

>[!CAUTION]
>
>La creación y modificación de recursos son operaciones sensibles que deben realizar únicamente los usuarios expertos.

El menú **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** , al que se accede mediante el logotipo de Adobe Campaign, le permite administrar los recursos **** personalizados, **publicarlos** y **acceder a las herramientas** de diagnóstico.

Los datos utilizados por Adobe Campaign se definen con diferentes recursos.

Puede **enriquecer la plantilla** de datos que se proporciona creando sus propios recursos personalizados, como tablas de productos o de compras.

Los recursos predeterminados (como campañas, correos electrónicos o audiencias) no se pueden modificar. Sin embargo, los recursos personalizados se pueden ampliar para agregar nuevos campos.

>[!NOTE]
>
>Puede encontrar una representación de modelo de datos para los recursos listos para usar [aquí](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

También puede **configurar la navegación** en las pantallas correspondientes al recurso creado.

Los campos de extensión se generan con un prefijo para que nunca entren en conflicto con los campos predeterminados.
