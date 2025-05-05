---
title: Cálculo de indicador
description: Comprenda los resultados de los informes con una lista de la fórmula de cada métrica.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Intermediate
exl-id: 47cc11d7-89e8-4d1c-9638-5f66a53cef7e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 7%

---

# Cálculo de indicador{#indicator-calculation}

>[!NOTE]
>
>Para procesar y administrar mejor los volúmenes altos y los análisis en tiempo real, el sistema de informes dinámico utiliza acumulaciones aproximadas para estimaciones de recuento distintas. Las agregaciones aproximadas ofrecen un uso limitado de la memoria y a menudo son más rápidas que los cálculos exactos.

Las tablas siguientes proporcionan la lista de los indicadores utilizados en los distintos informes y su fórmula de cálculo en función del tipo de envío.

## Envío de correo electrónico {#email-delivery}

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
   <td> En la lista de bloqueados <br /> </td> 
   <td> @blacklisted<br /> </td> 
   <td> count(@failureReason=8, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de Lista de bloqueados de<br /> </td> 
   <td> @rateBlacklisted<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error <br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Haga clic<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 ó 10 ó 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueclicks/@delivered<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en Sólo entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega <br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> @delivered/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazos graves<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failureType=2 AND @failureReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones graves<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio inválido<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failureReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Buzón lleno<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failureReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Página espejo<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en Sólo entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de la página espejo <br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@delivered<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> No conectado<br /> </td> 
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
   <td> @opens/@delivered<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en Sólo entrega.<br /> </td> 
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
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr>
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failureReason=20, @failureType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de rechazados<br /> </td> 
   <td> @rateRejected<br /> </td> 
   <td> @rejected/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivered + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Devolución suave<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failureType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de salida hacia otro sitio <br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en el recuento de Enviados (Entregados + Devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Los clics únicos se calculan utilizando conceptos de ThetaSketch. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=es#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> único(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
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
   <td> @unsubscribes/@delivered<br /> </td> 
   <td> El denominador para el cálculo de tasa se basa en Sólo entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuario desconocido<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failureReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Envío de notificaciones push {#push-notification-delivery}

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
   <td> @count(estado=enviado)<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(estado=entregado)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega <br /> </td> 
   <td> @rateDelivered<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error <br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@delivered/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(estado=abierto)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> @rateOpens<br /> </td> 
   <td> (@opens/@delivered)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopens<br /> </td> 
   <td> Las aperturas únicas se calculan mediante los conceptos de ThetaSketch de RecipientIds únicos. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=es#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(estado=entregado)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(estado=interactuar)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @uniqueclicks<br /> </td> 
   <td> Los clics únicos se calculan utilizando conceptos de ThetaSketch. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/reporting/about-reporting/troubleshooting.html?lang=es#unique-open-clicks-no-match">ejemplo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@delivered)*100<br /> </td> 
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
   <td> @count(estado=enviado)<br /> </td> 
   <td> sent=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(estado=entregado)<br /> </td> 
   <td> deliver=sent<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impressions<br /> </td> 
   <td> @count(status=view) o @count(status=button 1 click + button 2 click + dismissales)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Para <span class="uicontrol">usuarios de Target según su perfil de Campaign (inAppProfile)</span> plantilla, usuario = ID de destinatario.<br /> Para <span class="uicontrol">segmentar todos los usuarios de una aplicación móvil (inAppBroadcast)</span> y <span class="uicontrol">segmentar usuarios según su perfil móvil (inApp)</span> plantillas, usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics en la aplicación <br /> </td> 
   <td> @inappclicks<br /> </td> 
   <td> @count (estado=clic)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos en la aplicación<br /> </td> 
   <td> @uniqueinapp<br /> </td> 
   <td> @unique(@count (estado=clics))<br /> </td> 
   <td> Para <span class="uicontrol">usuarios de Target según su perfil de Campaign (inAppProfile)</span> plantilla, usuario = ID de destinatario.<br /> Para <span class="uicontrol">segmentar todos los usuarios de una aplicación móvil (inAppBroadcast)</span> y <span class="uicontrol">segmentar usuarios según su perfil móvil (inApp)</span> plantillas, usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de clics en la aplicación <br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total de clics en el botón 1 o el botón 2/total de impresiones*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despido en la aplicación<br /> </td> 
   <td> @dismissal<br /> </td> 
   <td> @count (estado=cerrar)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Descartes únicos en la aplicación<br /> </td> 
   <td> @uniquedismissal<br /> </td> 
   <td> @unique(@count (estado=cerrar))<br /> </td> 
   <td> Para <span class="uicontrol">usuarios de Target según su perfil de Campaign (inAppProfile)</span> plantilla, usuario = ID de destinatario.<br /> Para <span class="uicontrol">segmentar todos los usuarios de una aplicación móvil (inAppBroadcast)</span> y <span class="uicontrol">segmentar usuarios según su perfil móvil (inApp)</span> plantillas, usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de despido en la aplicación <br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impresiones totales/cerradas*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>
