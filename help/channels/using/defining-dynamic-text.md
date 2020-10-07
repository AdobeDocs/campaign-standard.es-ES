---
title: Definición de texto dinámico
description: Descubra cómo mostrar distintos textos de forma dinámica al usuario según las condiciones definidas en Adobe Campaign.
page-status-flag: never-activated
uuid: bbcd200c-4fb4-467b-ba39-09b8bee9bcaa
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: defining-conditional-content
discoiquuid: 6bb6cee3-5674-4113-8073-5a9572b3e830
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---


# Definición de texto dinámico{#defining-dynamic-text}

El texto dinámico se define del mismo modo que el contenido dinámico. Consulte la sección [Definición de contenido](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) dinámico.

>[!NOTE]
>
>Para SMS y push, solo puede definir texto dinámico. Puede definir contenido dinámico y texto en una página de aterrizaje. Si desea definir texto dinámico con el Diseñador [de](../../designing/using/designing-content-in-adobe-campaign.md)correo electrónico, consulte [Definición de contenido dinámico en un mensaje de correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Tenga en cuenta que los pares sustitutos, los caracteres no incluidos en el plano multilingüe básico del conjunto de caracteres Unicode, no se pueden almacenar en 2 bytes (16 bits) y deben codificarse en 2 caracteres UTF-16. Estos caracteres incluyen algunos ideogramas CJK, la mayoría de los emojis y algunos idiomas.
<br>Estos caracteres pueden provocar algunos problemas de incompatibilidad en el texto dinámico. Debe realizar pruebas sólidas antes de enviar los mensajes.


El ejemplo siguiente muestra cómo definir texto dinámico en un mensaje SMS.

1. Seleccione texto en el cuerpo del mensaje o la página de aterrizaje.
1. Haga clic en **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   La **[!UICONTROL Dynamic text]** opción se muestra en la paleta. Se configura de la misma manera que el contenido dinámico.

1. Seleccione una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina una condición para esta variante.

   ![](assets/dynamic_text_sms_4.png)

Una vez definida una condición para al menos una variante, se muestra un marco púrpura alrededor del texto dinámico.

![](assets/dynamic_text_sms_3.png)
