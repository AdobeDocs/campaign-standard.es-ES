---
title: Archivado de mensajes en Adobe Campaign Standard
description: Obtenga información sobre cómo archivar correos electrónicos con Adobe Campaign Standard mediante una dirección de correo electrónico CCO.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Performance Monitoring
role: User
level: Intermediate
exl-id: 7bf380d7-195e-413d-b14e-85e78b07ba8b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 16%

---

# Archivado con CCO de correo electrónico{#archiving-emails}

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma a través del CCO del correo electrónico.

En concreto, si su organización necesita archivar todos los mensajes de correo electrónico salientes para fines de conformidad, puede activar esta capacidad. Permite enviar una copia oculta exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de la entrega) que debe especificar.

Una vez habilitado, debe activar el correo electrónico CCO desde la opción **[!UICONTROL Archive emails]** en la plantilla de envíos de correo electrónico.

>[!NOTE]
>
>Adobe Campaign no administra los archivos archivados. Esto permite enviar los mensajes que elija a una dirección específica, desde la que se pueden procesar y archivar mediante un sistema externo.

## Recommendations y limitaciones {#recommendations-and-limitations}

* Esta función es opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.
* La dirección de CCO que elija se debe proporcionar al equipo de Adobe que la configurará.
* Solo puede utilizar una dirección de correo electrónico CCO.
* Solo se tienen en cuenta los correos electrónicos enviados correctamente. Las devoluciones no lo son.
* Por motivos de privacidad, los correos electrónicos CCO deben procesarse mediante un sistema de archivado capaz de almacenar información de identificación personal (PII) de forma segura.
* Al crear una nueva plantilla de envíos, el correo electrónico CCO no está habilitado de forma predeterminada, aunque se haya adquirido la opción. Debe habilitarlo manualmente en cada plantilla de envíos donde desee utilizarlo.

>[!NOTE]
>
>Actualmente, los correos electrónicos archivados siguen enviándose mediante el módulo de archivado heredado, que utiliza un reenvío SMTP simple.

## Activando archivado de correo electrónico {#activating-email-archiving}

Una vez habilitado, el correo electrónico CCO se activa en la [plantilla de correo electrónico](../../start/using/marketing-activity-templates.md), a través de una opción dedicada:

1. Vaya a **Resources**, **Templates**, **Delivery templates**.
1. Duplique la plantilla **[!UICONTROL Send via email]** lista para usar.
1. Seleccione la plantilla duplicada.
1. Haga clic en el botón **[!UICONTROL Edit properties]** para editar las propiedades de la plantilla.
1. Expanda la sección **[!UICONTROL Send]**.
1. Marque la casilla **[!UICONTROL Archive emails]** para conservar una copia de todos los mensajes enviados para cada envío basado en esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.
