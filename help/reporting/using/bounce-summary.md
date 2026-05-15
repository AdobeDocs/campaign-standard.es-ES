---
title: Resumen de devoluciones
description: Con el informe Predeterminado Resumen de devoluciones, obtenga información sobre el estado de las campañas enviadas y los errores que puedan haber encontrado.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
TQID: https://experienceleague.adobe.com/ggB-q-6kJyPF4GgJJzJGtsOqg6-7MeBhEfiGVY0M7sQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: f8a45b24-4be7-4f1b-909b-60d06b483a20
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 282
ht-degree: 1%

---

# Resumen de devoluciones{#bounce-summary}

Este informe detalla los errores generales, tanto los errores graves como los leves que se han encontrado durante las entregas, así como el procesamiento automático de las devoluciones (consulte [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivos ajustes de visualización.

**Flop 5 repartition** enumera las cinco entregas con el mayor número de cuarentenas:

La tabla **Razones de rechazo** contiene los datos disponibles para los tipos de errores que causaron devoluciones en cada envío:

* **[!UICONTROL User unknown]**: tipo de error generado cuando se envía una entrega a una dirección de correo electrónico no válida.
* **[!UICONTROL Invalid domain]**: tipo de error generado cuando se envía una entrega a una dirección de correo electrónico cuyo dominio es incorrecto o ya no existe.
* **[!UICONTROL Unreachable]**: tipo de error encontrado en la cadena de entrega de mensajes, como dominio temporalmente inaccesible.
* **[!UICONTROL Account disabled]**: tipo de error generado cuando se envía una entrega a una dirección de correo electrónico que ya no existe.
* **[!UICONTROL Mailbox full]**: tipo de error generado cuando la bandeja de entrada del destinatario está llena. Hay cinco intentos de enviar el mensaje antes de que se genere este error.
* **[!UICONTROL Not connected]**: tipo de error generado cuando el teléfono móvil del destinatario está apagado o no está conectado a una red en el momento en que se envía el mensaje.

  >[!NOTE]
  >
  >Este tipo de error solo afecta a las entregas de canales móviles.

* **[!UICONTROL Refused]**: tipo de error generado cuando el proveedor de servicios Internet (ISP) rechaza una dirección. Por ejemplo, cuando un software antispam ha aplicado una regla de seguridad.

La tabla **Domain repartition** muestra los problemas generales encontrados durante las entregas según el dominio del destinatario.
