---
title: Comprobación antes de enviar
seo-title: Comprobación antes de enviar
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/CLASSIC
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b80197491b45cff46273e1a41e3dfb7a939f96c5
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 93%

---


# Realice todas las comprobaciones necesarias antes de enviar {#perform-all-checks}

Cuando el mensaje esté listo, asegúrese de que su contenido se muestra correctamente en todos los dispositivos y no contiene ningún error, como por ejemplo de personalización incorrecta o enlaces rotos.

Antes de enviar el mensaje, compruebe que los parámetros y la configuración se adecuan al envío.

## Por qué la validación es clave {#validation-is-key}

Antes de entregar un envío, debe asegurarse de que sus destinatarios recibirán el mensaje que realmente desea enviarlos. Para ello, debe validar el contenido del mensaje y los parámetros de envío.

Este paso le permite detectar posibles errores y corregirlos antes de enviarlos a su destinatario principal.

Los pasos para validar un envío se presentan [en esta sección](../../sending/using/get-started-sending-messages.md#prepare-test-send).

## Procesamiento de correo electrónico {#email-rendering}

Antes de pulsar el botón **[!UICONTROL Send]**, asegúrese de que su mensaje se mostrará de una forma óptima en una gran variedad de clientes, correos y dispositivos web.

Para permitirlo, Adobe Campaign captura el procesamiento y lo pone a disposición en un informe dedicado. Esto le permite previsualizar el mensaje enviado en los diferentes contextos en los que se puede recibir.

**Sugerencias**:

* Puede ver el mensaje enviado en los diferentes contextos en los que se puede recibir webmail, servicio de mensajes, móvil, etc.

* Las funciones de procesamiento de correo electrónico son cruciales para identificar si sus campañas de correo electrónico superan con éxito los filtros de los principales ISP (Proveedores de servicio de Internet) y servicios de correo web. Estas herramientas envían una copia de un mensaje de correo electrónico a una red de bandejas de entrada de prueba, lo que le permite ver cómo se muestra el mensaje o cómo se renderiza en estos servicios. También pueden incluir informes y opciones de corrección de código que le ayudan a identificar y realizar correcciones con rapidez para mejorar la capacidad de envío.

Obtenga más información [en esta sección](../../sending/using/email-rendering.md).

## Mensajes de prueba {#proof-messages}

El envío de pruebas le permite comprobar el vínculo de no participación, la página espejo y cualquier otro vínculo, validar el mensaje, comprobar que se muestran las imágenes, detectar posibles errores, etc. También es posible que desee comprobar el diseño y el procesamiento en distintos dispositivos.

Obtenga más información [en esta sección](../../sending/using/sending-proofs.md).

## Configuración de envíos de pruebas A/B {#a-b-testing-deliveries}

Si tiene varios contenidos para un envío de correo electrónico, puede utilizar pruebas A/B para averiguar qué versión tendrá el mayor impacto en la población objetivo.

**Sugerencias**:

* Envíe las diferentes versiones a algunos de sus destinatarios

* Seleccione el que tenga la tasa de éxito más alta y envíelo al resto de destinatarios

Obtenga más información [en esta sección](../../channels/using/designing-an-a-b-test-email.md).

