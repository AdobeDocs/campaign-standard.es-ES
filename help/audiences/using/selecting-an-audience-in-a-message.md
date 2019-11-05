---
title: Selección de una audiencia en un mensaje
description: '"Procedimiento paso a paso para elegir las audiencias de un correo electrónico: población objetivo principal y perfiles de prueba".'
page-status-flag: nunca activado
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar-audiencias
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,asistente;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Selección de una audiencia en un mensaje{#selecting-an-audience-in-a-message}

Adobe Campaign permite configurar varios tipos de perfil dentro de la audiencia de un mensaje.

Las audiencias se pueden definir al crear el mensaje mediante el asistente de creación o desde el tablero de mensajes si el mensaje ya se ha creado.

>[!NOTE]
>
>Si la audiencia se ha creado en un flujo de trabajo y se ha enriquecido con datos adicionales, no podrá utilizar estos datos para personalizar una entrega independiente. Solo se pueden usar desde una entrega ejecutada en un flujo de trabajo.

1. Desde el tablero, vaya al bloque de audiencia para comenzar.

   ![](assets/delivery_audience_definition_1.png)

   Se abre la pantalla para definir las audiencias. Tiene dos fichas que le permiten definir por separado cada tipo de audiencia que recibirá el mensaje:

   * Target
   * Perfiles de prueba
   ![](assets/delivery_audience_definition_2.png)

1. Defina el principal **[!UICONTROL Target]** del correo electrónico. Ésta es la audiencia objetivo habitual del correo electrónico.

   El destino se define en la **[!UICONTROL Target]** ficha y está formado por perfiles identificados de la base de datos.

   Puede establecer el objetivo principal mediante las funciones del editor [de](../../automating/using/editing-queries.md#creating-queries) consultas.

   En esta ficha, la **[!UICONTROL Shortcuts]** paleta solo contiene filtros predefinidos y las audiencias que se han definido en los perfiles identificados. La **[!UICONTROL Explorer]** ficha le permite acceder a configuraciones adicionales.

   Por lo tanto, puede reutilizar y combinar audiencias existentes, aplicarles filtros adicionales, etc.

1. Defina el **[!UICONTROL Test profiles]** que desee utilizar para el correo electrónico. Los perfiles de prueba recibirán las pruebas que puede enviar antes para probar el correo electrónico antes de enviarlo al destino principal.

   Para obtener más información sobre la configuración de perfiles de prueba, consulte la sección Perfiles [de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md) .

El bloque de audiencias se actualiza y muestra que se ha seleccionado un objetivo y perfiles de prueba para el correo electrónico en cuestión.

![](assets/delivery_audience_definition_3.png)

