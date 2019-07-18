---
title: Clics directos
seo-title: Clics directos
description: Clics directos
seo-description: Con el informe predeterminado Clics directos, conozca dónde hizo clic el cliente en la entrega.
page-status-flag: no activado nunca
uuid: 7 ed 49 dd 3-d 7 ee -466 a -9 a 7 b-d 2 aa 16961667
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: lista de informes
discoiquuid: ecbc 1 ade -63 d 9-4 ac 2-9828-380 a 1 aa 95094
context-tags: Deliveryhotclicksreport, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Hot clicks{#hot-clicks}

This report can be accessed from the **[!UICONTROL Reports]** button in each delivery or transactional message.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta el contenido del mensaje (HTML o texto) con el porcentaje de clics en cada vínculo.

![](assets/delivery_reports_10.png)

Si ha creado contenido dinámico para la entrega, puede ver los porcentajes de cada condición que haya definido. For more on inserting conditional content in a delivery, see [Defining dynamic content](../../designing/using/defining-dynamic-content-in-a-landing-page.md).

Por ejemplo, imagine que ha creado una entrega con las condiciones siguientes:

* El vínculo de la imagen principal es diferente si el destinatario es hombre o mujer.
* También agregó un vínculo a una oferta especial que solo es visible para destinatarios mayores de 25 años.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

De forma predeterminada, no se selecciona ningún perfil. Se muestran sólo clics para destinatarios cuyo sexo es desconocido y para destinatarios que tienen menos de 25 años o cuya edad es desconocida.

![](assets/delivery_reports_hot-clicks_1.png)

To display clicks for women, click the **[!UICONTROL Change profile]** button and select a female test profile. Para mostrar los clics de los hombres, continúe de forma similar y seleccione un perfil de prueba masculino.

![](assets/delivery_reports_hot-clicks_2.png)

To display clicks for recipients over 25, click the **[!UICONTROL Change profile]** button and select a test profile whose birth date is matching this condition.

For more on test profiles, see [About test profiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles).

>[!NOTE]
>
>El número de clics en un vínculo específico es un porcentaje del total de clics para todo el contenido condicional de una entrega. Por lo tanto, si ha definido contenido dinámico, el total de porcentajes mostrados para un perfil de prueba específico podría no ser igual a 100.

Del mismo modo, para los envíos recurrentes y los mensajes transaccionales, puede seleccionar el perfil de prueba correspondiente al contenido dinámico que desea mostrar, pero también puede ver los porcentajes de clics según la entrega de ejecución seleccionada.

Una entrega de ejecución es un mensaje técnico no procesable y no funcional que se crea en los siguientes casos:

* Cada vez que se ejecuta o actualiza una entrega recurrente.

   Por ejemplo, si el flujo de trabajo que administra la entrega se ejecuta una vez al mes, habrá una entrega de ejecución al mes. Además, cada vez que se actualiza el contenido de la entrega, se crea una entrega adicional de ejecución.

   For more on recurring email deliveries, see [Email delivery](../../automating/using/email-delivery.md).

* De forma predeterminada, una vez al mes para los mensajes transaccionales, y cada vez que se edita y vuelve a publicar un mensaje de transacción.

   For more on transactional messages, see [About transactional messaging](../../channels/using/about-transactional-messaging.md).

>[!NOTE]
>
>Debido a que los ID de las URL rastreadas son diferentes para cada ejecución, los datos de clics dinámicos no se pueden agregar para todas las entregas de ejecución de un mensaje dado. Solo se puede mostrar para una entrega de ejecución a la vez.

Once your message is sent, select **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** from the delivery dashboard.

De forma predeterminada, se selecciona la última entrega de ejecución. Click the **[!UICONTROL Change execution delivery]** button to select another one.

![](assets/delivery_reports_hot-clicks_3.png)

Solo se muestran los porcentajes de clic para la ejecución de entrega seleccionada.
