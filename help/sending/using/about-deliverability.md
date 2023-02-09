---
title: Acerca de la capacidad de envío en Adobe Campaign Standard
description: Obtenga información sobre los conceptos y las prácticas recomendadas relacionadas con la capacidad de envío, así como las herramientas que ofrece Adobe Campaign Standard para optimizar la entrega de contenido.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 77%

---

# ¿Qué es la capacidad de entrega?{#about-deliverability}

La capacidad de entrega permite medir el éxito de las campañas que llegan a la bandeja de entrada de los destinatarios sin rebotar o marcadas como correo no deseado. [Descubra por qué la capacidad de entrega es importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=es#why-deliverability-matters).

Más concretamente, la capacidad de entrega de correo electrónico hace referencia al conjunto de características que determinan la capacidad de un mensaje para llegar a su destino a través de una dirección de correo electrónico personal, en poco tiempo y con la calidad esperada en términos de contenido y formato. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Para profundizar en lo que es la capacidad de entrega y obtener más información sobre los términos, conceptos y enfoques clave de la capacidad de entrega, consulte la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es).

## Cómo mejorar la capacidad de entrega {#deliverability-key-points}

Los problemas de entrega suelen estar vinculados a medidas de protección contra spam implementadas por los proveedores de servicios de Internet y los administradores de servidores de correo.

* Para obtener recomendaciones generales sobre cómo diseñar campañas de marketing por correo electrónico exitosas, consulte [Estrategia y definición de capacidad de entrega](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=es).

* Para obtener recomendaciones más específicas sobre cómo optimizar la entrega de los correos electrónicos de Adobe Campaign, recomendamos utilizar las prácticas recomendadas que se enumeran en esta sección.

>[!NOTE]
>
>Debido a que los proveedores de servicios de Internet están obligados a desarrollar continuamente nuevas técnicas sofisticadas de filtrado para proteger a sus clientes de los remitentes de spam, la capacidad de envío del correo electrónico se caracteriza por criterios y reglas que cambian constantemente. Asegúrese de consultar la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es), que se actualiza regularmente.

### Tasa de entrega

La tasa de entrega es el número de mensajes que llegan a las bandejas de entrada de los destinatarios en comparación con el número de mensajes que se entregaron. Para mejorar la capacidad de entrega, puede aumentar esta tasa.

Con Adobe Campaign, la tasa de entrega depende de numerosos factores, especialmente:

* Configuración correcta de las instancias: póngase en contacto con su representante de Adobe para obtener ayuda.
* Configuración de red legítima: consulte [esta sección](../../sending/using/optimize-delivery.md#network-config) y [Configuración y estrategia del dominio](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#domain-setup-and-strategy).
* Su reputación de dirección IP: consulte [Estrategia de IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#ip-strategy).
* Calidad de las direcciones objetivo: consulte [Administración de cuarentena](../../sending/using/optimize-delivery.md#quarantine-management).
* Tasas de [quejas](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=es) y [rechazos](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=es#hard-bounces) bajas.
* El contenido del mensaje: consulte [Control del contenido del correo electrónico](../../sending/using/control-email-content.md).
* Autenticación de mensajes (SPF, DKIM, DMARC): consulte [esta sección](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#authentication).
* Reputación del remitente: para conocer cómo evalúan los principales ISP la reputación de un remitente, consulte [esta sección](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html?lang=es).

## Herramientas de entrega de campañas {#deliverability-tools}

Adobe Campaign proporciona una serie de herramientas para rastrear y mejorar el rendimiento de envío de su plataforma. Esta página también resalta los principios generales que debe tener en cuenta para optimizar la capacidad de envío al utilizar Campaign.

### Cree su mensaje de forma considerada

Al configurar, diseñar y probar el mensaje, asegúrese de seguir las prácticas recomendadas que se mencionan en las secciones a continuación. El uso de todas las funciones que proporciona Adobe Campaign le ayuda a mejorar la capacidad de envío.

* [Prácticas recomendadas de entregas](../../sending/using/delivery-best-practices.md)
* [Control del contenido del correo electrónico](../../sending/using/control-email-content.md)
* [Vista previa de mensajes](../../sending/using/previewing-messages.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)

### Verificación del consentimiento mediante la doble inclusión {#double-opt-in}

Para evitar el envío de mensajes a direcciones no válidas, limitar las comunicaciones incorrectas y mejorar la reputación del remitente, Adobe recomienda implementar un mecanismo de inclusión doble. Esto le permite garantizar que sus destinatarios se hayan suscrito intencionadamente.

Para obtener más información, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Para obtener más información sobre las prácticas recomendadas al recopilar datos de sus clientes, consulte la [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html?lang=es#data-quality-and-hygiene).

### Mejora de la administración de cuarentena

Adobe Campaign administra una lista que recopila quejas por correo no deseado, rechazos graves y rechazos leves que se producen de forma consistente.

Para proteger la capacidad de entrega, los destinatarios cuyas direcciones están en esa lista se excluyen de forma predeterminada de todas las entregas futuras, ya que la entrega a estos contactos podría dañar su reputación de entrega.

Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como no deseados si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser incluido en la lista de bloqueados de bloqueados por estos proveedores.

Para obtener más información, consulte las siguientes secciones:

* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Cuarentena frente a lista de bloqueados](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Uso de herramientas de supervisión y creación de informes

Utilice las funciones que ofrece Adobe Campaign para monitorizar su capacidad de entrega.

Adobe Campaign le permite comprobar el rendimiento de sus envíos a través de un conjunto de indicadores integrados en tiempo real. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->También puede crear informes totalmente personalizables y en tiempo real para obtener una mejor perspectiva de los envíos.

Para obtener más información, consulte las siguientes secciones:

* [Supervisión de la capacidad de entrega](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Recepción de alertas cuando se produzcan errores](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Informes dinámicos](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
