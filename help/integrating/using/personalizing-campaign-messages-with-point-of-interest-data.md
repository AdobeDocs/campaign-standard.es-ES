---
title: Personalización de mensajes de campaña con datos de Punto de interés
seo-title: Personalización de mensajes de campaña con datos de Punto de interés
description: Personalización de mensajes de campaña con datos de Punto de interés
seo-description: Obtenga información sobre cómo crear un mensaje personalizado basado en la ubicación de los suscriptores con la integración de datos del punto de interés.
page-status-flag: no activado nunca
uuid: d 74 c 3 e 55-f 130-441 b-bc 2 a -06 ddcd 5 d 9784
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-mobile-for-mobile
discoiquuid: a 1736 ba 3-5121-4 d 01-bf 04-ebb 7 e 701 e 2 e 0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Personalizing Campaign messages with Point of Interest data{#personalizing-campaign-messages-with-point-of-interest-data}

En Adobe Campaign, puede utilizar los datos de Puntos de interés recopilados de los suscriptores de la aplicación móvil para enviarles mensajes de mercadotecnia personalizados, como un correo electrónico.

Solo puede reaccionar en los datos de Punto de interés con envíos estándar. [Los mensajes transaccionales](../../channels/using/about-transactional-messaging.md) no pueden utilizar datos de ubicación.

Cuanto más alta sea la reacción, más de 10 minutos.

En este caso, decide enviar un correo electrónico a todos los suscriptores que hayan visitado la tienda de Boston en las últimas dos semanas.

1. Cree una actividad de marketing por correo electrónico.
1. When defining the delivery's audience, drag and drop the **[!UICONTROL Subscriptions to an application]** element into the workspace.

   ![](assets/poi_subscriptions_app.png)

   Managing audiences is detailed in the [Defining audiences](../../audiences/using/creating-audiences.md) section.

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. In the **[!UICONTROL Add a rule - POI Location Subscription]** window, enter the label of the Point of Interest that you want to use.

   ![](assets/poi_location_subscription.png)

1. In the **[!UICONTROL Filter type]** field, select **[!UICONTROL Relative]**.
1. Check the **[!UICONTROL Preceding days]** option and enter **[!UICONTROL 15]** in the corresponding field.
1. Defina el número de veces que el usuario debe haber visitado el punto de interés.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Agregue contenido al correo electrónico.

   ![](assets/poi_email_content.png)

1. Confirme la creación de la actividad para ver el tablero del correo electrónico.
1. Envíe el mensaje.

El correo electrónico con la oferta del 10% de descuento se enviará a los suscriptores que:

* Se ha visitado Boston al menos una vez dentro de las últimas dos semanas.
* Tenía la aplicación móvil en primer plano al menos una vez durante la visita.

**Temas relacionados:**

* [Creación de un mensaje de correo electrónico](../../channels/using/creating-an-email.md)
* [Definición de contenido](../../designing/using/example--email-personalization.md)
* [Envío de mensajes](../../sending/using/confirming-the-send.md)

