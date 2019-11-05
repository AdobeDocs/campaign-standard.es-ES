---
title: Dimensiones y métricas de Campaign en Analytics
description: Conozca las diferentes dimensiones que puede encontrar en Adobe Analytics para empezar a realizar el seguimiento de los envíos de correo electrónico desde Adobe Campaign.
page-status-flag: nunca activado
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y análisis
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Dimensiones y métricas de Campaign en Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics permite realizar un seguimiento del éxito de los envíos de correo electrónico directamente en Adobe Analytics.

Las campañas **[!UICONTROL dimensions]** encontradas en Analytics se enumeran a continuación:

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
   <td> Etiqueta de campaña tal como se ve en Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de envío<br /> </td> 
   <td> Nombre interno de la entrega tal como se ve en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para enviar entregas infantiles cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega mostrará los resultados de cada entrega, a saber, de DM1 a DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de envío<br /> </td> 
   <td> Etiqueta de entrega tal como se ve en Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> ID de entrega ejecutada<br /> </td> 
   <td> Nombre interno de la entrega tal como se ve en Campaign. Esto solo afecta a la entrega en ejecución en Campaign.<br /> Por ejemplo, DM1 es una entrega recurrente programada para enviar entregas infantiles cada semana. DM2, DM3 y DM4 se envían las tres primeras semanas. La dimensión ID de entrega ejecutada mostrará los resultados de las entregas ejecutadas, a saber, las entregas secundarias DM2, DM3 y DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de entrega ejecutada<br /> </td> 
   <td> Etiqueta de entrega tal como se ve en Campaña. Esto solo afecta a la entrega en ejecución en Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Las campañas **[!UICONTROL metrics]** encontradas en Analytics se enumeran a continuación:

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
   <td> Cantidad de veces que se hizo clic en un contenido en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
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
   <td> Total de errores acumulados durante la entrega y el procesamiento de devolución automático en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura única<br /> </td> 
   <td> Número de destinatarios que abrieron el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clic único<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> No suscrito<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>

