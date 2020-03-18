---
title: Archivado de mensajes en Adobe Campaign Standard
description: Obtenga información sobre cómo archivar correos electrónicos con Adobe Campaign Standard mediante una dirección de correo electrónico CCO.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2bf1f8acb581645a6f89f50443a8d9a49d8acaf1

---


# Archivado con Email BCC{#archiving-emails}

Puede configurar Adobe Campaign para que conserve una copia de los correos electrónicos enviados desde su plataforma a través de Email BCC.

En particular, si su organización necesita archivar todos los mensajes de correo electrónico salientes para cumplir con la normativa, puede habilitar esta capacidad. Le permite enviar una copia oculta exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de la entrega) que debe especificar.

Una vez habilitada, debe activar Email BCC desde la **[!UICONTROL Archive emails]** opción de la plantilla de envío de correo electrónico.

>[!NOTE]
>
>La propia Adobe Campaign no administra los archivos archivados. Le permite enviar los mensajes de su elección a una dirección dedicada, desde donde se pueden procesar y archivar usando un sistema externo.

## Recomendaciones y limitaciones {#recommendations-and-limitations}

* Esta función es opcional. Compruebe el acuerdo de licencia y póngase en contacto con el administrador de cuentas para activarlo.
* La dirección de CCO que elija debe proporcionarse al equipo de Adobe que la configurará por usted.
* Solo puede usar una dirección de correo electrónico CCO.
* Solo se tienen en cuenta los correos electrónicos enviados correctamente. Las devoluciones no lo son.
* Por razones de privacidad, los correos electrónicos CCO deben ser procesados por un sistema de archiving capaz de almacenar información personal (PII) de manera segura.
* Al crear una nueva plantilla de entrega, Email BCC no está habilitado de forma predeterminada, aunque la opción se haya adquirido. Debe habilitarlo manualmente en cada plantilla de envío donde desee utilizarla.

>[!NOTE]
>
>Actualmente, los mensajes de correo electrónico archivados no se pueden enviar con el MTA [mejorado de](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)Adobe Campaign, aunque ya se haya actualizado al MTA mejorado.

## Activación del archivado de correo electrónico {#activating-email-archiving}

Una vez activado, Email BCC se activa en la plantilla [de](../../start/using/marketing-activity-templates.md)correo electrónico mediante una opción dedicada:

1. Go to **Resources** > **Templates** > **Delivery templates**.
1. Duplique la plantilla lista para usar **[!UICONTROL Send via email]** .
1. Seleccione la plantilla duplicada.
1. Haga clic en el **[!UICONTROL Edit properties]** botón para editar las propiedades de la plantilla.
1. Expanda la **[!UICONTROL Send]** sección.
1. Marque la **[!UICONTROL Archive emails]** casilla para guardar una copia de todos los mensajes enviados para cada envío en función de esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>If the emails sent to the BCC address are opened and clicked through, this will be taken into account in the **[!UICONTROL Total opens]** and **[!UICONTROL Clicks]** from the send analysis, which could cause some miscalculations.