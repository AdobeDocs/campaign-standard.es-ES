---
solution: Campaign Standard
product: campaign
title: Personalización de mensajes de Campaign con datos de Puntos de interés
description: Aprenda a crear un mensaje personalizado basado en la ubicación de sus suscriptores con la integración de datos del punto de interés.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 10%

---


# Personalización de mensajes de Campaign con datos de Puntos de interés{#personalizing-campaign-messages-with-point-of-interest-data}

En Adobe Campaign, puede utilizar los datos de puntos de interés recopilados de los suscriptores de la aplicación móvil para enviarles mensajes de marketing personalizados, como un correo electrónico.

Solo puede reaccionar en los datos del punto de interés con envíos estándar. [Los mensajes transaccionales](../../channels/using/getting-started-with-transactional-msg.md) no pueden utilizar datos de ubicación.

Lo más temprano que se puede reaccionar son unos 10 minutos.

En este caso, usted decide enviar un correo electrónico a todos los suscriptores que han visitado su tienda de Boston en las últimas dos semanas.

1. Cree una actividad de marketing por correo electrónico.
1. Al definir la audiencia del envío, arrastre y suelte el **[!UICONTROL Subscriptions to an application]** elemento en el espacio de trabajo.

   ![](assets/poi_subscriptions_app.png)

   La administración de audiencias se detalla en la sección [Definición de audiencias](../../audiences/using/creating-audiences.md) .

1. In the **[!UICONTROL Add a rule - Profile/Subscriptions to an application]** window, drag and drop the **[!UICONTROL POI Location Subscription]** element into the workspace.

   ![](assets/poi_add_rule_profile_subscription.png)

1. En la **[!UICONTROL Add a rule - POI Location Subscription]** ventana, introduzca la etiqueta del punto de interés que desea utilizar.

   ![](assets/poi_location_subscription.png)

1. En el campo **[!UICONTROL Filter type]**, seleccione **[!UICONTROL Relative]**.
1. Marque la **[!UICONTROL Preceding days]** opción e introduzca **[!UICONTROL 15]** en el campo correspondiente.
1. Defina el número de veces que el usuario debe haber visitado el punto de interés.
1. Click **[!UICONTROL Confirm]** to save your audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Añada contenido a su correo electrónico.

   ![](assets/poi_email_content.png)

1. Confirme la creación de la actividad para la vista del panel del correo electrónico.
1. Envíe su mensaje.

El correo electrónico con la oferta de descuento del 10 % se enviará a los suscriptores que:

* Visitó su tienda de Boston al menos una vez en las últimas dos semanas.
* Tener la aplicación móvil en primer plano al menos una vez durante la visita.

**Temas relacionados:**

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Definición de contenido](../../designing/using/personalization.md#example-email-personalization)
* [Envío de mensajes](../../sending/using/confirming-the-send.md)

