---
title: Cálculo de indicador
description: Comprender los resultados de los informes con una lista de la fórmula de cada métrica.
page-status-flag: never-activated
uuid: dfbc9d7e-62db-4e77-bb8e-0ac826ec7333
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: 45b11631-6b32-4074-8c8d-affd06407810
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3033e2f15065685f3c0e7c1759e184738cb67d9c

---


# Cálculo de indicador{#indicator-calculation}

Las tablas siguientes proporcionan la lista de indicadores utilizados en los distintos informes y su fórmula de cálculo según el tipo de envío.

## Envío de correo electrónico {#email-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong><br /> </th> 
   <th> <strong>Nombre del campo</strong> <br /> </th> 
   <th> <strong>Fórmula de cálculo del indicador</strong> <br /> </th> 
   <th> <strong>Comentarios</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Cuenta deshabilitada<br /> </td> 
   <td> @disabled<br /> </td> 
   <td> count(@failReason=4)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Bloqueado<br /> </td> 
   <td> @blacklist<br /> </td> 
   <td> count(@failReason=8, @failType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tarifa bloqueada<br /> </td> 
   <td> @rateBlacklists<br /> </td> 
   <td> @blacklisted/@sent<br /> </td> 
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> @bounces<br /> </td> 
   <td> count(@status=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rebotes + tasa de error<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> @bounces/@sent<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Haga clic<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> count(@trackingUrlType=1 o 10 o 11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> @uniqueClicks/@unique<br /> </td> 
   <td> El denominador para el cálculo del tipo de interés se basa en Entregado solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> count(@status=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> @rateEntreged<br /> </td> 
   <td> @delivery/@sent<br /> </td> 
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazos graves<br /> </td> 
   <td> @hardBounces<br /> </td> 
   <td> count(@failType=2 AND @failReason=8)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones en bruto<br /> </td> 
   <td> @rateHardBounces<br /> </td> 
   <td> @hardBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio inválido<br /> </td> 
   <td> @invalidDomain<br /> </td> 
   <td> count(@failReason=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Buzón de correo lleno<br /> </td> 
   <td> @mailBoxFull<br /> </td> 
   <td> count(@failReason=5)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Página de reflejo<br /> </td> 
   <td> @mirrorPage<br /> </td> 
   <td> count(@trackingUrlType=6)<br /> </td> 
   <td> El denominador para el cálculo del tipo de interés se basa en Entregado solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reflejar tasa de página<br /> </td> 
   <td> @rateMirrorPage<br /> </td> 
   <td> @mirrorPage/@did<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Sin conexión<br /> </td> 
   <td> @notConnected<br /> </td> 
   <td> count(@failReason=6)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> @uniqueOpen<br /> </td> 
   <td> count(@trackingUrlType=2 + unique(@trackingUrlType=1,2,3,6,10,11) - unique(@trackingUrlType=2))<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa abierta<br /> </td> 
   <td> @rateOpen<br /> </td> 
   <td> @open/@delivery<br /> </td> 
   <td> El denominador para el cálculo del tipo de interés se basa en Entregado solamente.<br /> </td> 
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
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> @refused<br /> </td> 
   <td> count(@failReason=20)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> @rejected<br /> </td> 
   <td> count(@failReason=20, @failType=2)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa rechazada<br /> </td> 
   <td> @rateReject<br /> </td> 
   <td> @rechazado/@sent<br /> </td> 
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> @sent<br /> </td> 
   <td> @delivery + @bounces<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Rebote suave<br /> </td> 
   <td> @softBounces<br /> </td> 
   <td> count(@failType=1)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Tasa de salida hacia otro sitio suave<br /> </td> 
   <td> @rateSoftBounces<br /> </td> 
   <td> @softBounces/@sent<br /> </td> 
   <td> El denominador para el cálculo del tipo se basa en el recuento de envíos (entregado + devoluciones).<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @exclueclicks<br /> </td> 
   <td> Los clics únicos se calculan mediante conceptos de ThetaSketch.<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> unique(@trackingUrlType=1,2,3,6,10,11)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Inaccesible <br /> </td> 
   <td> @unreachable<br /> </td> 
   <td> count(@failReason=3)<br /> </td> 
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
   <td> @unsubscribes/@delivery<br /> </td> 
   <td> El denominador para el cálculo del tipo de interés se basa en Entregado solamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Usuario desconocido<br /> </td> 
   <td> @unknownUser<br /> </td> 
   <td> count(@failReason=1)<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

## Envío de notificaciones push {#push-notification-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong><br /> </th> 
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
   <td> Enviado<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> @rateEntreged<br /> </td> 
   <td> (@did/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Rebotes + tasa de error<br /> </td> 
   <td> @rateBounces<br /> </td> 
   <td> (@did/@sent)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> @opens<br /> </td> 
   <td> @count(status=open)<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa abierta<br /> </td> 
   <td> @rateOpen<br /> </td> 
   <td> (@open/@delivery)*100<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> @uniqueopen<br /> </td> 
   <td> Las aperturas únicas se calculan utilizando los conceptos de ThetaSketch de RecipientIds únicos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impresiones<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic<br /> </td> 
   <td> @clicks<br /> </td> 
   <td> @count(status=interactive)<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> @exclueclicks<br /> </td> 
   <td> Los clics únicos se calculan mediante conceptos de ThetaSketch.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> @clickthrough<br /> </td> 
   <td> (@interact/@did)*100<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Entrega en la aplicación {#in-app-delivery}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Etiqueta</strong><br /> </th> 
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
   <td> sent=received<br /> </td> 
  </tr> 
  <tr> 
   <td> Enviado<br /> </td> 
   <td> @delivered<br /> </td> 
   <td> @count(status=delivery)<br /> </td> 
   <td> entregado=enviado<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> @impresiones<br /> </td> 
   <td> @count(status=view) o @count(status=button 1 clic + botón 2 clic + despidos)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> @uniqueimpressions<br /> </td> 
   <td> @unique(@count(status=view))<br /> </td> 
   <td> Para los usuarios de <span class="uicontrol">Target según su plantilla de perfil de campaña (en AppProfile)</span> , usuario = ID del destinatario.<br /> Para <span class="uicontrol">Target, todos los usuarios de una aplicación móvil (en AppBroadcast)</span> y los usuarios de <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
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
   <td> @unique(@count (status=clicks))<br /> </td> 
   <td> Para los usuarios de <span class="uicontrol">Target según su plantilla de perfil de campaña (en AppProfile)</span> , usuario = ID del destinatario.<br /> Para <span class="uicontrol">Target, todos los usuarios de una aplicación móvil (en AppBroadcast)</span> y los usuarios de <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones en la aplicación<br /> </td> 
   <td> @inappclickthrough<br /> </td> 
   <td> Total de clics en el botón 1 o el botón 2/impresiones totales*100<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despido en la aplicación<br /> </td> 
   <td> @dismisal<br /> </td> 
   <td> @count (status=close)<br /> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> Despedidos únicos en la aplicación<br /> </td> 
   <td> @uniquedismisal<br /> </td> 
   <td> @unique(@count (status=close))<br /> </td> 
   <td> Para los usuarios de <span class="uicontrol">Target según su plantilla de perfil de campaña (en AppProfile)</span> , usuario = ID del destinatario.<br /> Para <span class="uicontrol">Target, todos los usuarios de una aplicación móvil (en AppBroadcast)</span> y los usuarios de <span class="uicontrol">Target según sus plantillas de perfil móvil (en la aplicación)</span> , usuario = ID de MC o equivalente que representa una combinación única de usuario, aplicación móvil y dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de despido en la aplicación<br /> </td> 
   <td> @dismissalrate<br /> </td> 
   <td> Total de impresiones de cierre/total*100<br /> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

