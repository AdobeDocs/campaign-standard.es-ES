---
title: Lista blanca en Adobe Campaign Standard
description: Obtenga información sobre cómo optimizar las listas blancas con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Listas blancas{#whitelists}

Los principales proveedores de servicios de Internet (ISP) y proveedores de correo Web administran listas blancas de remitentes de mensajes de correo electrónico reconocidos. Adobe Campaign le ayuda en el proceso de obtener la certificación de las mejores listas blancas.

Una lista blanca de correo electrónico es una lista de direcciones de correo electrónico o nombres de dominio desde los que un programa de bloqueo de correo electrónico permitirá recibir mensajes.

Existen dos tipos de listas blancas:
* Listas blancas no comerciales
* Listas blancas comerciales

## Listas blancas no comerciales {#non-commercial-whitelists}

Para ser aceptado por estas listas blancas, el remitente debe pasar una serie de pruebas basadas en una verificación técnica (su servidor de correo electrónico no debe ser un relé abierto, sino que debe tener una IP estática) de la infraestructura o su actividad (frecuencia de entrega, volumen, número de quejas).

Si el remitente no sigue una de estas reglas, puede eliminarse de la lista de direcciones permitidas. En su paquete de **entrega** por correo electrónico de Adobe Campaign, Adobe Campaign ofrece un servicio de consultoría de expertos para el proceso de certificación de las listas blancas no comerciales.

## Listas blancas comerciales {#commercial-whitelists}

Las listas de direcciones permitidas comerciales se basan en un sistema que permite al remitente eludir por completo los filtros antispam o se le asignan puntos incrementales a medida que ingresan al sistema. Estas listas blancas de pago (CPT o sobre una base anual) se ofrecen mediante sistemas como Puntuación del remitente de ruta de retorno.

Los ISP son libres de utilizar estos servicios y el número de ISP puede variar según la lista de direcciones permitidas. Por lo tanto, el remitente puede confiar más en el envío de sus mensajes mediante una garantía de entrega. Algunas listas blancas también ofrecen la posibilidad de abrir imágenes y activar vínculos.

Aparecer en una lista blanca es un recurso innegable para cualquier campaña de correo electrónico. En su paquete de **entrega** por correo electrónico de Adobe Campaign, Adobe Campaign ofrece un servicio de certificación comercial de la lista blanca como CSA y la puntuación del remitente de ruta de retorno.