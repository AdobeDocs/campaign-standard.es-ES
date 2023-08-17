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
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Promoción de un servicio{#promoting-a-service}

Puede ofrecer suscripciones a un servicio de varias formas y ofrecer a los visitantes la capacidad de administrar su suscripción.

Puede utilizar Campaign para promocionar un servicio de las siguientes formas:

* [Inserción de un vínculo de suscripción o baja de suscripción a un servicio en un correo electrónico](../../designing/using/links.md#inserting-a-link).

* [Inserción de un vínculo a una página de aterrizaje de suscripción o de baja en un correo electrónico](../../designing/using/links.md). En este caso, se debe hacer referencia directamente al servicio en las propiedades de las páginas de aterrizaje relacionadas (consulte [Vinculación de una página de aterrizaje a un servicio](../../channels/using/configuring-landing-page.md#linking-a-landing-page-to-a-service)).

  >[!NOTE]
  >
  >También es importante dar a los suscriptores la posibilidad de cancelar la suscripción. Para ello, inserte un servicio <b>Vínculo de baja</b> en el correo electrónico de confirmación (definido en las propiedades del servicio) enviado automáticamente a los nuevos suscriptores, así como en futuros correos electrónicos de newsletter.

* Hacer que una página de aterrizaje de suscripción o de cancelación de suscripción esté disponible en un sitio web. Las direcciones URL que le proporcionan acceso a la página de aterrizaje deben especificar parámetros como el servicio asociado, así como el ID de perfil que accede a él. Este ID se puede definir en los parámetros de página de aterrizaje (consulte [Configuración de una página de aterrizaje](../../channels/using/configuring-landing-page.md)).
