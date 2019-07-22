---
title: Solución de problemas
seo-title: Solución de problemas
description: Solución de problemas
seo-description: Aquí encontrará preguntas comunes relacionadas con los informes dinámicos.
page-status-flag: no activado nunca
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: en
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: solución de problemas
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e0cbdfecde495d7c9f8bfa33dd5ee8598cdfe60a

---


# Troubleshooting{#troubleshooting}

En esta sección encontrará preguntas comunes relacionadas con los informes dinámicos.

## For Unique opens and Unique clicks, the count in the aggregate row is not matching the ones in individual rows {#unique-open-clicks-no-match}

Se trata de un comportamiento esperado.
Podemos tomar el siguiente ejemplo para explicar este comportamiento.

Se envía un correo electrónico a los perfiles P 1 y P 2.

P 1 abre el mensaje de correo electrónico dos veces el primer día y, a continuación, hora del árbol el segundo día.

En cambio, P 2 abre el mensaje de correo electrónico una vez el primer día y no lo vuelve a abrir en los días siguientes.
Esta es una representación visual de la interacción de perfiles con el correo electrónico enviado:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Día</strong><br /> </th> 
   <th align="center"> <strong>Aperturas</strong><br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

To understand the overall number of unique opens, we need to sum up the row counts of **[!UICONTROL Unique Opens]** which gives us the value 3. Sin embargo, como el correo electrónico fue dirigido solo a 2 perfiles, la tasa de apertura debería mostrar 150%.

To not obtain percentage higher than 100, the definition of **[!UICONTROL Unique Opens]** is maintained to be the number of unique broadlogs that were opened. En este caso, incluso si P 1 abrió el correo electrónico el día 1 y el Día 2, sus aperturas únicas seguirán siendo 1.

Esto resultará en la siguiente tabla:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Día</strong><br /> </th> 
   <th align="center"> <strong>Aperturas</strong><br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> Day 1<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Day 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Los recuentos únicos se basan en un boceto basado en HLL, esto puede provocar leves imprecisiones en recuentos grandes.

## Open counts do not match the Database count {#open-counts-no-match-database}

This may be due to the fact that, heuristics are used in Dynamic reporting to track opens even when we can't track the **[!UICONTROL Open]** action.

For example, if a user has disabled images on their client and click on a link in the email, the **[!UICONTROL Open]** may not be tracked by the database but the **[!UICONTROL Click]** will.

Therefore, the **[!UICONTROL Open]** tracking logs counts may not have the same count in the database.

Such occurrences are added as **"an email click implies an email open"**.

>[!NOTE]
>
>Debido a que los recuentos únicos se basan en un boceto basado en HLL, se pueden experimentar incoherencias menores entre los recuentos.

## ¿Cómo se calculan los recuentos para entregas recurrentes o transaccionales?

Al trabajar con entregas recurrentes y transaccionales, los recuentos se atribuirán tanto a los envíos principales como secundarios.

We can take the example of a recurring delivery named **R1** set to run every day on day 1 (RC1), day 2 (RC2) and day 3 (RC3).

Supongamos que solo una persona abrió todos los envíos secundarios varias veces. In this case, the individual recurring child deliveries will show the **[!UICONTROL Open]** count as 1 for each.

However, since the same person clicked on all the deliveries, the parent recurring delivery will also have **[!UICONTROL Unique open]** as 1.

After the Adobe Campaign Standard 19.2.1 release, the definition of **Unique counts** is changed from **Number of unique persons interacting with the delivery** to **Number of unique messages interacted**.

Antes de la versión de Adobe Campaign Standard 19.2.1, los informes tenían el siguiente aspecto:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregado</strong><br /> </th>
   <th align="center"> <strong>Aperturas</strong><br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>1<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Después de la versión Adobe Campaign Standard 19.2.1, los informes tienen el siguiente aspecto:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong><br /> </th> 
   <th align="center"> <strong>Enviado</strong><br /> </th> 
   <th align="center"> <strong>Entregado</strong><br /> </th>
   <th align="center"> <strong>Aperturas</strong><br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong><br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong>R1<br/> </td> 
   <td align="center"> <strong>100<br/> </td> 
   <td align="center"> <strong>90<br/> </td> 
   <td align="center"> <strong>10<br/> </td> 
   <td align="center"> <strong>3<br/> </td> 
  </tr> 
  <tr> 
   <td align="center"> RC1<br/> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 20<br /> </td> 
   <td align="center"> 6<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr>
    <tr> 
   <td align="center"> RC2<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 30<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
    <tr> 
   <td align="center"> RC3<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 40<br /> </td> 
   <td align="center"> 2<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

## What is the colors' signification in my reports' table? {#reports-color-signification}

Los colores mostrados en los informes se muestran aleatoriamente y no pueden personalizarse. Representan una barra de progreso y se muestran para ayudarle a resaltar mejor el valor máximo alcanzado en los informes.

En el ejemplo siguiente, la celda es del mismo color, ya que su valor es 100%.

![](assets/troubleshooting_1.png)

If you change the **Conditional formatting** to custom, when the value reaches the upper limit the cell will get greener. En cambio, si alcanza el límite inferior, se obtendrá un rojizo.

For example, here, we set the **Upper limit** to 500 and **Lower limit** to 0.

![](assets/troubleshooting_2.png)