---
title: Introducción a perfiles y audiencias
description: Defina poblaciones segmentadas, seleccione audiencias, filtre destinatarios, recopile datos y actualice perfiles.
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Profiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '604'
ht-degree: 25%

---

# Introducción a perfiles y audiencias{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">Segmentación y direccionamiento</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">Permiso y consentimiento</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">Cumplimiento de privacidad</a></p></td></tr>
</table>

Los perfiles de cliente integrados de Campaign le permiten realizar un seguimiento de cada interacción con los clientes en canales múltiples dentro de una sola vista, lo que le permite enviar mensajes relevantes y personalizados a sus clientes.

Segmente la base de datos en audiencias para optimizar el destinatario de las campañas de marketing.

Administre el permiso y el consentimiento de los clientes con servicios y páginas de aterrizaje para configurar mecanismos de inclusión y exclusión sencillos.

## Segmentación y direccionamiento {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

Al crear campañas o mensajes, puede especificar el destinatario de los envíos seleccionando entre los contactos de la base de datos de Campaign, utilizando criterios simples o avanzados o seleccionando audiencias.

Identifique a los clientes de forma más eficaz en todos los canales mediante **perfiles de cliente integrados**, **segmentos personalizados** y **grupos de control**. Cuando conoce sus clientes, intereses, características demográficas y preferencias de canal, es más fácil crear experiencias personalizadas que pasen desapercibidas.

Adobe Campaign crea perfiles de clientes enriquecidos en tiempo real, lo que le permite ofrecer ofertas más relevantes y personalizadas a medida que cambian las preferencias de sus clientes. Además, Adobe Campaign integra funciones avanzadas de análisis, administración de datos y segmentación para crear audiencias.

**Perfiles** son contactos individuales almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil se establezca como objetivo, cualificado y rastreado individualmente: Adobe Campaign puede rastrear cada interacción desde canales en línea y sin conexión y combinarla en un único perfil.

**Audiencias** son listas de perfiles creadas según un criterio específico o un conjunto de criterios. Con los flujos de trabajo y el editor de consultas, puede construir audiencias a las que se dirigen las campañas de marketing, según la información que tenga sobre ellas, sus actividades y su historial de marketing. Esto le permite filtrar perfiles suscritos, tomar muestras o crear audiencias de destino con un número ilimitado de criterios.

Más información:

* [Acerca de los perfiles](../../audiences/using/about-profiles.md)
* [Perfiles activos](../../audiences/using/active-profiles.md)
* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Enriquecimiento de la base de datos de Campaign](../../audiences/using/enriching-campaign-database.md)
* [Acerca de las audiencias](../../audiences/using/about-audiences.md)
* [Selección de una audiencia en un mensaje](../../audiences/using/selecting-an-audience-in-a-message.md)
* [Adición de un grupo de control](../../sending/using/control-group.md)

## Permiso y consentimiento {#permission}

<img src="assets/do-not-localize/icon_permission.svg"  width="60px">

Antes de empezar a enviar mensajes a un contacto, debe asegurarse de obtener su permiso. Si no es así, es posible que los correos electrónicos se marquen como correo no deseado, lo que afectará a la capacidad de envío de la plataforma. Para asegurarse de crear una base de datos de perfiles en buen estado, proteja este permiso como primer paso.

Con Campaign, le recomendamos que utilice **mecanismos de inclusión y exclusión sencillos** mediante [servicios](../../audiences/using/creating-a-service.md), y [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md) para actualizar su información de contacto y ampliar su base de datos.

Proporcionar **vínculos de baja** en sus mensajes, permitirá que se añadan perfiles a la lista de bloqueados de la, cuando sea necesario, y, por lo tanto, para mejorar la capacidad de envío de la plataforma. Para obtener más información sobre la administración de la lista de bloqueados de la, consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!IMPORTANT]
>
>Se le exige que respete el [Política de uso aceptable de Adobe Campaign](https://www.adobe.com/legal/terms/aup.html).

Más información:

* [Acerca de las suscripciones](../../audiences/using/about-subscriptions.md)
* [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Cumplimiento de privacidad {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign ofrece un conjunto de herramientas para ayudarle con su **Cumplimiento de privacidad** para el RGPD, la CCPA y otras leyes de privacidad.

Obtenga más información en esta [este artículo](https://helpx.adobe.com/es/campaign/kb/campaign-privacy.html) Acerca de la administración de la privacidad y las funciones que proporcionamos para administrar el derecho de acceso, el derecho a ser olvidado, el consentimiento, la retención de datos y las funciones de usuario.

La privacidad y el consentimiento en Campaign y cómo administrarlos se presentan en [esta sección](../../start/using/privacy.md). Entérese también de las mejores prácticas recomendadas para ayudarle con el cumplimiento de las normas de privacidad al utilizar el servicio.

## Recursos adicionales

* [Ingesta de audiencias de Adobe Experience Platform en Campaign](../../integrating/using/ingest-aep-data.md)
* [Uso de Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Adobe de audiencias compartidas](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [Uso de flujos de trabajo para importar perfiles](../../automating/using/creating-import-workflow-templates.md)
* [Vídeos de perfiles y audiencias](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
