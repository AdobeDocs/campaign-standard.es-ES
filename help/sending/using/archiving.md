---
solution: Campaign Standard
product: campaign
title: Archivado de mensajes en Adobe Campaign Standard
description: Obtenga información sobre cómo archivar correos electrónicos con Adobe Campaign Standard mediante una dirección de correo electrónico CCO.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
feature: Supervisión del rendimiento
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 16%

---


# Archivado con Email BCC{#archiving-emails}

Puede configurar Adobe Campaign para que mantenga una copia de los correos electrónicos enviados desde la plataforma a través del correo electrónico CCO.

En concreto, si su organización necesita archivar todos los mensajes de correo electrónico salientes para que sean compatibles, puede habilitar esta capacidad. Permite enviar una copia oculta exacta de los mensajes enviados correspondientes a una dirección de correo electrónico CCO (invisible para los destinatarios de la entrega) que debe especificar.

Una vez activado, debe activar el correo electrónico CCO desde la opción **[!UICONTROL Archive emails]** en la plantilla de envío de correo electrónico.

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
>Actualmente, los correos electrónicos archivados no se pueden enviar con el MTA mejorado de Adobe Campaign.

## Activación del archivado de correo electrónico {#activating-email-archiving}

Una vez activado, el correo electrónico CCO se activa en la [plantilla de correo electrónico](../../start/using/marketing-activity-templates.md) mediante una opción dedicada:

1. Vaya a **Resources**, **Templates**, **Delivery templates**.
1. Duplique la plantilla predeterminada **[!UICONTROL Send via email]** .
1. Seleccione la plantilla duplicada.
1. Haga clic en el botón **[!UICONTROL Edit properties]** para editar las propiedades de la plantilla.
1. Expanda la sección **[!UICONTROL Send]** .
1. Marque la casilla **[!UICONTROL Archive emails]** para mantener una copia de todos los mensajes enviados para cada envío basado en esta plantilla.

   ![](assets/email_archiving.png)

>[!NOTE]
>
>Si se abren y se hace clic en los correos electrónicos enviados a la dirección de CCO, esto se tiene en cuenta en el cálculo de **[!UICONTROL Total opens]** y **[!UICONTROL Clicks]** en el análisis de envío, lo cual podría provocar algunos cálculos erróneos.