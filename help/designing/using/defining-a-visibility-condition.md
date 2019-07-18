---
title: Definición de una condición de visibilidad
seo-title: Definición de una condición de visibilidad
description: Definición de una condición de visibilidad
seo-description: Hacer que un elemento de página Web sea visible solo si se respeta una determinada condición.
page-status-flag: no activado nunca
uuid: 224005 ba-ef 09-4790-b 2 f 0-30 ed 74 cfa 32 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: definir-condicional-content
discoiquuid: c 12125 a 7-a 1 cf -4 bc 1-a 138-57 ff 74974024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining a visibility condition{#defining-a-visibility-condition}

Puede especificar una condición de visibilidad en cualquier elemento. Solo será visible si se respeta la condición.

To add a visibility condition, select a block and enter the condition to be respected in the **[!UICONTROL Visibility condition]** field of its settings.

![](assets/delivery_content_5.png)

Esta opción solo está disponible para los siguientes elementos: ADDRESS, BLOCKQUOTE, CENTER, DIR, DIV, DL, FIELDSET, FORM, H 1, H 2, H 3, H 4, H 5, H 6, H 4, H 5, H 6, PRE, UL, TR, TR, TD.

The expression editor is presented in the [Advanced expression editing](../../automating/using/editing-queries.md#about-query-editor) section.

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). De forma predeterminada, todos los campos son visibles.

>[!NOTE]
>
>No se puede definir una condición para un bloque que ya contiene un subelemento con un contenido dinámico o un bloque que ya constituye un contenido dinámico. Los bloques dinámicos no visibles como listas desplegables no se pueden editar.

