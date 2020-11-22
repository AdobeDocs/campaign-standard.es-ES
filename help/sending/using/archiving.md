---
solution: Campaign Standard
product: campaign
title: Archivado de mensajes en Adobe Campaign Standard
description: Obtenga información sobre cómo archivar correos electrónicos con Adobe Campaign Standard mediante una dirección de correo electrónico CCO.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 15%

---


# Archivado con Email BCC{#archiving-emails}

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde su plataforma a través de Email BCC.

En particular, si su organización necesita archivar todos los mensajes de correo electrónico salientes para cumplir con la normativa, puede habilitar esta capacidad. Le permite enviar una copia oculta exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de envío) que debe especificar.

Una vez habilitada, debe activar Email BCC desde la **[!UICONTROL Archive emails]** opción de la Plantilla de envíos de correo electrónico.

>[!NOTE]
>
>Adobe Campaign no administra los archivos archivados. Le permite enviar los mensajes de su elección a una dirección dedicada, desde donde se pueden procesar y archivar usando un sistema externo.

## Recommendations y limitaciones {#recommendations-and-limitations}

* Esta función es opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.
* La dirección de CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.
* Solo puede usar una dirección de correo electrónico CCO.
* Solo se tienen en cuenta los correos electrónicos enviados correctamente. Las devoluciones no lo son.
* Por razones de privacidad, los correos electrónicos CCO deben ser procesados por un sistema de archiving capaz de almacenar información personal (PII) de manera segura.
* Al crear una nueva Plantilla de envíos, Email BCC no está habilitado de forma predeterminada, aunque la opción se haya adquirido. Debe activarlo manualmente en cada Plantilla de envíos donde desee utilizarla.

>[!NOTE]
>
>Actualmente, los mensajes de correo electrónico archivados no se pueden enviar con el MTA mejorado de Adobe Campaign, incluso si ya se ha actualizado al MTA mejorado.

## Activación del archivado de correo electrónico {#activating-email-archiving}

Una vez activado, Email BCC se activa en la plantilla [de](../../start/using/marketing-activity-templates.md)correo electrónico mediante una opción dedicada:

1. Vaya a **Resources**, **Templates**, **Delivery templates**.
1. Duplicado la plantilla lista para usar **[!UICONTROL Send via email]** .
1. Seleccione la plantilla duplicada.
1. Click the **[!UICONTROL Edit properties]** button to edit the template&#39;s properties.
1. Expanda la **[!UICONTROL Send]** sección.
1. Marque la **[!UICONTROL Archive emails]** casilla para guardar una copia de todos los mensajes enviados para cada envío en función de esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.