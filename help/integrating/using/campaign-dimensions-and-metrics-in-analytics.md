---
title: Dimensiones y métricas de Campaign en Analytics
description: Conozca las diferentes dimensiones que puede encontrar en Adobe Analytics para empezar a rastrear las entregas de correo electrónico desde Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6516c71a-efa8-4778-82bb-10615378f985
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 4%

---

# Dimensiones y métricas de Campaign en Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics le permite hacer un seguimiento del éxito de sus envíos de correo electrónico directamente en Adobe Analytics.

Campaign **[!UICONTROL dimensions]** que se encuentran en Analytics se enumeran a continuación:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID de campaña<br /> </td> 
   <td> Nombre interno de la campaña, tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de campaña<br /> </td> 
   <td> Etiqueta de campaña tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío<br /> </td> 
   <td> Nombre interno de la entrega, tal como se ve en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para realizar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega mostrará los resultados de cada entrega, es decir, de DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío<br /> </td> 
   <td> Etiqueta de envío tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío ejecutado<br /> </td> 
   <td> Nombre interno de la entrega, tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para realizar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega ejecutada muestra los resultados de las entregas ejecutadas, es decir, las entregas secundarias DM2, DM3 y DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío ejecutada<br /> </td> 
   <td> Etiqueta de envío tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** que se encuentran en Analytics se enumeran a continuación:

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clic<br /> </td> 
   <td> Número de veces que se hizo clic en un contenido en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de mensajes enviados correctamente en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto<br /> </td> 
   <td> Número de veces que se ha abierto un mensaje en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> Número total de envíos para el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones totales<br /> </td> 
   <td> Total de errores acumulados durante el envío y el procesamiento automático de devoluciones en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Única y abierta<br /> </td> 
   <td> Número de destinatarios que abrieron la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic único<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cancelado<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>
