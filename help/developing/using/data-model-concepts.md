---
title: Conceptos del modelo de datos
seo-title: Conceptos del modelo de datos
description: Conceptos del modelo de datos
seo-description: Obtenga información sobre el modelo de datos de Adobe Campaign y cómo modificarlo.
page-status-flag: no activado nunca
uuid: cacd 563 f -6936-4 b 3 e -83 e 3-5 d 4 ae 31 d 44 e 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: acerca de los recursos personalizados
discoiquuid: 4 e 0468 da -3052-4 ce 5-8174-45 aba 1 f 5 c 4 ed
context-tags: Cusresource, overview; Eventcusresource, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Data model concepts{#data-model-concepts}

Adobe Campaign viene con un modelo de datos predefinido. This data model can be modified by [administrators](../../administration/using/users-management.md#functional-administrators) who are able to add new resources or extensions to existing resources.

>[!CAUTION]
>
>La creación y modificación de recursos son operaciones sensibles que solo deben ser realizadas por usuarios expertos.

The **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** menu, accessed via the Adobe Campaign logo, allows you to manage your **custom resources**, **publish** them, and **access the diagnostic tools**.

Los datos utilizados por Adobe Campaign se definen a través de diferentes recursos.

**Puede enriquecer la plantilla** de datos que se proporciona creando sus propios recursos personalizados, como las tablas de productos o compras.

No se pueden modificar los recursos predeterminados (como campañas, correos electrónicos o audiencias). Sin embargo, los recursos personalizados se pueden ampliar para agregar campos nuevos.

>[!NOTE]
>
>You can find a datamodel representation for the out-of-the-box resources [here](https://docs.campaign.adobe.com/doc/standard/en/datamodel/datamodel.html).

You can also **configure the navigation** in the screens corresponding to the resource created.

Los campos de extensión se generan con un prefijo para que nunca entren en conflicto con los campos predeterminados.
