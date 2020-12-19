---
solution: Campaign Standard
product: campaign
title: Prueba de un mensaje transaccional
description: Aprenda a probar un mensaje transaccional en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 41%

---


# Prueba de un mensaje transaccional {#testing-a-transactional-message}

Antes de publicar el mensaje transaccional, puede crear un perfil de prueba específico que le permita comprobar correctamente el mensaje.

## Definición de un perfil de prueba específico {#defining-specific-test-profile}

Defina un perfil de prueba que se vinculará a su evento, lo que le permitirá previsualización de su mensaje y enviar una prueba relevante.

1. En el panel [mensaje transaccional](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), haga clic en el botón **[!UICONTROL Create test profile]**.

   ![](assets/message-center_test-profile.png)

1. Especifique la información que desea enviar en formato JSON en la sección **[!UICONTROL Event data used for personalization]**. Este es el contenido que se utiliza al obtener una vista previa del mensaje y cuando el perfil de prueba reciba la prueba.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Si ha enriquecido su mensaje, también puede introducir información relacionada con otra tabla, como **[!UICONTROL Profile]**. Consulte [Enriquecimiento del evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) y [Personalización de un mensaje transaccional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Una vez creado, el perfil de prueba se especificará previamente en el mensaje transaccional. Haga clic en el bloque **[!UICONTROL Test profiles]** del mensaje para comprobar el destinatario de la prueba.

   ![](assets/message-center_5.png)

También puede crear un nuevo perfil de prueba o utilizar uno que ya exista en el menú **[!UICONTROL Test profiles]**. Para ello:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. En la sección **[!UICONTROL Event]**, seleccione el evento que acaba de crear. En este ejemplo, seleccione “Abandono del carro de compras (EVTcartAbandonment)”.
1. Especifique la información que desea enviar en formato JSON en el cuadro de texto **[!UICONTROL Event data]**.

   ![](assets/message-center_3.png)

1. Guarde los cambios.
1. [Acceda al ](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) mensaje que ha creado y seleccione el perfil de prueba actualizado.

**Temas relacionados:**

* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Creación de audiencias](../../audiences/using/creating-audiences.md)

## Envío de una prueba {#sending-proof}

Una vez que haya creado uno o varios perfiles de prueba específicos y guardado el mensaje transaccional, puede enviar una prueba para probarlo.

![](assets/message-center_10.png)

Los pasos para enviar una prueba se detallan en la sección [Envío de pruebas](../../sending/using/sending-proofs.md).
