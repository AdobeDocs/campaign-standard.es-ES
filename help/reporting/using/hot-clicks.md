---
title: Clics activos
description: Con el informe listo para usar de Clics activos, descubra dónde hizo clic su cliente en su envío.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryHotClicksReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 5af37156-e93b-4ae9-9856-053364f211ef
TQID: 'https://experienceleague.adobe.com/YOdwQfIEEENsn3ZkEYqNOLPgZqlWB7dyzty7z9FYr4g'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%
---
# Clics activos{#hot-clicks}

>[!IMPORTANT]
>
>El informe de clics activos muestra exclusivamente la versión de HTML del correo electrónico y no admite la versión de texto.

Se puede acceder a este informe desde el botón **[!UICONTROL Reports]** en cada envío o mensaje transaccional.

![](assets/delivery_reports_hot-clicks_4.png)

Presenta el contenido del mensaje con el porcentaje de clics en cada vínculo.

![](assets/delivery_reports_10.png)

Si ha creado contenido dinámico para su envío, puede ver los porcentajes de cada condición que ha definido. Para obtener más información sobre la inserción de contenido condicional en una entrega, consulte [Definición de contenido dinámico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Por ejemplo, imaginemos que ha creado una entrega con las siguientes condiciones:

* El vínculo de la imagen principal es diferente si el destinatario es un hombre o una mujer.
* También ha agregado un vínculo a una oferta especial que solo es visible para los destinatarios mayores de 25 años.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, no se selecciona ningún perfil. Solo se muestran los clics de los destinatarios cuyo sexo es desconocido y de los destinatarios menores de 25 años o cuya edad es desconocida.

![](assets/delivery_reports_hot-clicks_1.png)

Para mostrar los clics de las mujeres, haga clic en el botón **[!UICONTROL Change profile]** y seleccione un perfil de prueba femenino. Para mostrar los clics de los hombres, continúe de forma similar y seleccione un perfil de prueba masculino.

![](assets/delivery_reports_hot-clicks_2.png)

Para mostrar los clics de los destinatarios mayores de 25 años, haga clic en el botón **[!UICONTROL Change profile]** y seleccione un perfil de prueba cuya fecha de nacimiento coincida con esta condición.

Para obtener más información sobre los perfiles de prueba, consulte [Acerca de los perfiles de prueba](../../audiences/using/managing-test-profiles.md).

>[!NOTE]
>
>El número de clics en un vínculo específico es un porcentaje del total de clics para todo el contenido condicional de una entrega. Por lo tanto, si ha definido contenido dinámico, el total de los porcentajes mostrados para un perfil de prueba específico puede no ser igual a 100.

Del mismo modo, para los envíos recurrentes y los mensajes transaccionales, puede seleccionar el perfil de prueba correspondiente al contenido dinámico que desea mostrar, pero también puede ver los porcentajes de clics según el envío de ejecución seleccionado.

Un envío de ejecución es un mensaje técnico no procesable y no funcional que se crea en los siguientes casos:

* Cada vez que se ejecuta o actualiza un envío recurrente.

  Por ejemplo, si el flujo de trabajo que administra este envío se ejecuta una vez al mes, habrá un envío de ejecución al mes. Además, cada vez que se actualiza el contenido del envío, se crea un envío de ejecución adicional.

  Para obtener más información sobre los envíos recurrentes de correo electrónico, consulte [Envío de correo electrónico](../../automating/using/email-delivery.md).

* De forma predeterminada, una vez al mes para los mensajes transaccionales y cada vez que se edita y vuelve a publicarse un mensaje transaccional.

  Para obtener más información sobre los mensajes transaccionales, consulte [Introducción a la mensajería transaccional](../../channels/using/getting-started-with-transactional-msg.md).

>[!NOTE]
>
>Dado que los ID de las direcciones URL rastreadas son diferentes para cada ejecución, los datos de clics activos no se pueden acumular para todas las entregas de ejecución de un mensaje determinado. Solo se puede mostrar para un envío de ejecución a la vez.

Una vez enviado el mensaje, seleccione **[!UICONTROL Reports]** > **[!UICONTROL Hot clicks]** en el panel de envío.

De forma predeterminada, se selecciona la última entrega de ejecución. Haga clic en el botón **[!UICONTROL Change execution delivery]** para seleccionar otro.

![](assets/delivery_reports_hot-clicks_3.png)

Solo se muestran los porcentajes de clics de la ejecución de entrega seleccionada.
