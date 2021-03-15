---
solution: Campaign Standard
product: campaign
title: Mejora de la reputación con Adobe Campaign Standard
description: Aprenda a mejorar su reputación con Adobe Campaign Standard administrando direcciones de correo electrónico y cuarentenas duplicadas.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Capacidad de entrega
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 71%

---


# Mejora de la reputación{#improving-reputation}

Para evitar que los destinatarios se agoten, elimine del destinatario las direcciones de correo electrónico duplicadas. Este paso protege su reputación de envío y garantiza una buena gestión de cuarentena. Adobe Campaign ofrece las herramientas necesarias para implementar estas recomendaciones y evitar el riesgo de que los ISP las agreguen a la  de lista de bloqueados.

A continuación se encuentran detalles sobre la administración de duplicados y cuarentena.

## Duplicados {#duplicates}

Contar con direcciones de correo electrónico duplicadas puede tener varias consecuencias:
* El mismo mensaje se envía más de una vez. Incluso si Campaign realiza un procedimiento de deduplicación de forma predeterminada antes de la entrega, no hay nada que detenga el mismo mensaje enviado por acciones diferentes que tengan el mismo contenido cuando se divide un destinatario.
* Solicitudes de cancelación de suscripción no aceptadas. Si un destinatario cancela la suscripción después de recibir un mensaje, su perfil duplicado sigue siendo apto para mensajes posteriores.

Además de este paso secundario de los procedimientos de inclusión, esta situación probablemente lleve a los usuarios a considerar los mensajes como no deseados y a activar un procedimiento de inclusión en la lista de bloqueados en el ISP.

Debe tener especial cuidado al realizar operaciones en la base de datos. Para evitar la mayor cantidad posible de duplicados, deben llevarse a cabo las siguientes acciones:
* **Las importaciones deben configurarse meticulosamente.** Esto es especialmente importante a la hora de elegir la clave de reconciliación.
* **Tenga cuidado al modificar direcciones de correo electrónico.** Las direcciones de correo electrónico cambiadas también pueden ser una fuente de duplicados. En particular, dos direcciones con dominios diferentes pueden redirigirse al mismo buzón, por ejemplo, en el caso de una empresa que ha cambiado el nombre y que ha mantenido el dominio anterior durante un periodo determinado: joe.doe@amce-co.com y joe.doe@acme-rebranded.com.
* **Preste atención durante las importaciones automáticas.** Ya sea de listas o de otras bases de datos, son elementos que se deben tener en cuenta al administrar perfiles. ¿Qué sucede cuando elimina o mueve un perfil en otra partición? Se puede volver a crear en la partición inicial mediante una importación automática, por ejemplo, cuando se realiza una orden de compra.
* **Los perfiles deben ordenarse en carpetas diferentes.**

De todas maneras, hay casos en los que los duplicados entre las diferentes particiones son normales. Por ejemplo, cuando se envían para terceros o entidades de empresa diferentes, es lógico que la misma persona sea receptora por diferentes motivos. Sin embargo, rara vez se pueden encontrar duplicados dentro de la misma partición.

## Cuarentenas {#quarantines}

Adobe Campaign administra una lista de direcciones en cuarentena. Los destinatarios cuyas direcciones están en cuarentena se excluyen de forma predeterminada durante el análisis de envío: no están segmentados.

La administración de cuarentena se detalla en [esta sección](../../sending/using/understanding-quarantine-management.md).

Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando el buzón está lleno o si la dirección no existe. En todos los casos, la cuarentena corresponde a las reglas específicas presentadas en [esta sección](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
