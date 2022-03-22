---
title: Resolución de problemas de la creación de informes dinámicos
description: Encuentre aquí preguntas comunes relacionadas con los informes dinámicos.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 5%

---

# Resolución de problemas{#troubleshooting}

En esta sección se pueden encontrar preguntas comunes relacionadas con los informes dinámicos.

## En el caso de aperturas únicas y clics únicos, el recuento de la fila agregada no coincide con los de filas individuales {#unique-open-clicks-no-match}

Este es un comportamiento esperado.
Podemos tomar el siguiente ejemplo para explicar este comportamiento.

Se envía un correo electrónico a los perfiles P1 y P2.

P1 abre el correo electrónico dos veces el primer día y, a continuación, tres veces el segundo día.

Por su parte, P2 abre el correo electrónico una vez el primer día y no lo vuelve a abrir en los días siguientes.
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
   <td align="center"> Día 1<br /> </td> 
   <td align="center"> 2 + 1 = 3<br /> </td> 
   <td align="center"> 1 + 1 = 2<br /> </td> 
  </tr> 
  <tr> 
   <td align="center"> Día 2<br /> </td> 
   <td align="center"> 3 + 0 = 3<br /> </td> 
   <td align="center"> 1 + 0 = 1<br /> </td> 
  </tr>
 </tbody> 
</table>

Para comprender el número total de aperturas únicas, necesitamos sumar los recuentos de filas de **[!UICONTROL Unique Opens]** que nos da el valor 3. Pero como el correo electrónico estaba dirigido a solo 2 perfiles, la tasa de apertura debería mostrar el 150%.

Para no obtener un porcentaje superior a 100, la definición de **[!UICONTROL Unique Opens]** se mantiene como el número de broadlogs únicos que se abrieron. En este caso, incluso si P1 abrió el correo electrónico el día 1 y el día 2, sus aperturas únicas seguirán siendo 1.

Esto resultará en la siguiente tabla:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong></strong> <br /> </th> 
   <th align="center"> <strong>Aperturas</strong> <br /> </th> 
   <th align="center"> <strong>Aperturas únicas</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td align="center"> <strong> Day </strong><br /> </td> 
   <td align="center"> <strong> 6 </strong><br /> </td> 
   <td align="center"> <strong> 2</strong><br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Día 1<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 2<br /> </td>
  </tr> 
  <tr> 
   <td align="center"> Día 2<br /> </td> 
   <td align="center"> 3<br /> </td> 
   <td align="center"> 1<br /> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Los recuentos únicos se basan en un boceto basado en HLL, lo que puede causar pequeñas imprecisiones en recuentos grandes.

## Los recuentos abiertos no coinciden con el recuento de bases de datos {#open-counts-no-match-database}

Esto puede deberse a que, en los informes dinámicos, se usan heurística para realizar el seguimiento de las aperturas, incluso cuando no se puede realizar el seguimiento de la variable **[!UICONTROL Open]** acción.

Por ejemplo, si un usuario ha deshabilitado las imágenes en su cliente y hace clic en un vínculo del correo electrónico, se muestra la variable **[!UICONTROL Open]** puede que la base de datos no la rastree, pero la variable **[!UICONTROL Click]** será.

Por lo tanto, la variable **[!UICONTROL Open]** es posible que los recuentos de registros de seguimiento no tengan el mismo recuento en la base de datos.

Estas ocurrencias se añaden como **&quot;un clic en un correo electrónico implica una apertura de correo electrónico&quot;**.

>[!NOTE]
>
>Dado que los recuentos únicos se basan en un boceto basado en HLL, se pueden experimentar incoherencias menores entre los recuentos.

## ¿Cómo se calculan los recuentos de las entregas recurrentes/transaccionales? {#counts-recurring-deliveries}

Al trabajar con envíos recurrentes y transaccionales, los recuentos se atribuyen tanto a los envíos principales como a los secundarios.
Podemos tomar el ejemplo de un envío recurrente llamado **R1** configurado para ejecutarse todos los días en el día 1 (RC1), día 2 (RC2) y día 3 (RC3).
Supongamos que solo una persona abrió todas las entregas secundarias varias veces. En este caso, los envíos secundarios recurrentes individuales mostrarán la variable **[!UICONTROL Open]** cuenta como 1 para cada uno.
Sin embargo, como la misma persona hizo clic en todos los envíos, la entrega recurrente principal también tendrá **[!UICONTROL Unique open]** como 1.

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
   <td align="center"> <strong>R1</strong><br/> </td> 
   <td align="center"> <strong>100</strong><br/> </td> 
   <td align="center"> <strong>90</strong><br/> </td> 
   <td align="center"> <strong>10</strong><br/> </td> 
   <td align="center"> <strong>3</strong><br/> </td> 
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

## ¿Cuál es la significación de los colores en la tabla de mis informes? {#reports-color-signification}

Los colores mostrados en los informes se asignan de forma aleatoria y no se pueden personalizar. Representan una barra de progreso y se muestran para ayudarle a resaltar mejor el valor máximo alcanzado en sus informes.

En el ejemplo siguiente, la celda tiene el mismo color, ya que su valor es del 100%.

![](assets/troubleshooting_1.png)

Si cambia la variable **[!UICONTROL Conditional formatting]** a personalizado, cuando el valor alcance el límite superior, la celda se volverá más verde. En cambio, si alcanza el límite inferior, se procesará.

Por ejemplo, aquí establecemos la variable **[!UICONTROL Upper limit]** a 500 y **[!UICONTROL Lower limit]** a 0.

![](assets/troubleshooting_2.png)

## ¿Por qué aparece el valor N/A en mis informes?

![](assets/troubleshooting_3.png)

El valor **N/D** a veces aparecen en los informes dinámicos. Esto se puede mostrar por tres motivos:

* La entrega se ha eliminado y se muestra aquí como **N/D** para no causar discrepancias en los resultados.
* Al arrastrar y soltar el **[!UICONTROL Transactional Delivery]** dimensión de los informes, el valor **N/D** puede aparecer como resultado. Esto sucede porque los informes dinámicos recuperan cada envío aunque no sean transaccionales. Esto también puede ocurrir al arrastrar y soltar el **[!UICONTROL Delivery]** al informe, pero en este caso, la dimensión **N/D** representa los envíos transaccionales.
* Cuando se utiliza una dimensión con una métrica que no está relacionada con la dimensión. En el ejemplo siguiente, se agrega un desglose con la variable **[!UICONTROL Tracking URL]** aunque la dimensión **[!UICONTROL Click]** count se establece en 0 en esta entrega.

   ![](assets/troubleshooting_4.png)

