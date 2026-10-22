---
title: Dimensiones y métricas de Campaign en Analytics
description: Conozca las diferentes dimensiones que puede encontrar en Adobe Analytics para empezar a rastrear las entregas de correo electrónico desde Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
TQID: 'https://experienceleague.adobe.com/PSAzSStMFWofMteBu3jMSizD2kj1M9F7-0iO3dcugjY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 4%
---
# Dimensiones y métricas de Campaign en Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics le permite hacer un seguimiento del éxito de sus envíos de correo electrónico directamente en Adobe Analytics.

La campaña **[!UICONTROL dimensions]** encontrada en Analytics se enumera a continuación:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definición <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Id. de campaña<br /> </td> 
   <td> Nombre interno de la campaña tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de campaña<br /> </td> 
   <td> Etiqueta de campaña tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío <br /> </td> 
   <td> Nombre interno de la entrega tal como se ve en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para realizar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega mostrará los resultados de cada entrega, es decir, de DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío <br /> </td> 
   <td> Etiqueta de envío tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Id. de envío ejecutado<br /> </td> 
   <td> Nombre interno de la entrega, tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para realizar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega ejecutada mostrará los resultados de las entregas ejecutadas, es decir, las entregas secundarias DM2, DM3 y DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío ejecutada <br /> </td> 
   <td> Etiqueta de envío tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La campaña **[!UICONTROL metrics]** encontrada en Analytics se enumera a continuación:

<table> 
 <thead> 
  <tr> 
   <th> Métrica <br /> </th> 
   <th> Definición <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Se hizo clic<br /> </td> 
   <td> Número de veces que se hizo clic en un contenido en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de mensajes enviados correctamente en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto<br /> </td> 
   <td> Número de veces que se abrió un mensaje en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> Número total de envíos para el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones totales <br /> </td> 
   <td> Total de errores acumulados durante el envío y el procesamiento automático de devolución en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Único abierto<br /> </td> 
   <td> Número de destinatarios que abrieron la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic único<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canceló la suscripción<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>
