---
title: Preguntas frecuentes sobre el flujo de trabajo técnico Sincronización con Launch
description: Preguntas frecuentes sobre el flujo de trabajo técnico de Launch.
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 2%

---

# Preguntas frecuentes sobre la sincronización de Adobe Launch {#syncwithlaunch-faq}

Puede importar propiedades móviles de Launch de Adobe en Adobe Campaign Standard a través del flujo de trabajo técnico dedicado de **[!UICONTROL Sync with Launch]** . Para obtener más información, consulte esta [página](../../administration/using/technical-workflows.md)

La sección siguiente enumera preguntas comunes sobre esta sincronización.

## Creé una propiedad en [!DNL Launch] (no administrador de la unidad de organización ALL). Mi aplicación está en estado Preparado para configurar en Adobe Campaign, pero no puedo abrirla ni configurarla. {#configuring-property}

Solo el administrador de la unidad organizativa ALL puede configurar las aplicaciones móviles en Adobe Campaign Standard. Una vez configurada, solo los usuarios de la unidad organizativa asignada pueden editar la variable
aplicación. Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## No puedo editar una aplicación móvil configurada en Adobe Campaign Standard y las aplicaciones móviles solo están en modo de lectura. {#read-mode-mobile-app}

Compruebe la unidad organizativa de la aplicación móvil en la sección **[!UICONTROL Access Authorization]** . Solo los usuarios de la unidad organizativa asignada pueden editar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## Soy administrador de la unidad organizativa ALL en Adobe Campaign Standard, pero no puedo configurar la aplicación móvil. {#org-unit-mobile}

Un administrador con la unidad de organización configurada en ALL debe tener derechos sobre todas las propiedades móviles en [!DNL Launch] para configurar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte esta [página](../../administration/using/organizational-units.md).

## Creé una propiedad móvil en [!DNL Launch] pero mi propiedad no es visible en Adobe Campaign Standard. {#visibility-mobile-property}

1. Compruebe que la extensión de Adobe Campaign Standard esté instalada en la propiedad móvil en [!DNL Launch].

1. Compruebe que los extremos de la instancia estén correctamente configurados en la extensión de .

1. Compruebe que &quot;Launch_URL_Campaign&quot; o &quot;NmsServer_URL&quot; sean correctos.

1. A continuación, compruebe que la sincronización entre [!DNL Launch] y Adobe Campaign se complete con el flujo de trabajo técnico **[!UICONTROL syncWithLaunch]**.

## ¿Cómo se comprueba si se ha completado la sincronización entre Adobe Campaign y Launch? {#sync-campaign-launch}

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el flujo de trabajo **[!UICONTROL syncWithLaunch]** .

1. Compruebe si el flujo de trabajo ha finalizado sin errores.

1. Compruebe en los registros que la sincronización del flujo de trabajo está habilitada y completada correctamente.

## Restablece la clave para una aplicación móvil configurada en Launch. ¿Cómo volver a configurar la clave en Launch? {#configuring-pkey}

1. Abra la propiedad móvil en Adobe Launch.

1. Establezca una nueva URL en la extensión de Adobe Campaign Standard para la que se restableció el PKey.

1. Guárdelo y deje que el flujo de trabajo se sincronice entre Adobe Campaign y [!DNL Launch].

1. Una vez finalizada la sincronización, abra la propiedad móvil en [!DNL Launch].

1. Establezca la dirección URL correcta en la extensión de Adobe Campaign Standard para la que se restableció PKey.

1. Guárdelo y permita que la sincronización del flujo de trabajo se ejecute de nuevo.

1. Solo entonces la propiedad aparecerá en estado **[!UICONTROL Ready to Configure]** en Adobe Campaign y ahora se puede configurar.

## Quiero configurar una propiedad móvil en Adobe Campaign. ¿Tendré que esperar para que el flujo de trabajo técnico se sincronice entre Adobe Launch y Adobe Campaign?

Puede realizar la ejecución inmediata del flujo de trabajo:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el flujo de trabajo **[!UICONTROL syncWithLaunch]** .

1. Haga clic en la actividad **[!UICONTROL Scheduler]** y seleccione **[!UICONTROL Immediate execution]**.
