---
title: Resumen de devoluciones
description: Con el informe listo para usar del resumen de devoluciones, conozca el estado de las campañas enviadas y los errores que puedan haber encontrado.
page-status-flag: nunca activado
uuid: 90087311-4236-4df9-ae7d-4a15c00c70ab
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: informes
content-type: referencia
topic-tags: lista de informes
discoiquuid: 5ae561b4-03cf-4541-87ff-47f1027d53b8
context-tags: bounceReport,principal;campaignCirculationReport,principal;programCirculationReport,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Resumen de devoluciones{#bounce-summary}

Este informe detalla los errores generales de hardware y software encontrados durante las entregas, así como el procesamiento automático de las devoluciones.

![](assets/campaign_reports_bounces.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar la forma en que se muestran los detalles en sus respectivas configuraciones de visualización.

**La repartición** Flop 5 enumera las cinco entregas con el mayor número de cuarentena:

La tabla **de motivos** de devolución contiene los datos disponibles para los tipos de errores que causaron devoluciones para cada entrega:

* **[!UICONTROL User unknown]**:: Tipo de error generado cuando se envía una entrega a una dirección de correo electrónico no válida.
* **[!UICONTROL Invalid domain]**:: Tipo de error generado cuando se envía una entrega a una dirección de correo electrónico cuyo dominio es incorrecto o ya no existe.
* **[!UICONTROL Unreachable]**:: Tipo de error encontrado en la cadena de envío del mensaje. Por ejemplo: incidente de retransmisión SMTP, dominio temporalmente inaccesible, etc.
* **[!UICONTROL Account disabled]**:: Tipo de error generado cuando se envía una entrega a una dirección de correo electrónico que ya no existe.
* **[!UICONTROL Mailbox full]**:: Tipo de error generado cuando la bandeja de entrada del destinatario está llena. Hay cinco intentos de enviar el mensaje antes de que se genere este error.
* **[!UICONTROL Not connected]**:: Tipo de error generado cuando el teléfono móvil del destinatario está apagado o no está conectado a una red en el momento en que se envía el mensaje.

   >[!NOTE]
   >
   >Este tipo de error solo afecta a entregas en canales móviles.

* **[!UICONTROL Refused]**:: Tipo de error generado cuando el proveedor de servicios de Internet (ISP) rechaza una dirección. Por ejemplo, cuando un software antispam ha aplicado una regla de seguridad.

La tabla **de partición** de dominio muestra los problemas generales que se han encontrado durante las entregas según el dominio del destinatario.
