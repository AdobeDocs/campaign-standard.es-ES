---
title: Pista de auditoría
description: Supervise las acciones y los eventos con la pista de auditoría de Campaign
audience: administration
content-type: reference
topic-tags: users-and-security
feature: Access Management
role: Admin
level: Experienced
exl-id: 4a4c14da-d842-4f65-821a-ca9e73a94adc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 2%

---

# Pista de auditoría {#audit}

El **[!UICONTROL Audit trail]** le permite acceder al historial completo de los cambios realizados dentro de la instancia.

**[!UICONTROL Audit trail]** captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de la instancia de Adobe Campaign Standard. Incluye una forma de autoservicio de acceder a un historial de datos para responder preguntas como: qué ha pasado con sus flujos de trabajo, recursos personalizados y opciones, quién los actualizó por última vez o qué han hecho los usuarios en la instancia.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** consta de tres componentes:

* **Pista** de auditoría de recursos personalizados: compruebe la actividad y la última modificación realizada en los recursos personalizados.

   Para obtener más información sobre **[!UICONTROL Custom resources]**, consulte esta [página](../../developing/using/key-steps-to-add-a-resource.md).

* **Pista** de auditoría de flujo de trabajo: compruebe la actividad y la última modificación realizadas en los flujos de trabajo y, además, el estado de los flujos de trabajo, como:

   * Creado
   * Modificado
   * Eliminado
   * Inicio del flujo de trabajo
   * Pausa del flujo de trabajo
   * Parada del flujo de trabajo
   * Reinicio del flujo de trabajo
   * Limpieza de flujo de trabajo
   * Workflow Simulate
   * Descarga del flujo de trabajo
   * Flujo de trabajo detención inmediata
   * Reinicio del flujo de trabajo con el mismo usuario
   * Reiniciar flujo de trabajo desconocido, comando

   Para obtener más información sobre **[!UICONTROL Workflows]**, consulte esta [página](../../automating/using/get-started-workflows.md).

* **Pista** de auditoría de opciones: compruebe la actividad y la última modificación realizada en las opciones .

   Para obtener más información sobre **[!UICONTROL Options]**, consulte esta [página](../../administration/using/about-campaign-standard-settings.md).

Tenga en cuenta que, de forma predeterminada, el período de retención es de 30 días.

## Acceso a la pista de auditoría {#audit-access}

Para acceder a la pista de auditoría de su instancia:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. La ventana **[!UICONTROL Audit trail]** se abre con la lista de las entidades. Adobe Campaign Standard auditará las acciones de creación, edición y eliminación de flujos de trabajo, opciones y recursos personalizados.

   Desde el menú **[!UICONTROL Search]**, puede filtrar la entidad en:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: Tipo de entidad entre Todos, Flujo de trabajo, Recurso personalizado y Opción.
   * **[!UICONTROL Entity name]**: ID del flujo de trabajo, la opción o el recurso personalizado

   ![](assets/audit-trail_2.png)

1. Seleccione una de las entidades para obtener más información sobre las últimas modificaciones.

1. La ventana Audit entity le proporciona información más detallada sobre la entidad elegida, como:

   * **[!UICONTROL Entity]**: ID del flujo de trabajo, la opción o el recurso personalizado.
   * **[!UICONTROL Action]**: Última acción realizada en esta entidad.
   * **[!UICONTROL Changed by]**: Nombre de usuario de la última persona que modificó esta entidad por última vez.
   * **[!UICONTROL Changed date]**: Fecha de la última acción realizada en esta entidad.
   * **[!UICONTROL Content]**: Bloque de código que proporciona más información sobre qué se ha cambiado exactamente en la entidad.

   En este ejemplo, podemos ver que el flujo de trabajo WKF110 lo inició el 26 de agosto el administrador de negocios de esta instancia.

   ![](assets/audit-trail_3.png)

## Habilitar/deshabilitar pista de auditoría {#enable-disable-audit}

La pista de auditoría se puede activar o desactivar fácilmente para una actividad específica.

Para ello:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Seleccione una de las siguientes opciones en función de la entidad que desee desactivar:

   * **[!UICONTROL XtkAudit_Workflows]** para administrar la pista de auditoría para flujos de trabajo.
   * **[!UICONTROL XtkAudit_Option]** para administrar la pista de auditoría de Opciones.
   * **[!UICONTROL XtkAudit_CusResource]** para administrar la pista de auditoría para los recursos personalizados.
   * **[!UICONTROL XtkAudit_Enable_All]** para administrar la pista de auditoría de cada entidad.

      >[!NOTE]
      >
      >Si la opción **[!UICONTROL XtkAudit_Enable_All]** se establece en 0, la función **[!UICONTROL Audit trail]** se desactivará por completo, independientemente de los demás valores de opción individuales.
   ![](assets/audit-trail_5.png)

1. En la página **[!UICONTROL Options]**, establezca **[!UICONTROL Value (integer)]** en 0 si desea deshabilitar el **[!UICONTROL Audit trail]** o en 1 para habilitarlo.

   ![](assets/audit-trail_6.png)

1. Haga clic en **[!UICONTROL Save]**.