---
title: Reglas de control
description: Aprenda a reforzar el control de calidad de sus mensajes con reglas de control.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 6461c128-1e42-4685-88f8-507244147e6f
TQID: https://experienceleague.adobe.com/lpPFofV3IPl7zmbaR4TOuyCcVqgjwI3maxr-jKzkd0Q
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 17%

---

# Reglas de control {#control-rules}

Las reglas de control permiten comprobar la validez y la calidad de los mensajes antes de enviarlos, como la visualización de caracteres, el tamaño del mensaje SMS, el formato de la dirección, etc.

>[!NOTE]
>
>Por motivos de seguridad, las reglas de control son de sólo lectura y no se pueden modificar.

## Reglas de control predeterminadas {#default-control-rules}

Un conjunto de reglas predeterminadas garantiza los controles estándar. La tabla siguiente proporciona información sobre estas reglas, así como su canal relacionado y [fases de ejecución](#control-rules-execution-phases).

| Etiqueta | Canal | Fase de ejecución | Descripción |
|---------|----------|---------|---------|
| **[!UICONTROL A/B Test]** | Correo electrónico | Al principio de la personalización | Extrae la población de prueba para una entrega con una prueba A/B. |
| **[!UICONTROL Check delivery size]** | Todos | Después de la segmentación | Comprueba el tamaño de los mensajes. |
| **[!UICONTROL Check email content is not empty]** | Correo electrónico | Después de la segmentación | Genera un error si el contenido del mensaje está vacío. |
| **[!UICONTROL Check In-App content for broadcast template]** | En la aplicación | Personalización al principio | Comprueba que los déclencheur o el contenido en la aplicación no estén vacíos para la plantilla de difusión. |
| **[!UICONTROL Check In-App content for profile template]** | En la aplicación | Al principio de la personalización | Comprueba que los déclencheur o el contenido en la aplicación no estén vacíos para la plantilla del perfil. |
| **[!UICONTROL Check In-App content for subscriber template]** | En la aplicación | Al principio de la personalización | Comprueba que los déclencheur o el contenido en la aplicación no estén vacíos para la plantilla del suscriptor. |
| **[!UICONTROL Check proof size]** | Todos | Después de la segmentación | Genera un mensaje de error si la población de destino de prueba supera los 100 destinatarios. |
| **[!UICONTROL Check social network sharing link]** | Correo electrónico | Al principio de la personalización | Comprueba la presencia de un vínculo a una página espejo cuando se incluye un vínculo de uso compartido de una red social (vínculos virales) en el contenido. |
| **[!UICONTROL Check subject]** | Correo electrónico | Al principio de la personalización | Comprueba que el asunto y la dirección del remitente no contienen caracteres especiales que puedan causar problemas en determinados agentes de transferencia de correo y comprueba que el asunto del mensaje se haya completado. |
| **[!UICONTROL Check unsubscription link]** | Correo electrónico | Al principio de la personalización | Comprueba la presencia de al menos una URL de baja (exclusión) en cada contenido (HTML y texto). |
| **[!UICONTROL Check URL labels]** | Correo electrónico | Al principio de la personalización | Comprueba que cada URL de seguimiento tiene una etiqueta. |
| **[!UICONTROL Check URLs]** | Correo electrónico | Al principio de la personalización | Comprueba las direcciones URL de seguimiento (presencia del carácter &quot;&amp;&quot;). |

## Fases de ejecución de reglas de control {#control-rules-execution-phases}

Las reglas de control se pueden aplicar en diferentes fases del ciclo de vida de la entrega:

* **Al principio del direccionamiento**: la regla de control se puede aplicar en esta fase para que el paso de personalización no se ejecute en caso de error.

* **Después del direccionamiento**: la ejecución después del direccionamiento le permite conocer el volumen del destino para aplicar la regla de control.

  Por ejemplo, la regla de control **Check proof size** se aplica después de la fase de direccionamiento: esta regla evita la preparación de la personalización del mensaje si hay demasiados destinatarios de prueba.

* **Al comienzo de la personalización**: se aplica cuando la comprobación está relacionada con la aprobación de la personalización de mensajes. La personalización del mensaje se lleva a cabo durante la fase de análisis.

* **Al final del análisis**: Cuando una comprobación requiere que se complete la personalización del mensaje.
