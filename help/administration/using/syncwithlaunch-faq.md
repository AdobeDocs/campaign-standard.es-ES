---
title: Preguntas más frecuentes sobre el flujo de trabajo técnico de sincronización con Launch
description: Preguntas frecuentes sobre el flujo de trabajo técnico de Launch.
page-status-flag: never-activated
uuid: 4f538452-cc67-4e03-9e2f-2d9eecc081c7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 54028f63-c9ca-4397-a079-e27e0cfdebf6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6c5cf90211451587537b9a6121430fc4f352384c
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 1%

---


# Preguntas más frecuentes sobre el flujo de trabajo técnico de sincronización con Launch {#syncwithlaunch-faq}

Puede importar las propiedades móviles de Adobe Launch en Adobe Campaign Standard mediante el flujo de trabajo técnico **[!UICONTROL Sync with Launch]** dedicado. Para obtener más información, consulte esta [página](../../administration/using/technical-workflows.md)

La sección siguiente lista preguntas comunes sobre esta sincronización.

>[!NOTE]
>
>Deberá enviar un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para que el flujo de trabajo **[!UICONTROL syncWithLaunch]** técnico esté habilitado en la instancia de Campaña.

## Creé una propiedad en [!DNL Launch] (no administrador de la unidad de organización ALL). Mi aplicación está en estado Listo para configurar en Adobe Campaign, pero no puedo abrirla/configurarla. {#configuring-property}

Sólo el administrador de la unidad organizativa ALL puede configurar aplicaciones móviles en Adobe Campaign Standard. Una vez configurada, solo los usuarios de la unidad organizativa asignada pueden editar la aplicación. For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## No puedo editar una aplicación móvil configurada en Adobe Campaign Standard y las aplicaciones móviles solo están en modo de lectura. {#read-mode-mobile-app}

Compruebe la unidad organizativa de la aplicación móvil en la **[!UICONTROL Access Authorization ]** sección . Solo los usuarios de la unidad organizativa asignada pueden editar la aplicación móvil.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## Soy administrador con TODAS las unidades de organización en Adobe Campaign Standard, pero no puedo configurar aplicaciones móviles. {#org-unit-mobile}

Un administrador con la unidad de organización establecida en ALL debe tener derechos sobre todas las propiedades móviles en [!DNL Launch] para configurar la aplicación móvil.

For more information on organizational unit, refer to this [page](../../administration/using/organizational-units.md).

## He creado una propiedad móvil en [!DNL Launch] pero mi propiedad no está visible en Adobe Campaign Standard. {#visibility-mobile-property}

1. Compruebe que la extensión de Adobe Campaign Standard está instalada en la propiedad mobile de [!DNL Launch].

1. Compruebe que los extremos de la instancia están correctamente configurados en la extensión.

1. Compruebe que &#39;Launch_URL_Campaña&#39; o &#39;NmsServer_URL&#39; son correctos.

1. A continuación, compruebe que la sincronización entre [!DNL Launch] y Adobe Campaign se ha completado con el flujo de trabajo **[!UICONTROL syncWithLaunch]** técnico.

## ¿Cómo comprobar si se ha completado la sincronización entre Adobe Campaign y Launch? {#sync-campaign-launch}

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el **[!UICONTROL syncWithLaunch]** flujo de trabajo.

1. Compruebe si el flujo de trabajo ha finalizado sin errores.

1. Compruebe los registros en los que la sincronización del flujo de trabajo está habilitada y completada correctamente.

## Restablece la clave para una aplicación móvil configurada en Launch. ¿Cómo volver a configurar la clave en Launch? {#configuring-pkey}

1. Abra la propiedad mobile en Adobe Launch.

1. Configure una nueva dirección URL en la extensión de Adobe Campaign Standard para la que se restableció el valor PKey.

1. Guárdela y permita que el flujo de trabajo se sincronice entre Adobe Campaign y [!DNL Launch].

1. Una vez finalizada la sincronización, abra la propiedad mobile en [!DNL Launch].

1. Establezca la dirección URL correcta en la extensión de Adobe Campaign Standard para la que se restableció PKey.

1. Guárdela y vuelva a ejecutar la sincronización del flujo de trabajo.

1. Sólo entonces la propiedad aparecerá en **[!UICONTROL Ready to Configure]** estado en Adobe Campaign y ahora se puede configurar.

## Quiero configurar una propiedad móvil en Adobe Campaign. ¿Tendré que esperar a que el flujo de trabajo técnico se sincronice entre Adobe Launch y Adobe Campaign?

Puede realizar la ejecución inmediata del flujo de trabajo:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el **[!UICONTROL syncWithLaunch]** flujo de trabajo.

1. Haga clic en la **[!UICONTROL Scheduler]** actividad y seleccione **[!UICONTROL Immediate execution]**.
