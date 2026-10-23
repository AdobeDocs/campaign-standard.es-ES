---
title: Información sobre las tipologías y reglas de tipología
description: Descubra cómo funcionan las tipologías y reglas de tipología en Adobe Campaign.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
context-tags: typology,overview;typologyRule,main;typologyRule,overview
feature: Typology Rules
role: User
level: Intermediate
exl-id: dff72856-d28c-45c4-a073-12cc25f51f23
TQID: 'https://experienceleague.adobe.com/fFTJTgKfIhII-D6pefx9hqnX3a022odFZS5AAmNK1Ao'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c858a28b-ea19-49b0-8d48-828717fad89c
    internal-label: Prepare and test messages
subfeature_v2:
  - id: e5fb657f-3c0a-4fcc-9980-3589a23ab4de
    internal-label: Typology rules
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '193'
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
1. Durante la preparación del mensaje, los perfiles se excluyen cuando se cumplen los criterios. Puede comprobar los registros para monitorizar las exclusiones.
