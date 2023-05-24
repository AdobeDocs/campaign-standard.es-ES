---
title: Preguntas frecuentes sobre el flujo de trabajo técnico Sincronizar con Launch
description: Preguntas comunes sobre el flujo de trabajo técnico de Adobe Launch
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: aaaceb3a-5e54-47da-9be4-b70747282830
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 2%

---

# Preguntas frecuentes sobre la sincronización de etiquetas en Adobe Experience Platform {#syncwithlaunch-faq}

Puede importar propiedades móviles de etiquetas en Adobe Campaign Standard a través del **[!UICONTROL Sync with Launch]** flujo de trabajo técnico dedicado. Para obtener más información, consulte esta [página](../../administration/using/technical-workflows.md)

La sección siguiente enumera preguntas comunes sobre esta sincronización.

## He creado una propiedad de etiqueta (que no es administrador de Org-unit ALL). Mi aplicación está en estado Listo para configurar en Adobe Campaign, pero no puedo abrirla o configurarla. {#configuring-property}

Solo el administrador de la unidad organizativa ALL puede configurar aplicaciones móviles en Adobe Campaign Standard. Una vez configurada, solo los usuarios de la unidad organizativa asignada pueden editar la aplicación. Para obtener más información sobre la unidad organizativa, consulte [página](../../administration/using/organizational-units.md).

## No puedo editar una aplicación móvil configurada en Adobe Campaign Standard y las aplicaciones móviles están solo en modo de lectura. {#read-mode-mobile-app}

Compruebe la unidad organizativa de la aplicación móvil en **[!UICONTROL Access Authorization]** sección. Solo los usuarios de la unidad organizativa asignada pueden editar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte [página](../../administration/using/organizational-units.md).

## Soy administrador con la unidad organizativa ALL en Adobe Campaign Standard, pero no puedo configurar la aplicación móvil. {#org-unit-mobile}

Un administrador con la unidad organizativa configurada como TODO debe tener derechos sobre todas las propiedades móviles de etiquetas para configurar la aplicación móvil.

Para obtener más información sobre la unidad organizativa, consulte [página](../../administration/using/organizational-units.md).

## He creado una propiedad móvil de etiqueta, pero mi propiedad no es visible en Adobe Campaign Standard. {#visibility-mobile-property}

1. Compruebe que la extensión de Adobe Campaign Standard esté instalada en la propiedad móvil en la IU de recopilación de datos.

1. Compruebe que los puntos finales de instancia están correctamente configurados en la extensión de.

1. Compruebe que Launch_URL_Campaign o NmsServer_URL sean correctos.

1. A continuación, compruebe que la sincronización se haya completado con **[!UICONTROL syncWithLaunch]** flujo de trabajo técnico.

## ¿Cómo se comprueba si se ha completado la sincronización entre Adobe Campaign y Etiquetas en Adobe Experience Platform? {#sync-campaign-launch}

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el **[!UICONTROL syncWithLaunch]** flujo de trabajo.

1. Compruebe si el flujo de trabajo ha finalizado sin errores.

1. Compruebe en los registros que la sincronización del flujo de trabajo está habilitada y completada correctamente.

## Restablecí la clave para una aplicación móvil de etiquetas configurada. ¿Cómo volver a configurar la clave en la IU de recopilación de datos? {#configuring-pkey}

1. Abra la propiedad móvil en la interfaz de usuario de la recopilación de datos.

1. Establezca una nueva URL en la extensión de Adobe Campaign Standard para la que se restableció la clave principal.

1. Guárdelo y deje que se sincronice el flujo de trabajo.

1. Una vez finalizada la sincronización, abra la propiedad móvil en en la interfaz de usuario de la recopilación de datos.

1. Establezca la dirección URL correcta en la extensión de Adobe Campaign Standard para la que se restableció la clave principal.

1. Guárdelo y deje que la sincronización del flujo de trabajo se ejecute de nuevo.

1. Solo entonces la propiedad aparecerá en **[!UICONTROL Ready to Configure]** en Adobe Campaign y ahora se puede configurar.

## Quiero configurar una propiedad móvil en Adobe Campaign. ¿Tengo que esperar para que el flujo de trabajo técnico se sincronice entre las etiquetas en Adobe Experience Platform y Adobe Campaign?

Puede realizar la ejecución inmediata del flujo de trabajo:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]**.

1. Abra el **[!UICONTROL syncWithLaunch]** flujo de trabajo.

1. Haga clic en **[!UICONTROL Scheduler]** actividad y seleccione **[!UICONTROL Immediate execution]**.
