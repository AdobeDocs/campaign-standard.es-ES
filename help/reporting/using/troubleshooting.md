---
title: Solución de problemas de informes dinámicos
description: Aquí encontrará preguntas comunes relacionadas con la creación de informes dinámicos.
audience: reporting
content-type: reference
topic-tags: troubleshooting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 0f99a109-2923-4e64-8131-80fcacf79c82
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 5%

---

# Resolución de problemas{#troubleshooting}

En esta sección encontrará preguntas comunes relacionadas con la creación de informes dinámicos.

## Para las aperturas únicas y los clics únicos, el recuento de la fila agregada no coincide con los de las filas individuales {#unique-open-clicks-no-match}

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

Para comprender el número total de aperturas únicas, es necesario resumir los recuentos de filas de **[!UICONTROL Unique Opens]** que nos da el valor 3. Pero como el correo electrónico estaba dirigido solo a 2 perfiles, la tasa de apertura debería mostrar el 150 %.

Para no obtener un porcentaje superior a 100, la definición de **[!UICONTROL Unique Opens]** se mantiene para que sea el número de broadlogs únicos que se abrieron. En este caso, incluso si P1 abrió el correo electrónico el día 1 y el día 2, sus aperturas únicas seguirán siendo 1.

Esto dará como resultado la siguiente tabla:

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
>Los recuentos únicos se basan en un boceto basado en HTML, lo que puede causar pequeñas imprecisiones en recuentos grandes.

## Los recuentos abiertos no coinciden con el recuento de la base de datos {#open-counts-no-match-database}

Esto puede deberse al hecho de que la heurística se utiliza en el sistema de informes dinámico para rastrear aperturas incluso cuando no podemos rastrear el **[!UICONTROL Open]** acción.

Por ejemplo, si un usuario ha desactivado las imágenes en su cliente y hace clic en un enlace del correo electrónico, la variable **[!UICONTROL Open]** puede no ser rastreado por la base de datos, pero la variable **[!UICONTROL Click]** lo haré.

Por lo tanto, el **[!UICONTROL Open]** es posible que los recuentos de registros de seguimiento no tengan el mismo recuento en la base de datos.

Estos sucesos se añaden como **&quot;un clic en el correo electrónico implica que se ha abierto un correo electrónico&quot;**.

>[!NOTE]
>
>Dado que los recuentos únicos se basan en un boceto basado en HTML, pueden producirse incoherencias menores entre los recuentos.

## ¿Cómo se calculan los recuentos de envíos recurrentes/transaccionales? {#counts-recurring-deliveries}

Al trabajar con envíos recurrentes y transaccionales, los recuentos se atribuyen tanto a los envíos principales como a los secundarios.
Podemos tomar el ejemplo de un envío recurrente llamado **R1** configurado para ejecutarse todos los días en el día 1 (RC1), el día 2 (RC2) y el día 3 (RC3).
Supongamos que solo una persona ha abierto todas las entregas secundarias varias veces. En este caso, las entregas secundarias recurrentes individuales mostrarán el **[!UICONTROL Open]** cuente como 1 para cada uno.
Sin embargo, como la misma persona hizo clic en todas las entregas, la entrega recurrente principal también tiene **[!UICONTROL Unique open]** como 1.

Los informes deben tener el aspecto siguiente:

<table> 
 <thead> 
  <tr> 
   <th align="center"> <strong>Envío</strong> <br /> </th> 
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

Los colores que se muestran en los informes son aleatorios y no se pueden personalizar. Representan una barra de progreso y se muestran para ayudarle a resaltar mejor el valor máximo alcanzado en los informes.

En el ejemplo siguiente, la celda es del mismo color, ya que su valor es 100%.

![](assets/troubleshooting_1.png)

Si cambia el **[!UICONTROL Conditional formatting]** de forma personalizada, cuando el valor alcance el límite superior, la celda se volverá más verde. Mientras que, si alcanza el límite inferior, se pondrá más rojo.

Por ejemplo, aquí se establece la variable **[!UICONTROL Upper limit]** a 500 y **[!UICONTROL Lower limit]** a 0.

![](assets/troubleshooting_2.png)

## ¿Por qué aparece el valor N/A en mis informes?

![](assets/troubleshooting_3.png)

El valor **N/D** a veces puede aparecer en los informes dinámicos. Esto se puede mostrar por tres motivos:

* La entrega se ha eliminado y se muestra aquí como **N/D** para no causar discrepancias en los resultados.
* Al arrastrar y soltar **[!UICONTROL Transactional Delivery]** dimensión a sus informes, el valor **N/D** podría aparecer como resultado. Esto sucede porque el informe dinámico recupera todos los envíos aunque no sean transaccionales. Esto también puede ocurrir cuando arrastra y suelta el **[!UICONTROL Delivery]** dimensión al informe, pero en este caso, la variable **N/D** representará los envíos transaccionales.
* Cuando se utiliza una dimensión con una métrica que no está relacionada con la dimensión. En el ejemplo siguiente, se añade un desglose con la variable **[!UICONTROL Tracking URL]** dimensión aunque la variable **[!UICONTROL Click]** el recuento se establece en 0 en esta entrega.

   ![](assets/troubleshooting_4.png)

## Los informes de las entregas muestran datos incompletos al utilizar la asignación de destino personalizada

Si utiliza asignaciones de Target personalizadas importadas en las entregas y no se muestran datos en los diferentes informes, esto podría significar que no se crearon los enriquecimientos de informes para esas asignaciones de Target.

Para resolver esto:

* Después de importar la asignación de Target desde un XML, también debe importar el enriquecimiento de Creación de informes.

* En lugar de importar la asignación de Target, puede crearla directamente en Adobe Campaign Standard, que creará automáticamente el enriquecimiento de creación de informes.
