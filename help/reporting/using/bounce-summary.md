---
solution: Campaign Standard
product: campaign
title: Resumen de devoluciones
description: Con el informe listo para usar del resumen de devoluciones, obtenga información sobre el estado de las campañas enviadas y los errores que puedan haber encontrado.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: bounceReport,main;campaignCirculationReport,main;programCirculationReport,main
translation-type: tm+mt
source-git-commit: 2bc5eae996dfa3ecdde3540f3a4f759c668e93ec
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 1%

---


# Resumen de devoluciones{#bounce-summary}

Este informe detalla los errores generales de hardware y software que se encontraron durante los envíos, así como el procesamiento automático de devoluciones (consulte [Explicación de los errores de envío](../../sending/using/understanding-delivery-failures.md)).

![](assets/campaign_reports_bounces.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar la forma en que se muestran los detalles en sus respectivas configuraciones de visualización.

**La** repartición de Flop 5 enumera los cinco envíos con el mayor número de cuarentenas:

La tabla **Motivos de devolución** contiene los datos disponibles para los tipos de errores que causaron devoluciones para cada envío:

* **[!UICONTROL User unknown]**:: Tipo de error generado cuando se envía un envío a una dirección de correo electrónico no válida.
* **[!UICONTROL Invalid domain]**:: Tipo de error generado cuando se envía un envío a una dirección de correo electrónico cuyo dominio es incorrecto o ya no existe.
* **[!UICONTROL Unreachable]**:: Tipo de error encontrado en la cadena de envío del mensaje, como dominio temporalmente inaccesible.
* **[!UICONTROL Account disabled]**:: Tipo de error generado cuando se envía un envío a una dirección de correo electrónico que ya no existe.
* **[!UICONTROL Mailbox full]**:: Tipo de error generado cuando la bandeja de entrada del destinatario está llena. Hay cinco intentos de enviar el mensaje antes de que se genere este error.
* **[!UICONTROL Not connected]**:: Tipo de error generado cuando el teléfono móvil del destinatario está apagado o no está conectado a una red en el momento en que se envía el mensaje.

   >[!NOTE]
   >
   >Este tipo de error solo afecta a envíos en canales móviles.

* **[!UICONTROL Refused]**:: Tipo de error generado cuando el proveedor de servicio de Internet (ISP) rechaza una dirección. Por ejemplo, cuando un software antispam ha aplicado una regla de seguridad.

La tabla **Repartición de dominio** muestra los problemas generales encontrados durante los envíos según el dominio de destinatario.
