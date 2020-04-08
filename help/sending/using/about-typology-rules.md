---
title: Acerca de las tipologías y reglas de tipología
description: Descubra cómo funcionan las tipologías y reglas de tipología en el Adobe Campaign.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 396084934a41d103eecd6fe141c700c118000f75

---


# Acerca de las tipologías y reglas de tipología{#about-typology-rules}

Campaign Standard le permite vincular un mensaje a una **tipología** para comprobar si el mensaje es válido y cumple los criterios de calidad.

Las tipologías son conjuntos de **reglas de tipología** que se ejecutan durante la fase de análisis de mensajes. Permiten asegurarse de que los mensajes de correo electrónico siempre contengan determinados elementos (como un vínculo baja o una línea de asunto) o reglas de filtrado para excluir grupos del destinatario deseado (como suscriptores, competidoras o clientes no leales).

![](assets/typology_messagelink.png)

Las tipologías y reglas de tipología listas para usar están disponibles en Campaign Standard. Según sus necesidades, también puede crear nuevas reglas y agregarlas a las tipologías existentes o nuevas para vincularlas a sus mensajes.

Los pasos para crear y aplicar una tipología a los mensajes son:

1. Crear reglas de tipología (consulte [esta sección](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Create a typology and reference the rules you created into it (see [this section](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configure el envío para que utilice la tipología que ha creado (consulte [esta sección](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante la preparación del mensaje, los perfiles se excluyen cuando se cumplen los criterios. Puede comprobar los registros para controlar las exclusiones.
