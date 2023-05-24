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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 3%

---

# Definición de texto dinámico{#defining-dynamic-text}

El texto dinámico se define del mismo modo que el contenido dinámico. Consulte la [Definición del contenido dinámico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email) sección.

>[!NOTE]
>
>Para SMS y push, solo puede definir texto dinámico. Puede definir contenido dinámico y texto en una página de aterrizaje. Si desea definir texto dinámico con la variable [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md), consulte [Definición del contenido dinámico en un correo electrónico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

Tenga en cuenta que los pares sustitutos, caracteres no incluidos en el plano multilingüe básico del conjunto de caracteres Unicode, no se pueden almacenar en 2 bytes (16 bits) y deben codificarse en 2 caracteres UTF-16. Estos caracteres incluyen algunos ideogramas CJK, la mayoría de emojis y algunos idiomas.
<br>Estos caracteres pueden provocar algunos problemas de incompatibilidad en el texto dinámico. Debe realizar pruebas sólidas antes de enviar los mensajes.


El ejemplo siguiente muestra cómo definir texto dinámico en un mensaje SMS.

1. Seleccione texto en el cuerpo del mensaje o de la página de aterrizaje.
1. Haga clic en **[!UICONTROL Enable dynamic text]**.

   ![](assets/dynamic_text_sms_1.png)

   El **[!UICONTROL Dynamic text]** La opción se muestra en la paleta. Se configura de la misma manera que el contenido dinámico.

1. Seleccione una variante.

   ![](assets/dynamic_text_sms_2.png)

1. Defina una condición para esta variante.

   ![](assets/dynamic_text_sms_4.png)

Una vez que se define una condición para al menos una variante, se muestra un marco morado alrededor del texto dinámico.

![](assets/dynamic_text_sms_3.png)
