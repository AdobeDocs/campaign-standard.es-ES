---
title: Definición de texto dinámico
description: Aprenda a mostrar diferentes textos de forma dinámica al usuario según las condiciones definidas en Adobe Campaign.
audience: designing
content-type: reference
topic-tags: defining-conditional-content
feature: SMS
role: User
level: Beginner
exl-id: 649e3428-a3bf-470f-923c-04d9a57a208f
TQID: 'https://experienceleague.adobe.com/fgQySs0BUlvKT3CKMSaW-0fVe3W65qV1fDEZb1kDZ3w'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%
---
# Definición de texto dinámico{#defining-dynamic-text}

El texto dinámico se define del mismo modo que el contenido dinámico. Consulte la sección [Definición de contenido dinámico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

>[!NOTE]
>
>Para SMS y push, solo puede definir texto dinámico. Puede definir contenido dinámico y texto en una página de aterrizaje. Si desea definir texto dinámico con [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), consulte [Definición de contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Tenga en cuenta que los pares sustitutos, caracteres no incluidos en el plano multilingüe básico del conjunto de caracteres Unicode, no se pueden almacenar en 2 bytes (16 bits) y deben codificarse en 2 caracteres UTF-16. Estos caracteres incluyen algunos ideogramas CJK, la mayoría de emojis y algunos idiomas.
<br>Estos caracteres pueden causar algunos problemas de incompatibilidad en el texto dinámico. Debe realizar pruebas sólidas antes de enviar los mensajes.


El ejemplo siguiente muestra cómo definir texto dinámico en un mensaje SMS.

1. Seleccione texto en el cuerpo del mensaje o de la página de aterrizaje.
1. Haga clic en **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   La opción **[!UICONTROL Dynamic text]** se muestra en la paleta. Se configura de la misma manera que el contenido dinámico.

1. Seleccione una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina una condición para esta variante.

   ![](assets/dynamic_text_sms_4.png)

Una vez que se define una condición para al menos una variante, se muestra un marco morado alrededor del texto dinámico.

![](assets/dynamic_text_sms_3.png)
