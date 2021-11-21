---
title: Dimensiones y métricas de Campaign en Analytics
description: Conozca las diferentes dimensiones que puede encontrar en Adobe Analytics para iniciar el seguimiento de los envíos de correo electrónico desde Adobe Campaign.
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
ht-degree: 7%

---

# Dimensiones y métricas de Campaign en Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics permite realizar un seguimiento del éxito de los envíos de correo electrónico directamente en Adobe Analytics.

Campaign **[!UICONTROL dimensions]** en Analytics se enumeran a continuación:

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
   <td> Nombre interno de la campaña tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de campaña<br /> </td> 
   <td> Etiqueta de campaña tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega<br /> </td> 
   <td> Nombre interno de la entrega como se ve en Campaign.<br /> Por ejemplo, DM1 es un envío recurrente programado para enviar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las primeras tres semanas. La dimensión ID de entrega muestra los resultados de cada entrega, concretamente de DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de entrega<br /> </td> 
   <td> Etiqueta de entrega tal como se ve en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega ejecutada<br /> </td> 
   <td> Nombre interno de la entrega como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> Por ejemplo, DM1 es un envío recurrente programado para enviar envíos secundarios cada semana. DM2, DM3 y DM4 se envían las primeras tres semanas. La dimensión ID de entrega ejecutada muestra los resultados de las entregas ejecutadas, concretamente las entregas secundarias DM2, DM3 y DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de entrega ejecutada<br /> </td> 
   <td> Etiqueta de entrega tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** en Analytics se enumeran a continuación:

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
   <td> Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Abierto<br /> </td> 
   <td> Número de veces que se abrió un mensaje en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> Número total de envíos para la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones totales<br /> </td> 
   <td> Total de errores acumulados durante la entrega y el procesamiento automático de devoluciones en relación con la cantidad total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura única<br /> </td> 
   <td> Número de destinatarios que abrieron la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic único<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cancelación de suscripción<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>
