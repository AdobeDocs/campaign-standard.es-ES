---
title: Resumen de devoluciones
seo-title: Resumen de devoluciones
description: Resumen de devoluciones
seo-description: Con el informe desplegable Resumen de devoluciones, obtenga información sobre el estado de las campañas enviadas y los errores que pueden haber encontrado.
page-status-flag: no activado nunca
uuid: 90087311-4236-4 df 9-ae 7 d -4 a 15 c 00 c 70 ab
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: lista de informes
discoiquuid: 5 ae 561 b 4-03 cf -4541-87 ff -47 f 1027 d 53 b 8
context-tags: Bouncereport, main; Campaigncirculationreport, main; Programissuationreport, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 77b0933bcd004cedc6a58f80717a4284b284e0cd

---


# Bounce summary{#bounce-summary}

Este informe detalla los errores generales y duros que se encontraron durante los envíos, así como el procesamiento automático de devoluciones.

![](assets/campaign_reports_bounces.png)

Cada tabla está representada por números de resumen y gráficos. Puede cambiar cómo se muestran los detalles en sus respectivas configuraciones de visualización.

**La repartición** de Flop 5 enumera los cinco envíos con el número más alto de ubicaciones:

The **Bounce reasons** table contains the available data for the types of errors that caused bounces for each delivery:

* **[!UICONTROL User unknown]**: El tipo de error generado cuando se envía una entrega a una dirección de correo electrónico no válida.
* **[!UICONTROL Invalid domain]**: El tipo de error generado cuando se envía una entrega a una dirección de correo electrónico cuyo dominio es incorrecto o ya no existe.
* **[!UICONTROL Unreachable]**: El tipo de error encontrado en la cadena de entrega del mensaje. Por ejemplo, incidente de rellamada SMTP, dominio no disponible temporalmente, etc.
* **[!UICONTROL Account disabled]**: El tipo de error generado cuando se envía una entrega a una dirección de correo electrónico que ya no existe.
* **[!UICONTROL Mailbox full]**: El tipo de error generado cuando la bandeja de entrada del destinatario está llena. Hay cinco intentos de enviar el mensaje antes de que se genere este error.
* **[!UICONTROL Not connected]**: El tipo de error generado cuando el teléfono móvil del destinatario está desactivado o no está conectado a una red en el momento en que se envía el mensaje.

   >[!NOTE]
   >
   >Este tipo de error solo se refiere a las entregas en canales móviles.

* **[!UICONTROL Refused]**: El tipo de error generado cuando el proveedor de servicios de Internet rechaza una dirección (ISP). Por ejemplo, cuando el software antispam aplicó una regla de seguridad.

The **Domain repartition** table displays the overall problems encountered during the deliveries according to the recipient domain.
