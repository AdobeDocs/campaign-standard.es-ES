---
title: Administración de perfiles de prueba
description: Obtenga información sobre cómo administrar los perfiles de prueba.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 767d4233236019213003961aae1abb317198e581

---


# Administración de perfiles de prueba {#managing-test-profiles}

## Acerca de los perfiles de prueba {#about-test-profiles}

Los perfiles de prueba le permiten dirigirse a destinatarios adicionales que no coincidan con los criterios de objetivo definidos. Se agregan a la audiencia de un mensaje para detectar cualquier uso fraudulento de la base de datos de destinatarios o para garantizar que los correos electrónicos llegan a las bandejas de entrada.

Puede administrar los perfiles de prueba desde el menú avanzado **[!UICONTROL Profiles & audiences > Test profiles]**.

Un perfil de prueba contiene información ficticia de contacto, o información de contacto controlada por el remitente, que se puede utilizar en un mensaje en los siguientes contextos:

* Para enviar **pruebas**: La prueba es un mensaje específico que se utiliza para comprobar el mensaje antes de enviar la entrega finalizada a los destinatarios. Un perfil de prueba se encarga de comprobar la entrega, en relación con su contenido y formato. Consulte [Envío de pruebas](../../sending/using/sending-proofs.md).
* Para el procesamiento **de** correo electrónico: El perfil de prueba de procesamiento de correo electrónico se utiliza para comprobar la forma en que se muestra un mensaje según la bandeja de entrada del mensaje que lo recibe. Por ejemplo: webmail, servicio de mensajes, móvil, etc. Consulte Representación [por correo electrónico](../../sending/using/email-rendering.md).

   El uso de procesamiento **de** correo electrónico es de sólo lectura. Los perfiles de prueba con este uso solo están disponibles de forma predeterminada en Adobe Campaign.

* Como **trampa**: El mensaje se envía al perfil de prueba tal como se envía al destino principal. Consulte [Uso de trampas](../../sending/using/using-traps.md).
* Para **previsualizar** mensajes: Se puede seleccionar un perfil de prueba al obtener una vista previa de un mensaje para probar los elementos de personalización. Consulte [Vista previa de mensajes](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Creación de perfiles de prueba {#creating-test-profiles}

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Perfiles y audiencias > Probar perfiles** para acceder a la lista de perfiles de prueba.

   ![](assets/test_profile_creation_1.png)

1. En el **[!UICONTROL Test profiles]** tablero, haga clic en **Crear**.

   ![](assets/test_profile_creation_2.png)

1. Introduzca los datos de este perfil.

   ![](assets/test_profile_creation_3.png)

1. Seleccione el uso que desee para el perfil de prueba.

   ![](assets/test_profile_creation_4.png)

1. Introduzca los canales de contacto **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, así como la dirección del perfil de prueba si es necesario.

   >[!NOTE]
   >
   >Puede definir un formato de correo electrónico preferido: **[!UICONTROL Text]** o **[!UICONTROL HTML]**.

1. Especifique un tipo de evento y los datos de este evento si desea utilizar este perfil de prueba para probar la personalización de un mensaje transaccional.
1. Haga clic en **[!UICONTROL Create]** para guardar el perfil de prueba.

El perfil de prueba se agregará a continuación a la lista de perfiles.

**Tema relacionado:**

[Creación de un vídeo de perfil](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html) de prueba

## Edición de perfiles de prueba {#editing-test-profiles}

Para editar un perfil de prueba y consultar los datos vinculados a él, o para modificarlo:

1. Seleccione el perfil de prueba que desee editar haciendo clic en su imagen.
1. Consulte o modifique los campos.

   ![](assets/test_profile_edit.png)

1. Haga clic **[!UICONTROL Save]** si ha introducido los cambios o seleccione el nombre del perfil de prueba y, a continuación, **[!UICONTROL Test profiles]** en la sección de la parte superior de la pantalla para volver al tablero de perfiles de prueba.
