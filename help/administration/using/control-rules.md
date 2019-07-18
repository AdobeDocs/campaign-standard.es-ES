---
title: Reglas de control
seo-title: Reglas de control
description: Reglas de control
seo-description: Conozca cómo reforzar la comprobación de calidad de los mensajes con reglas de control.
page-status-flag: no activado nunca
uuid: 33 a 1 c 90 c -534 e -4 fe 1-982 c-f 4 e 1858 d 4 d 2 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305 cadde -6424-4 c 6 f-b 11 b -1 e 8 bdbad 6 ef 1
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Control rules{#control-rules}

Las reglas de control permiten al usuario comprobar la validez y la calidad de los mensajes antes de enviarlos, como visualización de caracteres, tamaño de mensaje SMS, formato de dirección, etc.

Un conjunto de reglas predeterminadas disponibles en Adobe Campaign garantiza los controles estándar:

* **[!UICONTROL Check subject]** (correo electrónico): comprueba que el asunto y la dirección remitente no contienen caracteres especiales que puedan causar problemas en determinados agentes de transferencia de correo y verifique que se haya completado el asunto del mensaje.
* **[!UICONTROL Check URL labels]** (correo electrónico): comprueba que cada URL de seguimiento tenga una etiqueta.
* **[!UICONTROL Check URLs]** (correo electrónico): comprueba las URL de seguimiento (presencia del carácter " &amp;").
* **[!UICONTROL Check proof size]** (todos los canales): genera un mensaje de error si la población objetivo de prueba supera los 100 destinatarios.
* **Comprobar el vínculo de cancelación de suscripción** (correo electrónico): comprueba la presencia de al menos una URL de cancelación de suscripción (desactivación) en cada contenido (HTML y texto).
* **[!UICONTROL Check delivery size]** (todos los canales): comprueba el tamaño de los mensajes.
* **[!UICONTROL Check social network sharing link]** (correo electrónico): comprueba la presencia de un vínculo a una página reflejada al incluir un vínculo de uso compartido de redes sociales (virallinks) en el contenido.
* **[!UICONTROL A/B Test]**: extrae la población de prueba de una entrega con una prueba A/B.

Puede elegir el momento en el que la regla se aplicará desde una de las fases del ciclo de vida de la entrega. Select the value to apply in the drop-down list from the **[!UICONTROL Phase]** field of the typology rule.

![](assets/typology_phase.png)

Los valores posibles son:

* **Al principio de la segmentación**

   La regla de control se puede aplicar en esta fase para que el paso de personalización no se ejecute en caso de error.

* **Después de segmentación**

   Si necesita conocer el volumen del objetivo para aplicar la regla de control, seleccione esta fase.

   For example, the **Check proof size** control rule applies after the targeting stage: this rule prevents the preparation of message personalization if there are too many proof recipients.

* **Al principio de la personalización**

   Esta fase debe seleccionarse si la casilla de verificación trata la aprobación de personalización de mensajes. La personalización de mensajes se realiza durante la fase de análisis.

* **Al final del análisis**

   Cuando una comprobación requiera que se complete la personalización de mensaje, seleccione esta fase.

