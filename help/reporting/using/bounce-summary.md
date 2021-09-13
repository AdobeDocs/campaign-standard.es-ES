---
title: Resumen de devoluciones
description: Con el informe predeterminado Resumen de devoluciones , conozca el estado de las campañas enviadas y los errores que puedan haber encontrado.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 03ea2f20-959c-497e-bd71-4e77132d712e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---

# Resumen de devoluciones{#bounce-summary}

Este informe detalla los errores generales, graves y leves que se han encontrado durante los envíos, así como el procesamiento automático de los rechazos (consulte [Comprensión de los errores de envío](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivos ajustes de visualización.

**La** repartición de Flop 5 enumera las cinco entregas con el mayor número de cuarentenas:

La tabla **Bounce reasons** contiene los datos disponibles para los tipos de errores que causaron devoluciones para cada envío:

* **[!UICONTROL User unknown]**: Tipo de error generado cuando se realiza un envío a una dirección de correo electrónico no válida.
* **[!UICONTROL Invalid domain]**: Tipo de error generado cuando se realiza un envío a una dirección de correo electrónico cuyo dominio es incorrecto o ya no existe.
* **[!UICONTROL Unreachable]**: Tipo de error encontrado en la cadena de entrega de mensajes, como un dominio temporalmente inaccesible.
* **[!UICONTROL Account disabled]**: Tipo de error generado cuando se realiza un envío a una dirección de correo electrónico que ya no existe.
* **[!UICONTROL Mailbox full]**: Tipo de error generado cuando la bandeja de entrada del destinatario está llena. Hay cinco intentos de enviar el mensaje antes de que se genere este error.
* **[!UICONTROL Not connected]**: Tipo de error generado cuando el teléfono móvil del destinatario está apagado o no está conectado a una red en el momento en que se envía el mensaje.

   >[!NOTE]
   >
   >Este tipo de error solo afecta a los envíos de canales móviles.

* **[!UICONTROL Refused]**: Tipo de error generado cuando el proveedor de servicios de Internet (ISP) rechaza una dirección. Por ejemplo, cuando el software antispam ha aplicado una regla de seguridad.

La tabla **Domain repartir** muestra los problemas generales que se han encontrado durante los envíos según el dominio del destinatario.
