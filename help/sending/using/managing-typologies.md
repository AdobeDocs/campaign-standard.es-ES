---
title: Administración de tipologías
description: Descubra cómo usar las tipologías.
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


# Administración de tipologías {#managing-typologies}

## Acerca de las tipologías {#about-typologies}

Las tipologías son conjuntos de reglas que permiten comprobar la validez del mensaje antes de enviarlo. Por ejemplo: El contenido del mensaje no está vacío, hay un baja, exclusión de duplicados, etc.

Se puede acceder a las tipologías a través del menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** . De forma predeterminada, hay una tipología predeterminada disponible en la aplicación. En función de sus necesidades, puede crear sus propias tipologías o modificar las existentes.

![](assets/typologies-list.png)

Para cada tipología, la **[!UICONTROL Typology rules]** sección lista el conjunto de reglas que se ejecutan al usar la tipología con un mensaje.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Para obtener más detalles sobre una de las reglas de tipología, haga clic en ella con el botón doble. La regla se mostrará en modo de solo lectura.

## Creating a typology {#creating-a-typology}

Para crear una nueva tipología, siga estos pasos:

1. Acceda al menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .

1. Se muestra la lista de tipologías. Haga clic en el botón **[!UICONTROL Create]**.

   ![](assets/typologies-create.png)

1. Defina la tipología **[!UICONTROL Label]**, luego haga clic en el **[!UICONTROL Add an element]** botón para seleccionar las reglas de tipología que desee incluir en ella. For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >El **[!UICONTROL IP affinity]** campo permite administrar las afinidades según la configuración. Se definen en el archivo de configuración de la instancia. Si desea utilizar las afinidades, póngase en contacto con el administrador.

1. Haga clic en **[!UICONTROL Create]** para confirmar la selección. Su tipología ya está lista para utilizarse en los mensajes.

## Aplicación de tipologías a mensajes {#applying-typologies-to-messages}

Al asociar una tipología con una plantilla de mensaje o mensaje, las reglas de tipología incluidas en la tipología se ejecutarán para comprobar la validez del mensaje.

>[!NOTE]
>
>A cada mensaje o plantilla de mensaje solo se le puede asignar una única tipología.

Para vincular una tipología a un mensaje, siga estos pasos:

1. Acceda a las propiedades del mensaje. Tenga en cuenta que se puede acceder a las plantillas de mensaje desde el menú **[!UICONTROL Resources]** > **[!UICONTROL Templates]** navegación.

1. En la sección **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]** , seleccione la tipología para vincular al mensaje.

   ![](assets/typology_message.png)

1. Haga clic **[!UICONTROL Confirm]**.

   La tipología seleccionada está ahora vinculada al mensaje. Todas sus reglas de tipología asociadas se ejecutarán para comprobar la validez del mensaje.
