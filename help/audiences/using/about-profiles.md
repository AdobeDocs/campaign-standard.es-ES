---
title: Acerca de los perfiles
description: Los contactos se almacenan como perfiles en la base de datos de Campaign y se actualizan durante todo su ciclo de vida.
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: recipient,overview
feature: Profiles
role: User
level: Beginner
exl-id: 65310e00-567f-4fae-89bc-b1d5591fca77
TQID: https://experienceleague.adobe.com/8netKX93BsN9JxgyckV44tpKK5uPjFMrrnD8F4FCpJM
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 155
ht-degree: 74%

---

# Acerca de los perfiles{#about-profiles}

Adobe Campaign permite administrar contactos en todo el ciclo de vida: creación, importación, definición de público objetivo, seguimiento de acciones, actualizaciones, etc. Los contactos se almacenan en la base de datos como perfiles que contienen la información vinculada a ellos: apellidos, nombre, dirección, suscripciones, envíos, etc.

>[!NOTE]
>
>También hay perfiles disponibles mediante la API de Adobe Campaign Standard. Para obtener más información, consulte la [documentación dedicada](../../api/using/retrieving-profiles.md).

![](assets/marketing_history.png)

Al crear campañas, puede definir el destinatario de los envíos seleccionando perfiles según criterios simples o avanzados. Técnicamente, un perfil es una entrada en la base de datos que contiene toda la información necesaria para segmentar, calificar y rastrear comportamientos.

Un perfil puede ser: un cliente, un cliente potencial, una persona suscrita a un boletín, un destinatario, un usuario o cualquier otra denominación según la organización. Para definir varios tipos de perfiles, utilice [dimensiones de segmentación](../../automating/using/query.md#targeting-dimensions-and-resources).
