---
title: Dimensiones y métricas de campaña en Analytics
seo-title: Dimensiones y métricas de campaña en Analytics
description: Dimensiones y métricas de campaña en Analytics
seo-description: Descubra las distintas dimensiones que puede encontrar en Adobe Analytics para empezar a rastrear sus entregas por correo electrónico desde Adobe Campaign.
page-status-flag: no activado nunca
uuid: effa 1028-66 b 2-4 bef-b 5 e 4-7319 dbb 23 d 5 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb 3639 f 5-7246-46 c 4-8 ddb-da 9413 b 40 c 32 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Campaign dimensions and metrics in Analytics{#campaign-dimensions-and-metrics-in-analytics}

La integración de Adobe Campaign y Adobe Analytics permite realizar el seguimiento del éxito de las entregas por correo electrónico directamente en Adobe Analytics.

Campaign **[!UICONTROL dimensions]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Dimension<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Campaign ID<br /> </td> 
   <td> Campaign's internal name as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign label<br /> </td> 
   <td> Campaign's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery ID<br /> </td> 
   <td> Nombre interno de entrega como se ve en Campaign.<br /> Por ejemplo, DM 1 es una entrega recurrente programada para enviar entregas secundarias todas las semanas. DM 2, DM 3 y DM 4 se envían las primeras tres semanas. The Delivery ID dimension will then display the results for every delivery, namely DM1 to DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery label<br /> </td> 
   <td> Delivery's label as seen in Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery ID<br /> </td> 
   <td> Nombre interno de entrega como se ve en Campaign. Esto solo concierne a la entrega en ejecución en Campaign.<br /> Por ejemplo, DM 1 es una entrega recurrente programada para enviar entregas secundarias todas las semanas. DM 2, DM 3 y DM 4 se envían las primeras tres semanas. The Executed delivery ID dimension will then display the results for the executed deliveries, namely the child deliveries DM2, DM3 and DM4. <br /> </td> 
  </tr> 
  <tr> 
   <td> Executed delivery label<br /> </td> 
   <td> Etiqueta de entrega como se ve en Campaign. This only concerns delivery in execution in Campaign.<br /> </td> 
  </tr> 
 </tbody> 
</table>

Campaign **[!UICONTROL metrics]** found in Analytics are listed below:

<table> 
 <thead> 
  <tr> 
   <th> Metric<br /> </th> 
   <th> Definition<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Clicked<br /> </td> 
   <td> Number of times a content was clicked in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivered<br /> </td> 
   <td> Number of messages successfully sent, in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Opened<br /> </td> 
   <td> Number of times a message was opened in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sent<br /> </td> 
   <td> Total number of sends for the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Total Bounces<br /> </td> 
   <td> Total of errors cumulated during delivery and automatic return processing in relation to the total number of sent messages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Open<br /> </td> 
   <td> Number of recipients who opened the delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unique Click<br /> </td> 
   <td> Number of recipients who clicked on a content in a delivery.<br /> </td> 
  </tr> 
  <tr> 
   <td> Unsubscribed<br /> </td> 
   <td> Number of clicks on the unsubscription link.<br /> </td> 
  </tr> 
 </tbody> 
</table>

