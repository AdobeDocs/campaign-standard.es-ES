---
title: Clics activos
description: Con los clics directos en el informe listo para usar, conozca dónde hizo clic el cliente en el envío.
page-status-flag: never-activated
uuid: 7ed49dd3-d7ee-466a-9a7b-d2aa16961667
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: ecbc1ade-63d9-4ac2-9828-380a1aa95094
context-tags: deliveryHotClicksReport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1efcd646f4af86175b3b09b53185c792cb4cf7dd
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# Clics activos{#hot-clicks}

Se puede acceder a este informe desde el **[!UICONTROL Reports]** botón de cada envío o mensaje transaccional.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta el contenido del mensaje (HTML y/o texto) con el porcentaje de clics en cada vínculo.

![](assets/delivery_reports_10.png)

Si ha creado contenido dinámico para el envío, puede realizar la vista de los porcentajes de cada condición que haya definido. Para obtener más información sobre la inserción de contenido condicional en un envío, consulte [Definición de contenido](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)dinámico.

Por ejemplo, imagine que ha creado un envío con las siguientes condiciones:

* El vínculo de la imagen principal es diferente si el destinatario es un hombre o una mujer.
* También ha agregado un vínculo a una oferta especial que solo es visible para destinatarios mayores de 25 años.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, no hay ningún perfil seleccionado. Solo se muestran los clics para destinatarios cuyo sexo es desconocido y para destinatarios menores de 25 años o cuya edad se desconoce.

![](assets/delivery_reports_hot-clicks_1.png)

Para mostrar clics para mujeres, haga clic en el **[!UICONTROL Change profile]** botón y seleccione un perfil de prueba femenino. Para mostrar clics para hombres, proceda de manera similar y seleccione un perfil de prueba masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para mostrar los clics de destinatarios mayores de 25 años, haga clic en el **[!UICONTROL Change profile]** botón y seleccione un perfil de prueba cuya fecha de nacimiento coincida con esta condición.

Para obtener más información sobre los perfiles de prueba, consulte [Acerca de los perfiles](../../audiences/using/managing-test-profiles.md)de prueba.

>[!NOTE]
>
>El número de clics en un vínculo específico es un porcentaje del total de clics para todo el contenido condicional de un envío. Por lo tanto, si ha definido contenido dinámico, el total de los porcentajes mostrados para un perfil de prueba específico puede no ser igual a 100.

Del mismo modo, para envíos y mensajes transaccionales recurrentes, puede seleccionar el perfil de prueba correspondiente al contenido dinámico que desea mostrar, pero también puede vista de los porcentajes de clics según el envío de ejecución seleccionado.

Un envío de ejecución es un mensaje técnico no procesable y no funcional que se crea en los siguientes casos:

* Cada vez que se ejecuta o actualiza un envío recurrente.

   Por ejemplo, si el flujo de trabajo que administra este envío se ejecuta una vez al mes, habrá un envío de ejecución por mes. Además, cada vez que se actualiza el contenido del envío, se crea un envío de ejecución adicional.

   Para obtener más información sobre envíos recurrentes de correo electrónico, consulte envío [de correo electrónico](../../automating/using/email-delivery.md).

* De forma predeterminada, una vez al mes para mensajes transaccionales y cada vez que se edita y publica un mensaje transaccional de nuevo.

   Para obtener más información sobre mensajes transaccionales, consulte [Acerca de los mensajes](../../channels/using/getting-started-with-transactional-msg.md)transaccionales.

>[!NOTE]
>
>Dado que los ID de las direcciones URL rastreadas son diferentes para cada ejecución, los datos de clics interactivos no se pueden agregar para todos los envíos de ejecución de un mensaje determinado. Solo se puede mostrar para un envío de ejecución a la vez.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, se selecciona el último envío de ejecución. Haga clic en el **[!UICONTROL Change execution delivery]** botón para seleccionar otro.

![](assets/delivery_reports_hot-clicks_3.png)

Solo se muestran los porcentajes de clics correspondientes a la ejecución del envío seleccionado.
