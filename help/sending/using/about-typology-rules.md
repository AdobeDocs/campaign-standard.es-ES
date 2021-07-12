---
solution: Campaign Standard
product: campaign
title: Información sobre las tipologías y reglas de tipología
description: Descubra cómo funcionan las tipologías y reglas de tipología en Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Reglas de tipología
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 100%

---

# Acerca de las tipologías y reglas de tipología{#about-typology-rules}

Campaign Standard le permite vincular un mensaje a una **tipología** para comprobar si el mensaje es válido y cumple con los criterios de calidad.

Las tipologías son conjuntos de **reglas de tipología** que se ejecutan durante la fase de análisis de mensajes. Le permiten asegurarse de que los mensajes de correo electrónico siempre contengan determinados elementos (como un vínculo de baja o una línea de asunto) o reglas de filtrado para excluir grupos de los destinatarios deseados (como suscriptores que se han dado de baja, competidoras o clientes que no sean fieles).

![](assets/typology_messagelink.png)

Las tipologías y reglas de tipología listas para usar están disponibles en Campaign Standard. Según sus necesidades, también puede crear nuevas reglas y añadirlas a las tipologías existentes o nuevas para vincularlas a sus mensajes.

Los pasos para crear y aplicar una tipología a los mensajes son:

1. Crear reglas de tipología (consulte [esta sección](../../sending/using/managing-typology-rules.md#creating-a-typology-rule)).
1. Cree una tipología y haga referencia a las reglas que creó en ella (consulte [esta sección](../../sending/using/managing-typologies.md#creating-a-typology)).
1. Configure el envío para que utilice la tipología que ha creado (consulte [esta sección](../../sending/using/managing-typologies.md#applying-typologies-to-messages)).
1. Durante la preparación del mensaje, los perfiles se excluyen cuando se cumplen los criterios. Puede comprobar los registros para controlar las exclusiones.
