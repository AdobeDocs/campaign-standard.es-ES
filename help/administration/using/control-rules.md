---
title: Reglas de control
description: Aprenda a reforzar la comprobación de calidad de sus mensajes con reglas de control.
page-status-flag: nunca activado
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: reglas de trabajo con tipología
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Reglas de control{#control-rules}

Las reglas de control permiten al usuario comprobar la validez y calidad de los mensajes antes de enviarlos, como la visualización de caracteres, el tamaño del mensaje SMS, el formato de la dirección, etc.

Un conjunto de reglas predeterminadas disponibles en Adobe Campaign garantiza los controles estándar:

* **[!UICONTROL Check subject]** (correo electrónico): comprueba que el asunto y la dirección del remitente no contienen caracteres especiales que puedan causar problemas en determinados agentes de transferencia de correo, y comprueba que se ha completado el asunto del mensaje.
* **[!UICONTROL Check URL labels]** (correo electrónico): comprueba que cada URL de seguimiento tiene una etiqueta.
* **[!UICONTROL Check URLs]** (correo electrónico): comprueba las direcciones URL de seguimiento (presencia del carácter "&amp;").
* **[!UICONTROL Check proof size]** (todos los canales): genera un mensaje de error si la población de destino de prueba supera los 100 destinatarios.
* **Comprobar vínculo** de cancelación de suscripción (correo electrónico): comprueba la presencia de al menos una URL de cancelación de suscripción (exclusión) en cada contenido (HTML y texto).
* **[!UICONTROL Check delivery size]** (todos los canales): comprueba el tamaño de los mensajes.
* **[!UICONTROL Check social network sharing link]** (correo electrónico): comprueba la presencia de un vínculo a una página de reflejo cuando se incluye un vínculo de uso compartido de redes sociales (ViralLinks) en el contenido.
* **[!UICONTROL A/B Test]**:: extrae la población de prueba para una entrega con una prueba A/B.

Puede elegir el momento en que se aplicará la regla desde una de las fases del ciclo de vida de la entrega. Seleccione el valor que desee aplicar en la lista desplegable del **[!UICONTROL Phase]** campo de la regla de tipología.

![](assets/typology_phase.png)

Los valores posibles son:

* **Al principio del objetivo**

   La regla de control se puede aplicar en esta fase para que el paso de personalización no se ejecute en caso de error.

* **Después del objetivo**

   Si necesita conocer el volumen del destino para aplicar la regla de control, seleccione esta fase.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **Al principio de la personalización**

   Esta fase se debe seleccionar si la comprobación se refiere a la aprobación de la personalización de mensajes. La personalización del mensaje se lleva a cabo durante la fase de análisis.

* **Al final del análisis**

   Cuando una comprobación requiera que se complete la personalización de mensajes, seleccione esta fase.

>[!NOTE]
>
>Por motivos de seguridad, no se puede modificar el contenido de las reglas de control. El **[!UICONTROL Code]** campo es de sólo lectura.
