---
title: Resolución de problemas
description: Encuentre aquí preguntas comunes relacionadas con el sistema de informes dinámico.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: beneat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: troubleshooting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a894e72bb02fbecb86d43c6d2a13adf7ab10f73e
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 5%

---


# Resolución de problemas{#troubleshooting}

En esta sección encontrará preguntas comunes relacionadas con el sistema de informes dinámico.

## Para las aperturas únicas y los clics únicos, el recuento de la fila acumulada no coincide con los de filas individuales {#unique-open-clicks-no-match}

Este es un comportamiento esperado.
Podemos tomar el siguiente ejemplo para explicar este comportamiento.

Se envía un correo electrónico a los perfiles P1 y P2.

P1 abre el correo electrónico dos veces el primer día y luego tres veces el segundo día.

Mientras que P2 abre el correo electrónico una vez el primer día y no lo vuelve a abrir en los días siguientes.
Esta es una representación visual de la interacción de los perfiles con el correo electrónico enviado:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong> <br /> </th> 
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

Para comprender el número total de aperturas únicas, necesitamos sumar los recuentos de filas de **[!UICONTROL Unique Opens]** los que se obtiene el valor 3. Pero como el correo electrónico estaba dirigido a solo 2 perfiles, la tasa de apertura debería mostrar el 150%.

Para no obtener un porcentaje superior a 100, se mantiene la definición de **[!UICONTROL Unique Opens]** frecuencia como el número de diarios de banda ancha únicos que se abrieron. En este caso, incluso si P1 abrió el correo electrónico el día 1 y el día 2, su apertura única seguirá siendo 1.

Esto dará como resultado la siguiente tabla:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Day</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong> <br /> </th> 
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
>Los recuentos únicos se basan en un boceto basado en HLL, lo que puede causar pequeñas imprecisiones en los recuentos grandes.

## Los recuentos abiertos no coinciden con el recuento de la base de datos {#open-counts-no-match-database}

Esto puede deberse al hecho de que la heurística se utiliza en el sistema de informes dinámico para rastrear aperturas incluso cuando no podemos rastrear la **[!UICONTROL Open]** acción.

Por ejemplo: si un usuario ha desactivado las imágenes de su cliente y hace clic en un vínculo del correo electrónico, es posible que la base de datos no **[!UICONTROL Open]** las rastree, pero la **[!UICONTROL Click]** voluntad.

Por lo tanto, es posible que los recuentos de **[!UICONTROL Open]** registros de seguimiento no tengan el mismo recuento en la base de datos.

Estas ocurrencias se agregan como **&quot;un clic de correo electrónico implica abrir un correo electrónico&quot;**.

>[!NOTE]
>
>Dado que los recuentos únicos se basan en un boceto basado en HLL, se pueden experimentar incoherencias menores entre los recuentos.

## ¿Cómo se calculan los recuentos de envíos recurrentes y transaccionales? {#counts-recurring-deliveries}

Al trabajar con envíos recurrentes y transaccionales, los recuentos se atribuirán tanto al envío principal como al secundario.
Podemos tomar el ejemplo de un envío recurrente llamado **R1** configurado para ejecutarse todos los días el día 1 (RC1), el día 2 (RC2) y el día 3 (RC3).
Supongamos que sólo una persona abrió todos los envíos infantiles varias veces. En este caso, los envíos secundarios recurrentes individuales mostrarán el **[!UICONTROL Open]** recuento como 1 para cada uno.
Sin embargo, como la misma persona hizo clic en todos los envíos, el envío recurrente principal también tendrá **[!UICONTROL Unique open]** el valor 1.

Los informes deben tener el siguiente aspecto:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Entrega</strong> <br /> </th> 
   <th align="center"> <strong>Enviado</strong> <br /> </th> 
   <th align="center"> <strong>Entrega</strong> <br /> </th>
   <th align="center"> <strong>Aperturas</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong> <br /> </th>
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

## ¿Cuál es la significación de los colores en la tabla de los informes? {#reports-color-signification}

Los colores que se muestran en los informes son aleatorios y no se pueden personalizar. Representan una barra de progreso y se muestran para ayudarle a resaltar mejor el valor máximo alcanzado en los informes.

En el ejemplo siguiente, la celda tiene el mismo color, ya que su valor es 100%.

![](assets/troubleshooting_1.png)

Si cambia el **[!UICONTROL Conditional formatting]** a personalizado, cuando el valor alcance el límite superior, la celda se volverá más verde. Mientras que, si alcanza el límite inferior, se enrojecerá.

Por ejemplo: aquí, establecemos el **[!UICONTROL Upper limit]** valor en 500 y **[!UICONTROL Lower limit]** en 0.

![](assets/troubleshooting_2.png)

## ¿Por qué aparece el valor N/D en mis informes?

![](assets/troubleshooting_3.png)

El valor **N/D** puede aparecer a veces en los informes dinámicos. Esto se puede mostrar por dos motivos:

* El envío se ha eliminado y se muestra aquí como **N/D** para no causar discrepancias en los resultados.
* Al arrastrar y soltar la **[!UICONTROL Transactional Delivery]** dimensión en los informes, el valor **N/D** podría aparecer como resultado. Esto sucede porque los informes dinámicos recuperan todos los envíos aunque no sean transaccionales.
Esto también puede suceder cuando arrastra y suelta la **[!UICONTROL Delivery]** dimensión en el informe, pero en este caso, el valor **N/D** representará envíos transaccionales.
