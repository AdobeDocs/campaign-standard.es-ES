---
title: Clics activos
seo-title: Clics activos
description: Clics activos
seo-description: Con los clics directos en el informe listo para usar, descubra dónde hizo clic el cliente en la entrega.
page-status-flag: nunca activado
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: informes
content-type: referencia
topic-tags: lista de informes
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 159c33639ab7b53558dac2ce183c3801c15ccb0f

---


# Clics activos{#hot-clicks}

Se puede acceder a este informe desde el **[!UICONTROL Reports]** botón de cada envío o mensaje transaccional.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta el contenido del mensaje (HTML o texto) con el porcentaje de clics en cada vínculo.

![](assets/delivery_reports_10.png)

Si ha creado contenido dinámico para la entrega, puede ver los porcentajes de cada condición que haya definido. Para obtener más información sobre la inserción de contenido condicional en una entrega, consulte [Definición de contenido](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)dinámico.

Por ejemplo, imagine que ha creado una entrega con las siguientes condiciones:

* El vínculo de la imagen principal es diferente si el destinatario es un hombre o una mujer.
* También ha agregado un vínculo a una oferta especial que solo es visible para los destinatarios mayores de 25 años.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, no hay ningún perfil seleccionado. Solo se muestran los clics para los destinatarios cuyo sexo es desconocido y para los destinatarios menores de 25 años o cuya edad se desconoce.

![](assets/delivery_reports_hot-clicks_1.png)

Para mostrar clics para mujeres, haga clic en el **[!UICONTROL Change profile]** botón y seleccione un perfil de prueba femenino. Para mostrar clics para hombres, proceda de manera similar y seleccione un perfil de prueba masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para mostrar los clics de los destinatarios mayores de 25 años, haga clic en el **[!UICONTROL Change profile]** botón y seleccione un perfil de prueba cuya fecha de nacimiento coincida con esta condición.

Para obtener más información sobre los perfiles de prueba, consulte [Acerca de los perfiles](../../sending/using/managing-test-profiles-and-sending-proofs.md#about-test-profiles)de prueba.

>[!NOTE]
>
>El número de clics en un vínculo específico es un porcentaje del total de clics para todo el contenido condicional de una entrega. Por lo tanto, si ha definido contenido dinámico, el total de los porcentajes mostrados para un perfil de prueba específico puede no ser igual a 100.

Del mismo modo, para envíos recurrentes y mensajes transaccionales, puede seleccionar el perfil de prueba correspondiente al contenido dinámico que desea mostrar, pero también puede ver los porcentajes de clics según la entrega de ejecución seleccionada.

Una entrega de ejecución es un mensaje técnico no procesable y no funcional que se crea en los siguientes casos:

* Cada vez que se ejecuta o actualiza una entrega recurrente.

   Por ejemplo, si el flujo de trabajo que administra esta entrega se ejecuta una vez al mes, habrá una entrega de ejecución por mes. Además, cada vez que se actualiza el contenido de la entrega, se crea una entrega de ejecución adicional.

   Para obtener más información sobre los envíos recurrentes por correo electrónico, consulte Envío [por correo electrónico](../../automating/using/email-delivery.md).

* De forma predeterminada, una vez al mes para los mensajes transaccionales y cada vez que se edita y publica un mensaje transaccional de nuevo.

   Para obtener más información sobre los mensajes transaccionales, consulte [Acerca de los mensajes](../../channels/using/about-transactional-messaging.md)transaccionales.

>[!NOTE]
>
>Dado que los ID de las direcciones URL rastreadas son diferentes para cada ejecución, los datos de clics interactivos no se pueden agregar para todas las entregas de ejecución de un mensaje determinado. Solo se puede mostrar para una entrega de ejecución a la vez.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** &gt; **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, se selecciona la última entrega de ejecución. Haga clic en el **[!UICONTROL Change execution delivery]** botón para seleccionar otro.

![](assets/delivery_reports_hot-clicks_3.png)

Solo se muestran los porcentajes de clics para la ejecución de entrega seleccionada.
