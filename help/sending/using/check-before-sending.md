---
title: Comprobación antes de enviar
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Una vez que el mensaje esté listo, aprenda a realizar todas las comprobaciones necesarias antes de enviar
feature: Deliverability
role: User
level: Intermediate
exl-id: dfc5fc00-87aa-4d22-ad7c-cc0ba1ee21be
TQID: https://experienceleague.adobe.com/3qM5opRzD4u8HV5PALkfERzsLnWx1AsLuaDs8frG-Ic
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 412
ht-degree: 80%

---

# Realice todas las comprobaciones necesarias antes de enviar {#perform-all-checks}

Cuando el mensaje esté listo, asegúrese de que su contenido se muestra correctamente en todos los dispositivos y no contiene ningún error, como por ejemplo de personalización incorrecta o enlaces rotos.

Antes de enviar el mensaje, compruebe que los parámetros y la configuración se adecuan al envío.

## Por qué la validación es clave {#validation-is-key}

Antes de entregar un envío, debe asegurarse de que sus destinatarios recibirán el mensaje que realmente desea enviarlos. Para ello, debe validar el contenido del mensaje y los parámetros de envío.

Este paso le permite detectar posibles errores y corregirlos antes de enviarlos a su destinatario principal.

Los pasos para validar un envío se presentan [en esta sección](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Representación de correo electrónico {#email-rendering}

Antes de pulsar el botón **[!UICONTROL Send]**, asegúrese de que su mensaje se mostrará de una forma óptima en una gran variedad de clientes, correos y dispositivos web.

Para permitirlo, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite previsualizar el mensaje enviado en los diferentes contextos en los que se puede recibir.

**Sugerencias**:

* Puede ver el mensaje enviado en los diferentes contextos en los que se puede recibir webmail, servicio de mensajes, móvil, etc.

* Las funciones de procesamiento de correo electrónico son esenciales para identificar si las campañas de correo electrónico superan correctamente los filtros de los principales ISP (proveedores de servicios de Internet) y servicios de correo web. Estas herramientas envían una copia de un mensaje de correo electrónico a una red de bandejas de entrada de prueba, lo que le permite ver cómo se muestra el mensaje o cómo se renderiza en estos servicios. También pueden incluir informes y opciones de corrección de código que le ayudan a identificar y realizar correcciones con rapidez para mejorar la capacidad de envío.

Obtenga más información [en esta sección](../../sending/using/email-rendering.md).

## Mensajes de prueba {#proof-messages}

El envío de pruebas le permite comprobar el vínculo de no participación, la página espejo y cualquier otro vínculo, validar el mensaje, comprobar que se muestran las imágenes, detectar posibles errores, etc. También es posible que desee comprobar el diseño y el procesamiento en diferentes dispositivos.

Obtenga más información [en esta sección](../../sending/using/sending-proofs.md).

## Configuración de envíos de pruebas A/B {#a-b-testing-deliveries}

Si tiene varios contenidos para un envío de correo electrónico, puede utilizar pruebas A/B para averiguar qué versión tendrá el mayor impacto en la población objetivo.

**Sugerencias**:

* Envíe las diferentes versiones a algunos de sus destinatarios

* Seleccione el que tenga la tasa de éxito más alta y envíelo al resto de destinatarios

Obtenga más información [en esta sección](../../channels/using/designing-an-a-b-test-email.md).
