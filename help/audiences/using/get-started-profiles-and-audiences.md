---
solution: Campaign Standard
product: campaign
title: Introducción a perfiles y audiencias
description: Defina poblaciones segmentadas, seleccione audiencias, filtre destinatarios, recopile datos y actualice perfiles.
audience: audiences
content-type: reference
topic-tags: about-profiles-and-audiences
feature: Perfiles
role: User
level: Beginner
exl-id: b4de2f1a-09ec-486d-b1ef-66208cbe211f
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 25%

---

# Introducción a perfiles y audiencias{#about-profiles-and-audiences}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_segment.svg" width="60px"><p><a href="#segmenting-targeting">Segmentación y direccionamiento</a></p></td>
<td><img src="assets/do-not-localize/icon_permission.svg" width="60px"><p><a href="#permission">Permiso y consentimiento</a></p></td>
<td><img src="assets/do-not-localize/icon_privacy.svg" width="60px"><p><a href="#privacy">Cumplimiento de la privacidad</a></p></td></tr>
</table>

Los perfiles de cliente integrados de Campaign le permiten realizar un seguimiento de cada interacción con los clientes en canales múltiples dentro de una sola vista, lo que le permite enviar mensajes relevantes y personalizados a sus clientes.

Segmente la base de datos en audiencias para optimizar el destinatario de las campañas de marketing.

Administre el permiso y el consentimiento de los clientes con servicios y páginas de aterrizaje para configurar mecanismos de inclusión y exclusión sencillos.

## Segmentación y direccionamiento {#segmenting-targeting}

<img src="assets/do-not-localize/icon_segment.svg" width="60px">

Al crear campañas o mensajes, puede especificar el destinatario de los envíos seleccionando entre los contactos de la base de datos de Campaign, utilizando criterios simples o avanzados o seleccionando audiencias.

Identifique a los clientes de forma más eficaz en todos sus canales mediante **perfiles de cliente integrados**, **segmentos personalizados** y **grupos de control**. Cuando conoce sus clientes, intereses, información demográfica y preferencias de canal, es más fácil crear experiencias personalizadas que se noten.

Adobe Campaign crea perfiles de clientes enriquecidos en tiempo real, lo que le permite ofrecer ofertas más relevantes y personalizadas a medida que cambian las preferencias de sus clientes. Además, Adobe Campaign integra funciones avanzadas de análisis, administración de datos y segmentación para crear audiencias.

**** Los perfiles son contactos individuales almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil sea segmentado, cualificado y rastreado individualmente: Adobe Campaign puede rastrear cada interacción desde canales en línea y sin conexión y combinarla en un solo perfil.

**** Las audiencias son listas de perfiles creados basándose en criterios específicos o en un conjunto de criterios. Con los flujos de trabajo y el editor de consultas, puede crear audiencias a las que se dirigirán las campañas de marketing, en función de la información que tenga sobre ellos, sus actividades y su historial de marketing. Esto le permite filtrar perfiles suscritos, muestras o crear audiencias de destino según un número ilimitado de criterios.

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

Antes de empezar a enviar mensajes a un contacto, debe asegurarse de obtener su permiso. Si no es así, los correos electrónicos pueden marcarse como correo no deseado, lo que afectará a la capacidad de envío de la plataforma. Para asegurarse de crear una base de datos de perfiles saludable, asegúrese de que este permiso sea el primer paso.

Con Campaign, le recomendamos que utilice **mecanismos de inclusión y exclusión sencillos** a [services](../../audiences/using/creating-a-service.md) y [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md) para actualizar su información de contacto y ampliar la base de datos.

Si se proporcionan **vínculos de baja** en los mensajes, los perfiles podrán agregarse a la  de lista de bloqueados cuando sea necesario y, por lo tanto, mejorarse la capacidad de envío de la plataforma. Para obtener más información sobre lista de bloqueados administración de , consulte [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!IMPORTANT]
>
>Debe respetar la [directiva de uso aceptable de Adobe Campaign](https://www.adobe.com/legal/terms/aup.html).

Más información:

* [Acerca de las suscripciones](../../audiences/using/about-subscriptions.md)
* [Acerca de la inclusión y la exclusión en Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Cumplimiento de la privacidad {#privacy}

<img src="assets/do-not-localize/icon_privacy.svg" width="60px">

Adobe Campaign ofrece un conjunto de herramientas que le ayudarán con su **cumplimiento de la privacidad** para el RGPD, la CCPA y otras leyes de privacidad.

Obtenga más información en este [artículo](https://helpx.adobe.com/es/campaign/kb/campaign-privacy.html) sobre Administración de privacidad y las funciones que proporcionamos para administrar Derecho de acceso, Derecho a ser olvidado, consentimiento, retención de datos y funciones de usuario.

La privacidad y el consentimiento en Campaign y cómo administrarlos se presentan en [esta sección](../../start/using/privacy.md). Entérese también de las mejores prácticas recomendadas para ayudarle con el cumplimiento de las normas de privacidad al utilizar el servicio.

## Recursos adicionales

* [Ingesta de audiencias de Adobe Experience Platform en Campaign](../../integrating/using/ingest-aep-data.md)
* [Uso de Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Audiencias compartidas de Adobe](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)
* [Uso de flujos de trabajo para importar perfiles](../../automating/using/creating-import-workflow-templates.md)
* [Vídeos de perfiles y audiencias](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/profiles-and-audiences/creating-profiles-and-audiences.html)
