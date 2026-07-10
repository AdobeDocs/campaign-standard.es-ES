---
title: Directrices de CNIL sobre los píxeles de seguimiento de correo electrónico
description: Obtenga información acerca de las directrices actualizadas de CNIL sobre los píxeles de seguimiento de correo electrónico y los controles de Adobe Campaign Standard que pueden apoyar sus esfuerzos de conformidad.
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1081'
ht-degree: 0%

---


# Explicación de las directrices actualizadas de CNIL sobre los píxeles de seguimiento de correo electrónico {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**En esta página:** Obtenga información acerca de la recomendación de abril de 2026 de CNIL sobre los píxeles de seguimiento de correo electrónico y descubra los controles de Adobe Campaign Standard (activación de seguimiento, seguimiento de nivel de vínculo, modelo de datos de consentimiento, mecanismos de exclusión y creación de informes) que pueden apoyar sus esfuerzos de conformidad.

>[!ENDSHADEBOX]

Esta publicación es solo con fines informativos. No es asesoramiento legal y no garantiza el cumplimiento de la ley aplicable. Las funcionalidades del producto de Adobe Campaign Standard que se describen a continuación son componentes básicos que, configurados y operados correctamente, pueden admitir una implementación compatible. Cada cliente es responsable de determinar y cumplir con sus obligaciones según la ley aplicable.

## Información general {#overview}

El 14 de abril de 2026, la *Comisión Nacional de Informática y Libertades* (CNIL), la autoridad de protección de datos de Francia, publicó una [recomendación sobre el uso de píxeles de seguimiento en correos electrónicos](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). La guía aclara cuándo se requiere el consentimiento y resalta la importancia de las prácticas de consentimiento adecuadas para el seguimiento de píxeles del correo electrónico. Esta política podría afectar a las prácticas de envío de cualquier entidad que envíe correos electrónicos a suscriptores con sede en Francia.

CNIL proporcionó a las empresas un periodo de tres meses a partir de la fecha de la recomendación para informar a sus destinatarios de correo electrónico (&quot;usuarios&quot;) de la presencia de los píxeles de seguimiento, su propósito y el derecho de los usuarios a la exclusión. Durante este período de transición, se espera que los clientes notifiquen a los usuarios el seguimiento de píxeles y proporcionen una exclusión si es necesario. Se espera que CNIL inicie sus actividades de aplicación después del 14 de julio de 2026.

A medida que la CNIL y otros reguladores aclaren las directrices sobre el seguimiento de píxeles y problemas relacionados, Adobe seguirá supervisando las actualizaciones e informando a los clientes de las funciones técnicas de los productos de Adobe que admiten el marketing por correo electrónico, incluido Adobe Campaign Standard.

Las aplicaciones de ejecución de marketing por correo electrónico de Adobe, incluidas Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign y Marketo Engage, proporcionan controles que pueden ayudar a los clientes a administrar el seguimiento abierto en el nivel de envío o de correo electrónico. Los clientes son responsables de determinar sus propias obligaciones de cumplimiento según las directrices de CNIL aplicables y otras leyes, pero estas capacidades pueden apoyar los esfuerzos de cumplimiento de los clientes.

### Qué es un píxel de seguimiento de correo electrónico {#tracking-pixel}

Un píxel de seguimiento de correo electrónico es una imagen transparente 1x1 incrustada en el HTML de un correo electrónico. Cuando el cliente de correo electrónico del destinatario carga esa imagen, el píxel hace ping a un servidor que registra datos como una marca de tiempo, un tipo de dispositivo, un cliente de correo electrónico y, a veces, una dirección IP para obtener una ubicación aproximada. A continuación, ese registro se vincula al registro de un destinatario, lo que permite a los especialistas en marketing ver si se abre un correo electrónico.

### Atención al cliente {#support}

Los clientes que busquen ayuda para implementar los cambios descritos anteriormente pueden interactuar con el ecosistema de Adobe existente. Para preguntas técnicas sobre las funcionalidades de Adobe a las que se hace referencia, póngase en contacto con el administrador de éxito del cliente o con el administrador técnico de cuentas.

## Funcionalidad de Adobe Campaign Standard relacionada con el seguimiento de correo electrónico {#acs-functionality}

Los clientes pueden utilizar los mecanismos nativos de seguimiento, esquema y personalización de Adobe Campaign Standard para abordar ciertos elementos al configurar la arquitectura.

### Clasificación de correo electrónico {#email-classification}

Amplíe la plantilla de envío con un campo personalizado que indique el tipo de correo electrónico (autenticación, solo capacidad de envío, transaccional, marketing con consentimiento, prospección B2B). En Campaign Standard, las plantillas de envío pueden llevar campos personalizados que fluyen a la lógica de los informes y del flujo de trabajo. Esta clasificación determina qué seguimiento es adecuado para cada envío.

[Aprenda a crear y utilizar plantillas de envío](../../channels/using/creating-an-email.md)

### Modelo de datos de consentimiento {#consent-data-model}

Amplíe el recurso Perfil mediante el mecanismo de recursos personalizados de Campaign Standard (**Administración > Desarrollo > Recursos personalizados**) para que lleve indicadores de consentimiento específicos, marcas de tiempo de consentimiento y la fecha de la última apertura (solo fecha — sin componente de hora). Un recurso personalizado independiente vinculado al perfil captura el registro de eventos de consentimiento de solo anexar que admite la prueba de consentimiento individual. Dado que las páginas de aterrizaje de Campaign Standard pueden escribir directamente en los campos de Perfil, el estado de consentimiento actual se puede administrar de forma nativa; el registro de consentimiento se escribe mediante la API de REST de Adobe Campaign Standard (`/profileAndServicesExt`) una vez que se envía una preferencia.

[Obtenga información sobre cómo crear o ampliar un recurso](../../developing/using/creating-or-extending-the-resource.md)

[Obtenga información sobre cómo interactuar con recursos personalizados mediante API](../../api/using/interacting-with-custom-resources.md)

### Emisión en píxeles {#pixel-emission}

Adobe Campaign Standard controla el seguimiento en el nivel de entrega a través de la opción **[!UICONTROL Activate tracking]** en las propiedades de entrega o plantilla. Esta opción está desactivada en los envíos en los que el seguimiento abierto no es legal (solo autenticación, correos electrónicos de solicitud). En el caso de los envíos en los que la emisión de píxeles por propósito sea adecuada, uno de los métodos consiste en deshabilitar el píxel insertado automáticamente estándar y utilizar bloques de contenido que contengan elementos de imagen rastreados 1×1 condicionales, uno por propósito, en los que a cada imagen se le asigna una categoría URL (`PIX_DELIV`, `PIX_PERF`, `PIX_PROFILE`, `PIX_FRAUD`) y se muestran solo cuando el indicador de consentimiento correspondiente del destinatario es verdadero.

[Obtenga información sobre cómo configurar los parámetros de seguimiento de correo electrónico](configuring-email-channel.md#tracking-parameters)

[Obtenga información sobre cómo administrar las direcciones URL rastreadas en el Designer de correo electrónico](../../designing/using/links.md#about-tracked-urls)

[Aprenda a añadir bloques de contenido](../../designing/using/personalization.md#adding-a-content-block)

### Retirada {#withdrawal}

Agregue un vínculo **Administrar preferencias de rastreador** a cada pie de página del correo electrónico, distinto del vínculo de cancelación de suscripción. El vínculo apunta a una página de aterrizaje de Campaign Standard autenticada mediante el mecanismo `recipientId` o `urlSubscription`; el destinatario alterna sus indicadores de consentimiento por propósito y los envía. En la confirmación, una pequeña llamada a la API de REST de Campaign Standard escribe el evento de retirada en el registro de consentimiento. La recomendación indica que este vínculo está exento de seguridad del requisito de seguimiento.

[Obtenga información sobre cómo configurar páginas de aterrizaje de inclusión y de exclusión](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[Obtenga información sobre cómo empezar a utilizar las páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)

### Prueba de consentimiento {#consent-proof}

Cada cambio de consentimiento (captura al registrarse, actualización desde la página de preferencias, caducidad) crea una fila en el recurso personalizado del registro de consentimiento, que incluye el código de versión de la redacción, la marca de tiempo de captura, el origen de captura y el ámbito. Este registro se puede consultar a través del explorador de Campaign Standard, exponerse a través de la API de REST y exportarse para su revisión por RPD a través de un flujo de trabajo programado.

[Obtenga información sobre cómo interactuar con recursos personalizados mediante API](../../api/using/interacting-with-custom-resources.md)

### Gobernanza de la solicitud {#re-solicitation}

Un campo personalizado `cusLastPixelRefusalDate` en el perfil, combinado con una regla de filtrado de tipología que excluye los perfiles en los que ese campo se encuentra dentro de un período de tiempo elegido, impide que se vuelva a solicitar a los destinatarios que han rechazado en ese período de tiempo. Un flujo de trabajo programado administra los intervalos de tiempo de caducidad del consentimiento de los clientes marcando los registros antiguos y escribiendo eventos de caducidad en el registro de consentimiento.

[Aprenda a trabajar con reglas de tipología](../../sending/using/about-typology-rules.md)

[Descubra cómo administrar las reglas de tipología](../../sending/using/managing-typology-rules.md)

### Creación de informes {#reporting}

Los informes dinámicos de Campaign Standard se basan en categorías de URL y dimensiones de perfil. Las categorías de URL específicas introducidas más arriba aparecen en los informes dinámicos como nuevas dimensiones, lo que permite a los operadores cortar datos abiertos y hacer clic en ellos por propósito. La distinción entre seguimiento consentido y no consentido se puede ver de forma nativa una vez que se han establecido las categorías de URL.

[Obtenga información sobre cómo empezar a usar los informes dinámicos](../../reporting/using/about-dynamic-reports.md)

[Obtenga información sobre los indicadores de seguimiento](../../reporting/using/tracking-indicators.md)
