---
solution: Campaign Standard
product: campaign
title: Reglas de control
description: Aprenda a reforzar la comprobación de calidad de sus mensajes con reglas de control.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 17%

---


# Reglas de control {#control-rules}

Las reglas de control permiten comprobar la validez y calidad de los mensajes antes de enviarlos, como la visualización de caracteres, el tamaño del mensaje SMS, el formato de la dirección, etc.

>[!NOTE]
>
>Por motivos de seguridad, las reglas de control son de solo lectura y no se pueden modificar.

## Reglas de control predeterminadas {#default-control-rules}

Un conjunto de reglas predeterminadas garantiza los controles estándar. En la tabla siguiente se proporciona información sobre estas reglas, así como sobre las fases [de canal y](#control-rules-execution-phases)ejecución relacionadas.

| Etiqueta | Canal | Fase de ejecución | Descripción |
---------|----------|---------|---------
| **[!UICONTROL A/B Test]** | Correo electrónico | At the start of personalization | Extrae la población de prueba de un envío con una prueba A/B. |
| **[!UICONTROL Check delivery size]** | Todo | After targeting | Comprueba el tamaño de los mensajes. |
| **[!UICONTROL Check email content is not empty]** | Correo electrónico | After targeting | Genera un error si el contenido del mensaje está vacío. |
| **[!UICONTROL Check In-App content for broadcast template]** | En la aplicación | Personalización de inicio | Comprueba que el contenido en la aplicación o los activadores no están vacíos para la plantilla de difusión. |
| **[!UICONTROL Check In-App content for profile template]** | En la aplicación | At the start of personalization | Comprueba que el contenido en la aplicación o los activadores no están vacíos para la plantilla de perfil. |
| **[!UICONTROL Check In-App content for subscriber template]** | En la aplicación | At the start of personalization | Comprueba que el contenido en la aplicación o los activadores no están vacíos para la plantilla de suscriptor. |
| **[!UICONTROL Check proof size]** | Todo | After targeting | Genera un mensaje de error si la población de destinatarios de prueba supera los 100 destinatarios. |
| **[!UICONTROL Check social network sharing link]** | Correo electrónico | At the start of personalization | Comprueba la presencia de un vínculo a una página espejo al incluir un vínculo de uso compartido de redes sociales (ViralLinks) en el contenido. |
| **[!UICONTROL Check subject]** | Correo electrónico | At the start of personalization | Comprueba que el asunto y la dirección del remitente no contienen caracteres especiales que puedan causar problemas en determinados agentes de transferencia de correo y comprueba que el asunto del mensaje se ha completado. |
| **[!UICONTROL Check unsubscription link]** | Correo electrónico | At the start of personalization | Comprueba la presencia de al menos una URL baja (de exclusión) en cada contenido (HTML y texto). |
| **[!UICONTROL Check URL labels]** | Correo electrónico | At the start of personalization | Comprueba que cada URL de seguimiento tiene una etiqueta. |
| **[!UICONTROL Check URLs]** | Correo electrónico | At the start of personalization | Comprueba las direcciones URL de seguimiento (presencia del carácter &quot;&amp;&quot;). |

## Fases de ejecución de reglas de control {#control-rules-execution-phases}

Las reglas de control se pueden aplicar en diferentes fases del ciclo de vida del envío:

* **En el inicio del objetivo**: La regla de control se puede aplicar en esta fase para que el paso de personalización no se ejecute en el evento de un error.

* **Después del objetivo**: La ejecución después del establecimiento de objetivos permite conocer el volumen del destinatario para aplicar la regla de control.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **En el inicio de la personalización**: Se aplica cuando la comprobación se refiere a la aprobación de la personalización de mensajes. La personalización del mensaje se lleva a cabo durante la fase de análisis.

* **At the end of the analysis**:: Cuando una comprobación requiere que se complete la personalización del mensaje.
