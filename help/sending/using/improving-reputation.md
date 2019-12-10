---
title: Mejora de su reputación con Adobe Campaign Standard
description: Obtenga información sobre cómo mejorar su reputación con Adobe Campaign Standard administrando direcciones de correo electrónico y cuarentena duplicadas.
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


# Mejorar su reputación{#improving-reputation}

Para evitar que los destinatarios se agoten, elimine del objetivo las direcciones de correo electrónico duplicadas. Este paso protege su reputación de envío y garantiza una buena gestión de cuarentena. Adobe Campaign ofrece las herramientas necesarias para implementar estas recomendaciones y evitar el riesgo de ser bloqueado por el ISP.

A continuación encontrará detalles sobre la administración de duplicados y cuarentena.

## Duplicados {#duplicates}

El tener direcciones de correo electrónico duplicadas puede tener varias consecuencias:
* El mismo mensaje se envía más de una vez. Incluso si Campaign realiza un procedimiento de desduplicación de forma predeterminada antes de enviar, no hay nada que detenga el mismo mensaje enviado por acciones diferentes que tengan el mismo contenido cuando se divide un objetivo.
* Solicitudes de cancelación de suscripción no aceptadas. Si un destinatario cancela la suscripción después de recibir un mensaje, su perfil duplicado seguirá siendo apto para futuros mensajes.

Además de este paso secundario de los procedimientos de inclusión, esta situación probablemente llevará a los usuarios a considerar los mensajes como spam y a activar un procedimiento de lista negra en el ISP.

Debe tener especial cuidado al realizar operaciones en la base de datos. Para evitar la mayor cantidad posible de duplicados, deben llevarse a cabo las siguientes acciones:
* **Las importaciones deben configurarse meticulosamente.** Esto es particularmente importante a la hora de elegir la clave de reconciliación.
* **Tenga cuidado al modificar direcciones de correo electrónico.** Las direcciones de correo electrónico cambiadas también pueden ser una fuente de duplicados. En particular, dos direcciones con dominios diferentes pueden enrutarse al mismo buzón, por ejemplo, en el caso de una empresa que ha cambiado el nombre y que ha mantenido el dominio anterior durante un período de tiempo determinado: joe.doe@amce-co.com y joe.doe@acme-rebranded.com.
* **Preste atención durante las importaciones automáticas.** Ya sea de listas o de otras bases de datos, son elementos que se deben tener en cuenta al administrar perfiles. ¿Qué sucede cuando elimina o mueve un perfil en otra partición? Se puede volver a crear en la partición inicial mediante una importación automática, por ejemplo, cuando se realiza una orden de compra.
* **Los perfiles deben ordenarse en distintas carpetas.**

Hay, en todo caso, casos en los que los duplicados entre las diferentes particiones son normales. Por ejemplo, cuando se envían para terceros o entidades de empresa diferentes, es lógico que la misma persona sea receptora por diferentes motivos. Sin embargo, rara vez es normal encontrar duplicados dentro de la misma partición.

## Cuarantines {#quarantines}

Adobe Campaign administra una lista de direcciones en cuarentena. Los destinatarios cuyas direcciones están en cuarentena se excluyen de forma predeterminada durante el análisis de entrega: no están segmentados.

La administración de cuarentena se detalla en [esta sección](../../sending/using/understanding-quarantine-management.md).

Una dirección de correo electrónico se puede poner en cuarentena, por ejemplo, cuando la bandeja de entrada está llena o si la dirección no existe. En todos los casos, la cuarentena corresponde a las reglas específicas presentadas en [esta sección](../../sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).
