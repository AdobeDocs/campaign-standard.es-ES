---
title: Promoción de un servicio
description: Utilice Adobe Campaign para promocionar un servicio y atraer a sus clientes a través de páginas de aterrizaje dedicadas, correos electrónicos o directamente en su sitio web.
audience: audiences
content-type: reference
topic-tags: managing-subscriptions
feature: Audiences
role: User
level: Intermediate
exl-id: c1f8770a-8b25-41db-aa52-828e181a563d
TQID: 'https://experienceleague.adobe.com/7WD3y15WK-NJeWZJFIv-crMu5UZ4m8V3KfYbamSY9WA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%
---
# Promoción de un servicio{#promoting-a-service}

Puede ofrecer suscripciones a un servicio de varias formas y ofrecer a los visitantes la capacidad de administrar su suscripción.

Puede utilizar Campaign para promocionar un servicio de las siguientes formas:

* [Insertando un vínculo de suscripción o de baja de servicio en un correo electrónico](../../designing/using/links.md#inserting-a-link).

* [Inserción de un vínculo a una página de aterrizaje de suscripción o de cancelación de suscripción en un correo electrónico](../../designing/using/links.md). En este caso, se debe hacer referencia directamente al servicio en las propiedades de las páginas de aterrizaje relacionadas (consulte [Vinculación de una página de aterrizaje a un servicio](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

  >[!NOTE]
  >
  >También es importante dar a los suscriptores la posibilidad de cancelar la suscripción. Para ello, inserte un servicio <b>Vínculo de baja</b> en el correo electrónico de confirmación (definido en las propiedades del servicio) enviado automáticamente a los nuevos suscriptores, así como en futuros correos electrónicos de la newsletter.

* Hacer que una página de aterrizaje de suscripción o de cancelación de suscripción esté disponible en un sitio web. Las direcciones URL que le proporcionan acceso a la página de aterrizaje deben especificar parámetros como el servicio asociado, así como el ID de perfil que accede a él. Este identificador se puede definir en los parámetros de la página de aterrizaje (consulte [Configuración de una página de aterrizaje](../../channels/using/configuring-landing-page.md)).
