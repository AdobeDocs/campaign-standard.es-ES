---
title: Administración de reglas de tipología
description: Descubra cómo usar reglas de tipología.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ba1fcca02ce9582d85e57bde815ccf3f551ac7a3

---


# Administración de reglas de tipología {#managing-typology-rules}

## Acerca de las reglas de tipología {#about-typology-rules}

Las Reglas de tipología son reglas comerciales que permiten realizar comprobaciones y filtros en el mensaje antes de enviarlo. Los tipos de reglas de tipología disponibles son:

* **Filtrado** de reglas: Este tipo de regla permite excluir una parte del destinatario de mensajes según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado un determinado número de correos electrónicos. Para obtener más información, consulte [esta sección](../../sending/using/filtering-rules.md).

* **Reglas de fatiga** : Este tipo de reglas le permite definir un número máximo de mensajes por perfil para evitar que se soliciten demasiado. Para obtener más información, consulte [esta sección](../../sending/using/fatigue-rules.md).

* **Reglas de control** : Este tipo de reglas permite al usuario comprobar la validez y calidad de los mensajes antes de enviarlos, como la visualización de caracteres, el tamaño del mensaje SMS, el formato de la dirección, etc. Para obtener más información, consulte [esta sección](../../sending/using/control-rules.md).

Las Reglas de tipología están disponibles en el menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** > **[!UICONTROL Typology rules]** .

De forma predeterminada, hay disponibles varias reglas de tipología de **filtrado** y **control** listas para usar. Se detallan en las secciones Reglas [de](../../sending/using/fatigue-rules.md) filtrado y Reglas [de control](../../sending/using/control-rules.md) .

Según sus necesidades, puede modificar reglas de tipología existentes o crear otras nuevas, excepto **[!UICONTROL Control]** las reglas, que son de solo lectura y no se pueden modificar.

## Crear una regla de tipología {#creating-a-typology-rule}

Los pasos principales para crear una reglas de tipología son los siguientes:

1. Acceda al menú **[!UICONTROL Administration]** / **[!UICONTROL Channels]** / **[!UICONTROL Typologies]** / **[!UICONTROL Typology rules]** y haga clic en **[!UICONTROL Create]**.

   ![](assets/typology_create-rule.png)

1. Introduzca la tipología **[!UICONTROL Label]** y, a continuación, especifique **[!UICONTROL Channel]** a qué debe aplicarse la regla.

   ![](assets/typology-rule-label.png)

1. Especifique la reglas de tipología **[!UICONTROL Type]**, luego configúrela según sus necesidades. Tenga en cuenta que la configuración de reglas de tipología varía según el tipo. Para obtener más información, consulte las secciones Reglas **[de](../../sending/using/filtering-rules.md)**filtrado y Reglas de**[ fatiga](../../sending/using/fatigue-rules.md)** .

1. Seleccione las tipologías en las que desea incluir la nueva regla. Para ello, seleccione la **[!UICONTROL Typologies]** ficha y, a continuación, haga clic en **[!UICONTROL Create element]** el botón .

   ![](assets/typology-typologies-tab.png)

1. Seleccione la tipología que desee y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/typology-link.png)

1. Una vez seleccionadas todas las tipologías, haga clic en **[!UICONTROL Create]** para confirmar la creación de la reglas de tipología.

## Orden de ejecución de Reglas de tipología {#typology-rules-execution-order}

Las Reglas de tipología se ejecutan en un orden especificado durante las fases de segmentación, análisis y personalización de mensajes.

En el modo de operación estándar, las reglas se aplican en la siguiente secuencia:

1. Reglas de control, si se aplican al principio del objetivo.
1. Reglas de filtrado:

   * Reglas de aplicación nativas para la revisión de direcciones: dirección definida/dirección no verificada/dirección en lista negra/dirección en cuarentena/calidad de la dirección.
   * Reglas de filtrado definidas por el usuario.

1. Reglas de control, si se aplican al final del objetivo.
1. Reglas de control, si se aplican al inicio de la personalización.
1. Reglas de control, si se aplican al final de la personalización.

Sin embargo, puede adaptar el orden de ejecución del mismo tipo de reglas en cada tipología. De hecho, cuando se ejecutan varias reglas durante la misma fase de procesamiento de mensajes, puede elegir el orden en que se aplican.

Por ejemplo, una regla de filtrado cuya orden de ejecución se posiciona en el número 20 se ejecutará antes que una regla de filtrado cuya orden de ejecución se posicione en el número 30.

En el caso **[!UICONTROL Properties]** de una reglas de tipología, puede establecer su orden de ejecución. Cuando se deben aplicar varias reglas, el orden de ejecución de cada regla determina las que se deben procesar primero. Para obtener más información sobre esto, consulte la sección Orden [de ejecución de](#typology-rules-execution-order) Reglas de tipología.

![](assets/typology_rule-active.png)

Una reglas de tipología se puede desactivar mediante su función **[!UICONTROL Properties]** si no desea que la regla se aplique en el momento en que se analizan los mensajes relacionados con la regla.

![](assets/typology_rule-order.png)