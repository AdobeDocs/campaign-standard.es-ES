---
title: Selección de una audiencia en un mensaje
seo-title: Selección de una audiencia en un mensaje
description: Selección de una audiencia en un mensaje
seo-description: '«Procedimiento paso a paso para elegir audiencias de un correo electrónico: población objetivo principal y perfiles de prueba. "'
page-status-flag: no activado nunca
uuid: 7 d 8 f 8446-f 2 e 0-49 c 1-83 f 6-9667 b 29 bc 228
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: administración de audiencias
discoiquuid: 158 da 6 ff -8899-4 e 7 b-b 925-8 a 42 c 3 de 46 a 1
context-tags: Deliverycreation, wizard; entrega, audiencia, atrás
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c9e33f51ab497b8bd111dfc307670f2fde5d804f

---


# Selecting an audience in a message{#selecting-an-audience-in-a-message}

Adobe Campaign permite configurar varios tipos de perfiles dentro de la audiencia de un mensaje.

Las audiencias se pueden definir al crear el mensaje a través del asistente de creación o del panel de mensajes si el mensaje ya se ha creado.

>[!NOTE]
>
>Si la audiencia ha sido creada dentro de un flujo de trabajo y ha sido enriquecida con datos adicionales, no podrá utilizar estos datos para personalizar una entrega independiente. Solo se pueden utilizar desde una entrega ejecutada en un flujo de trabajo.

1. Desde el tablero, vaya al bloque de audiencia para comenzar.

   ![](assets/delivery_audience_definition_1.png)

   Se abre la pantalla para definir las audiencias. Cuenta con dos fichas que le permiten definir por separado cada tipo de audiencia que recibirá el mensaje:

   * Target
   * Perfiles de prueba
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. Audiencia objetivo normal del correo electrónico.

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   You can establish your main target using the [query editor](../../automating/using/editing-queries.md#creating-queries) functionalities.

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. The **[!UICONTROL Explorer]** tab allows you to access additional configurations.

   Por lo tanto, puede volver a utilizar y combinar audiencias existentes, aplicarles filtros adicionales, etc.

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. Los perfiles de prueba recibirán las pruebas que puede enviar antes de probar el correo electrónico antes de enviarlo al objetivo principal.

   For more information on configuring test profiles, refer to the [Test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md) section.

El bloque de audiencias se actualiza y muestra que se han seleccionado los perfiles de objetivo y de prueba para el correo electrónico en cuestión.

![](assets/delivery_audience_definition_3.png)

