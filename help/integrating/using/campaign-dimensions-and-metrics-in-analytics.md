---
solution: Campaign Standard
product: campaign
title: Dimensiones y métricas de Campaign en Analytics
description: Conozca las diferentes dimensiones que puede encontrar en Adobe Analytics para realizar el seguimiento de inicios de sus envíos de correo electrónico desde Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 7%

---


# Dimensiones y métricas de Campaign en Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics le permite realizar un seguimiento del éxito de sus envíos de correo electrónico directamente en Adobe Analytics.

La campaña **[!UICONTROL dimensions]** encontrada en Analytics se muestra a continuación:

<table> 
 <thead> 
  <tr> 
   <th> Dimensión<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> ID de campaña<br /> </td> 
   <td> Nombre interno de la campaña como se ve en Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de campaña<br /> </td> 
   <td> Etiqueta de la campaña como se ve en la Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío<br /> </td> 
   <td> Nombre interno del envío como se ve en Campaña.<br /> Por ejemplo, DM1 es un envío recurrente programado para enviar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de Envío mostrará los resultados de cada envío, a saber, de DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío<br /> </td> 
   <td> Etiqueta del envío como se ve en la Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío ejecutado<br /> </td> 
   <td> Nombre interno del envío como se ve en Campaña. Esto sólo se refiere al envío en ejecución en Campaña.<br /> Por ejemplo, DM1 es un envío recurrente programado para enviar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. A continuación, la dimensión ID de envío ejecutado mostrará los resultados de los envíos ejecutados, a saber, los envíos secundarios DM2, DM3 y DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío ejecutada<br /> </td> 
   <td> Etiqueta del envío como se ve en la Campaña. Esto sólo se refiere al envío en ejecución en Campaña.<br /> </td> 
  </tr> 
 </tbody> 
</table>

La campaña **[!UICONTROL metrics]** encontrada en Analytics se muestra a continuación:

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
   <td> Número de veces que se hizo clic en un contenido en un envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto<br /> </td> 
   <td> Número de veces que se abrió un mensaje en un envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> Número total de envíos para el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones totales<br /> </td> 
   <td> Total de errores acumulados durante el envío y el procesamiento de devolución automático en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura única<br /> </td> 
   <td> Número de destinatarios que abrieron el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic único<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de un envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> No suscrito<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>

