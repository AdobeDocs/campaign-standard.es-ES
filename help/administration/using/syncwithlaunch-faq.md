---
solution: Campaign Standard
product: campaign
title: Preguntas más frecuentes sobre el flujo de trabajo técnico de sincronización con Launch
description: Preguntas frecuentes sobre el flujo de trabajo técnico de Launch.
audience: administration
content-type: reference
topic-tags: users-and-security
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---


# Preguntas más frecuentes sobre la sincronización de Adobe Experience Platform Launch {#syncwithlaunch-faq}

Puede importar propiedades móviles de Adobe Launch en Adobe Campaign Standard mediante el **[!UICONTROL Sync with Launch]** flujo de trabajo técnico dedicado. Para obtener más información, consulte esta [página](../../administration/using/technical-workflows.md)

La sección siguiente lista preguntas comunes sobre esta sincronización.

## Creé una propiedad en [!DNL Launch] (no administrador de Org-unit ALL). Mi aplicación está en estado Listo para configurar en Adobe Campaign, pero no puedo abrirla/configurarla. {#configuring-property}

Sólo el administrador de la unidad organizativa ALL puede configurar aplicaciones móviles en Adobe Campaign Standard. Una vez configurada, solo los usuarios de la unidad organizativa asignada pueden editar la variable
aplicación. Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## No puedo editar una aplicación móvil configurada en Adobe Campaign Standard y las aplicaciones móviles solo están en modo de lectura. {#read-mode-mobile-app}

Compruebe la unidad organizativa de la aplicación móvil en la sección **[!UICONTROL Access Authorization ]**. Solo los usuarios de la unidad organizativa asignada pueden editar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## Soy administrador de la unidad de organización ALL en Adobe Campaign Standard, pero no puedo configurar la aplicación móvil. {#org-unit-mobile}

Un administrador con la unidad de organización configurada en ALL debe tener derechos sobre todas las propiedades móviles en [!DNL Launch] para configurar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## Creé una propiedad móvil en [!DNL Launch] pero mi propiedad no está visible en Adobe Campaign Standard. {#visibility-mobile-property}

1. Compruebe que la extensión de Adobe Campaign Standard está instalada en la propiedad mobile en [!DNL Launch].

1. Compruebe que los extremos de la instancia están correctamente configurados en la extensión.

1. Compruebe que &#39;Launch_URL_Campaña&#39; o &#39;NmsServer_URL&#39; son correctos.

1. A continuación, compruebe que la sincronización entre [!DNL Launch] y Adobe Campaign se ha completado con el flujo de trabajo técnico **[!UICONTROL syncWithLaunch]**.

## ¿Cómo comprobar si se ha completado la sincronización entre Adobe Campaign y Launch? {#sync-campaign-launch}

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el flujo de trabajo **[!UICONTROL syncWithLaunch]**.

1. Compruebe si el flujo de trabajo ha finalizado sin errores.

1. Compruebe los registros en los que la sincronización del flujo de trabajo está habilitada y completada correctamente.

## Restablece la clave para una aplicación móvil configurada en Launch. ¿Cómo volver a configurar la clave en Launch? {#configuring-pkey}

1. Abra la propiedad mobile en Inicio de Adobe.

1. Configure una nueva URL en la extensión de Adobe Campaign Standard para la que se restableció el PKey.

1. Guárdela y permita la sincronización del flujo de trabajo entre Adobe Campaign y [!DNL Launch].

1. Una vez finalizada la sincronización, abra la propiedad mobile en [!DNL Launch].

1. Configure la dirección URL correcta en la extensión de Adobe Campaign Standard para la que se restableció PKey.

1. Guárdela y vuelva a ejecutar la sincronización del flujo de trabajo.

1. Sólo entonces la propiedad aparecerá en el estado **[!UICONTROL Ready to Configure]** en Adobe Campaign y ahora se puede configurar.

## Quiero configurar una propiedad móvil en Adobe Campaign. ¿Tendré que esperar a que el flujo de trabajo técnico se sincronice entre Adobe Launch y Adobe Campaign?

Puede realizar la ejecución inmediata del flujo de trabajo:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el flujo de trabajo **[!UICONTROL syncWithLaunch]**.

1. Haga clic en la actividad **[!UICONTROL Scheduler]** y seleccione **[!UICONTROL Immediate execution]**.
