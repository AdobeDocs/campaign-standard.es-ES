---
title: Optimización del envío de mensajes
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Aprenda a proteger y optimizar el proceso de envío de forma ascendente.
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '746'
ht-degree: 85%

---

# Optimización de las entregas {#optimize-delivery}

Antes de empezar a crear envíos, puede realizar varias acciones para proteger y optimizar el proceso de envío de forma ascendente.

En la siguiente sección se describen las prácticas recomendadas y los procedimientos recomendados para una configuración óptima de Adobe Campaign. Si sigue estas prácticas, se minimizarán los problemas que podría tener que afrontar en la fase posterior.

## Rendimiento de la plataforma

Varios factores pueden afectar directamente al rendimiento del servidor y ralentizar la plataforma:

* Número y tipo de elementos de personalización: la personalización en correos electrónicos extrae datos de la base de datos para cada destinatario. Si hay muchos elementos de personalización, esto aumenta la cantidad de datos necesarios para preparar la entrega.  Obtenga más información acerca de la personalización de correo electrónico en [esta sección](../../designing/using/personalization.md)

* Carga del servidor: cuando Campaign gestiona muchas tareas diferentes al mismo tiempo, puede ralentizar el rendimiento. El servidor de debe coordinar todos los datos entrantes y salientes de todos los envíos para garantizar que los datos sean correctos y oportunos.

  **SUGERENCIA:** Para evitar esto, coordine la programación de las envíos con los demás miembros de su equipo para garantizar el mejor rendimiento.

* El [ejecución de flujo de trabajo](../../automating/using/about-workflow-execution.md): la monitorización de los flujos de trabajo es esencial para evitar problemas de rendimiento de la plataforma. Siga las directrices enumeradas [en esta página](../../automating/using/monitoring-workflow-execution.md). Obtenga más información en la [prácticas recomendadas de flujo de trabajo](../../automating/using/best-practices-workflows.md) sección.

* Puede aprovechar [Funcionalidades del Panel de control de Campaign de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=es) para supervisar su plataforma, utilizando [supervisión del rendimiento](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=es) funcionalidades.

## Comprobación de la configuración de red {#network-config}

Para optimizar el envío al administrar correos electrónicos en grandes volúmenes y evitar que se confunda con spam, asegúrese de tener una configuración de red legítima que no intente ocultar la identidad del servidor.

**Sugerencia**: Utilice una dirección de remitente transparente correspondiente al sitio web de la marca. Por ejemplo, la compañía TravelAgency gestiona la cadena hotelera Valentino. Dispone de su propio dominio valentino.com para su sitio web. Para promocionar el hotel Valentino en París, utiliza el subdominio paris.valentino.com. Por lo tanto, una dirección de remitente relevante puede ser hotel@paris.valentino.com.

## Administración de la capacidad de entrega {#deliverability-management}

Para llegar a la bandeja de entrada de sus destinatarios sin rebotar ni ser marcado como correo no deseado, debe mejorar la capacidad de envío de sus mensajes.

* ¿Qué es la capacidad de envío?

   * Hace referencia a los factores de un mensaje de correo electrónico que determinan su capacidad para ser aceptado por el servidor de un destinatario. Los ISP (proveedores de servicios de Internet) filtran los correos electrónicos que se identifican como SPAM o bloquean la descarga de imágenes. Si determinan que cierto dominio está enviando demasiados correos electrónicos, establecerán un límite en el número de correos electrónicos que aceptarán de ese remitente.

   * Al comprobar la tasa de envíos de sus correos electrónicos, debe centrarse en cuatro categorías principales: calidad de los datos, mensaje y contenido, infraestructuras de envío y reputación. Para profundizar en este tema, consulte [esta sección](../../sending/using/about-deliverability.md).

* Al iniciar una nueva plataforma, aplique las recomendaciones detalladas en [esta página](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html#transition-process).

* Póngase en contacto con su representante de Adobe para obtener ayuda.

## Administración de cuarentena {#quarantine-management}

Le conviene mantener buenos procesos de gestión de cuarentenas.

Al comenzar a enviar correos electrónicos en una nueva plataforma, puede utilizar una lista de direcciones que no esté totalmente confirmada. Si realiza envíos a direcciones no válidas o a direcciones honeypot (bandejas de entrada creadas únicamente para engañar a remitentes de correo electrónico no deseado), la reputación de su plataforma comenzará a reducirse. Unos procesos de administración de cuarentena adecuados ayudan a mantener la calidad de la dirección, evitar la lista de bloqueados de los proveedores de acceso a internet, y reducir la tasa de errores para acelerar los envíos y el rendimiento.

**Sugerencias**

* Los destinatarios cuyas direcciones están en cuarentena se excluyen de forma predeterminada durante el análisis de envío: no están segmentados. Esto acelera las entregas, ya que la tasa de error afecta significativamente a la velocidad de entrega. Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando el buzón está lleno o si la dirección no existe. [Más información](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Adobe Campaign administra las direcciones erróneas según el tipo de error devuelto. Para obtener más información, consulte [esta sección](../../sending/using/understanding-quarantine-management.md).

* Algunos proveedores de acceso a Internet consideran automáticamente los correos electrónicos como no deseados si la tasa de direcciones no válidas es demasiado alta. Por lo tanto, la cuarentena le permite evitar ser incluido en la lista de bloqueados de bloqueados por estos proveedores.

* Además, la gestión de cuarentenas ayuda a reducir el coste de envío de SMS mediante la exclusión en los envíos de los números de teléfono incorrectos.

## Mecanismo de inclusión doble {#double-opt-in}

Para evitar el envío de mensajes a direcciones no válidas, limitar las comunicaciones incorrectas y mejorar la reputación del remitente, Adobe recomienda implementar un mecanismo de inclusión doble para la confirmación posterior a la suscripción. Esto ayuda a garantizar la suscripción intencionada de un destinatario.

Los detalles para la implementación de este mecanismo se describen en [esta sección](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Obtenga más información en [Introducción a perfiles y audiencias](../../audiences/using/get-started-profiles-and-audiences.md).
