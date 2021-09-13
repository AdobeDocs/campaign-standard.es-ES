---
title: Cálculo de indicador
description: Comprender los resultados de los informes con una lista de la fórmula de cada métrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '726'
ht-degree: 8%

---

# Cálculo de indicador{#indicator-calculation}

>[!NOTE]
>
>Para procesar y administrar mejor los volúmenes altos y los análisis en tiempo real, los informes dinámicos utilizan acumulaciones aproximadas para realizar estimaciones de recuento distintas. Las agregaciones aproximadas ofrecen un uso limitado de la memoria y a menudo son más rápidas que los cálculos exactos.

Las tablas siguientes proporcionan la lista de indicadores utilizados en los distintos informes y su fórmula de cálculo en función del tipo de envío.

## Entrega de correo electrónico {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong> <br /> </th> 
   <th> <strong>Nombre del campo</strong> <br /> </th> 
   <th> <strong>Fórmula de cálculo del indicador</strong> <br /> </th> 
   <th> <strong>Comentarios</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Cuenta deshabilitada<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failureReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Al lista de bloqueados de la <br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> lista de bloqueados tasa de <br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Haga clic en<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 o 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@deliver<br /> </td> 
   <td> El denominador para el cálculo de la tasa se basa en Entrega solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @deliver<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa entregada<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @deliver/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazos graves<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones duras<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio inválido<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Buzón de correo lleno<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Página espejo<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> El denominador para el cálculo de la tasa se basa en Entrega solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de página espejo<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@deliver<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Sin conexión<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failureReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> @uniqueOpens<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> @opens/@deliver<br /> </td> 
   <td> El denominador para el cálculo de la tasa se basa en Entrega solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cuarentena<br /> </td> 
   <td> @quarantine<br /> </td> 
   <td> isQuarantine=true<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de cuarentena<br /> </td> 
   <td> @rateQuarantine<br /> </td> 
   <td> @quarantine/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr>
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa rechazada<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @deliver + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rechazo leve<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones suave<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Los clics únicos se calculan mediante conceptos de ThetaSketch. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inaccesible <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failureReason=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Cancelar suscripción<br /> </td> 
   <td> @unsubscribes<br /> </td> 
   <td> count(@trackingUrlType=3)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de cancelación de suscripción<br /> </td> 
   <td> @rateUnsubscribes<br /> </td> 
   <td> @unsubscribes/@deliver<br /> </td> 
   <td> El denominador para el cálculo de la tasa se basa en Entrega solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuario desconocido<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega de notificaciones push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong> <br /> </th> 
   <th> <strong>Nombre del campo</strong> <br /> </th> 
   <th> <strong>Fórmula de cálculo del indicador</strong> <br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @deliver<br /> </td> 
   <td> @count(status=deliver)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa entregada<br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@deliver/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@deliver/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@deliver)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> Las aperturas únicas se calculan utilizando conceptos ThetaSketch de RecipientIds únicos. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=deliver)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic en<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interaction)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Los clics únicos se calculan mediante conceptos de ThetaSketch. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interaction/@delivered)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega en la aplicación {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong> <br /> </th> 
   <th> <strong>Nombre del campo</strong> <br /> </th> 
   <th> <strong>Fórmula de cálculo del indicador</strong> <br /> </th> 
   <th> <strong>Comentarios</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @count(status=sent)<br /> </td> 
   <td> sent=deliver<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @deliver<br /> </td> 
   <td> @count(status=deliver)<br /> </td> 
   <td> deliver=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) o @count(status=button 1 clic + botón 2 clic + despidos)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Para la plantilla <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> , user = Recipient Id.<br /> Para  <span class="uicontrol">dirigirse a todos los usuarios de una aplicación móvil (en AppBroadcast)</span>  y a los usuarios de  <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , user = MC Id o equivalente que represente una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics en la aplicación <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (status=click)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos en la aplicación<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (status=clicks)<br /> </td> 
   <td> Para la plantilla <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> , user = Recipient Id.<br /> Para  <span class="uicontrol">dirigirse a todos los usuarios de una aplicación móvil (en AppBroadcast)</span>  y a los usuarios de  <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , user = MC Id o equivalente que represente una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones en la aplicación<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Clics totales en el Botón 1 o el Botón 2/impresiones totales*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despido en la aplicación<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Eliminaciones únicas en la aplicación<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Para la plantilla <span class="uicontrol">Target users based on their Campaign profile (inAppProfile)</span> , user = Recipient Id.<br /> Para  <span class="uicontrol">dirigirse a todos los usuarios de una aplicación móvil (en AppBroadcast)</span>  y a los usuarios de  <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , user = MC Id o equivalente que represente una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de despido en la aplicación<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impresiones de cierre/total*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
