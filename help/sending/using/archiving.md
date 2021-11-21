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

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma a través del correo electrónico CCO.

En concreto, si su organización necesita archivar todos los mensajes de correo electrónico salientes para que sean compatibles, puede habilitar esta capacidad. Permite enviar una copia oculta exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de la entrega) que debe especificar.

Una vez activado, debe activar el correo electrónico CCO desde el **[!UICONTROL Archive emails]** en la plantilla de envío de correo electrónico.

>[!NOTE]
>
>Adobe Campaign no administra los archivos archivados. Permite enviar los mensajes que elija a una dirección específica, desde la que se pueden procesar y archivar mediante un sistema externo.

## Recommendations y limitaciones {#recommendations-and-limitations}

* Esta función es opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.
* La dirección de CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.
* Solo puede utilizar una dirección de correo electrónico CCO.
* Solo se tienen en cuenta los correos electrónicos enviados correctamente. Las devoluciones no lo son.
* Por motivos de privacidad, los correos electrónicos CCO deben ser procesados por un sistema de archiving capaz de almacenar información personal segura (PII).
* Al crear una nueva plantilla de envío, el correo electrónico CCO no está habilitado de forma predeterminada, aunque se haya comprado la opción. Debe activarlo manualmente en cada plantilla de envío donde desee utilizarla.

>[!NOTE]
>
>Actualmente, los correos electrónicos archivados siguen siendo enviados por el módulo de archivado heredado que utiliza una simple retransmisión SMTP.

## Activación del archivado de correo electrónico {#activating-email-archiving}

Una vez habilitado, el correo electrónico CCO se activa en la variable [plantilla de correo electrónico](../../start/using/marketing-activity-templates.md), mediante una opción dedicada:

1. Vaya a **Resources**, **Templates**, **Delivery templates**.
1. Duplicación de elementos predeterminados **[!UICONTROL Send via email]** plantilla.
1. Seleccione la plantilla duplicada.
1. Haga clic en el **[!UICONTROL Edit properties]** para editar las propiedades de la plantilla.
1. Expanda el **[!UICONTROL Send]** para obtener más información.
1. Marque la **[!UICONTROL Archive emails]** para mantener una copia de todos los mensajes enviados para cada envío basado en esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.
