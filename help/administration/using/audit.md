---
title: Pista de auditoría
description: Monitorización de acciones y eventos con la pista de auditoría de Campaign
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: bda6f8d5-3bcf-498c-a7c4-d3c2c79b9510
source-git-commit: 64da7ac09e1b0fbf13ba1e563b6dc7be995b1640
workflow-type: tm+mt
source-wordcount: '495'
ht-degree: 3%

---

# Pista de auditoría {#audit}

El **[!UICONTROL Audit trail]** le proporciona acceso al historial completo de cambios realizados dentro de su instancia.

**[!UICONTROL Audit trail]** captura en tiempo real una lista completa de las acciones y eventos que se producen dentro de su instancia de Adobe Campaign Standard. Incluye una forma de autoservicio de acceder a un historial de datos para responder preguntas como: qué ha pasado con sus flujos de trabajo, recursos personalizados y opciones, quién los actualizó por última vez o qué han hecho los usuarios en la instancia.

![](assets/audit-trail.png)

**[!UICONTROL Audit trail]** consta de tres componentes:

* **Pista de auditoría de recursos personalizados**: compruebe la actividad y la última modificación realizadas en los recursos personalizados.

  Para obtener más información sobre **[!UICONTROL Custom resources]**, consulte esta [página](../../developing/using/key-steps-to-add-a-resource.md).

* **Pista de auditoría de flujo de trabajo**: compruebe la actividad y la última modificación realizadas en los flujos de trabajo y, además, el estado de los mismos, como por ejemplo:

   * Creado
   * Modificado
   * Eliminado
   * Inicio del flujo de trabajo
   * Pausa de flujo de trabajo
   * Parada de flujo de trabajo
   * Reinicio del flujo de trabajo
   * Limpieza de flujo de trabajo
   * Simulación de flujo de trabajo
   * Reactivación de flujo de trabajo
   * Parada inmediata del flujo de trabajo
   * Reinicio del flujo de trabajo con el mismo usuario
   * Comando Workflow Restart Unknown

  Para obtener más información sobre **[!UICONTROL Workflows]**, consulte esta [página](../../automating/using/get-started-workflows.md).

* **Pista de auditoría de opciones**: compruebe la actividad y la última modificación realizadas en las opciones.

  Para obtener más información sobre **[!UICONTROL Options]**, consulte esta [página](../../administration/using/about-campaign-standard-settings.md).

Tenga en cuenta que, de forma predeterminada, el período de retención es de 30 días.

## Acceso a Pista de auditoría {#audit-access}

Para acceder a la pista de auditoría de su instancia:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Audit trail]**.

   ![](assets/audit-trail.png)

1. La ventana **[!UICONTROL Audit trail]** se abre con la lista de sus entidades. Adobe Campaign Standard auditará las acciones de creación, edición y eliminación de flujos de trabajo, opciones y recursos personalizados.

   Desde el menú **[!UICONTROL Search]**, puede filtrar su entidad por:

   * **[!UICONTROL Start date]**
   * **[!UICONTROL End date]**
   * **[!UICONTROL Type]**: tipo de entidad entre Todos, Flujo de trabajo, Recurso personalizado y Opción.
   * **[!UICONTROL Entity name]**: ID de su flujo de trabajo, opción o recurso personalizado

   ![](assets/audit-trail_2.png)

1. Seleccione una de las entidades para obtener más información sobre las últimas modificaciones.

1. La ventana Audit entity proporciona información más detallada sobre la entidad elegida, como:

   * **[!UICONTROL Entity]**: ID de su flujo de trabajo, opción o recurso personalizado.
   * **[!UICONTROL Action]**: última acción realizada en esta entidad.
   * **[!UICONTROL Changed by]**: nombre de usuario de la última persona que modificó esta entidad por última vez.
   * **[!UICONTROL Changed date]**: fecha de la última acción realizada en esta entidad.
   * **[!UICONTROL Content]**: bloque de código que le proporciona más información sobre lo que se ha cambiado exactamente en su entidad.

   En este ejemplo, podemos ver que el administrador de empresa de esta instancia ha iniciado el flujo de trabajo WKF110 el 26 de agosto.

   ![](assets/audit-trail_3.png)

## Habilitar/deshabilitar pista de auditoría {#enable-disable-audit}

>[!NOTE]
>
> Solo los administradores funcionales pueden activar o desactivar Pista de auditoría. Para obtener más información, consulte esta [página](../../administration/using/users-management.md#functional-administrators).

La pista de auditoría se puede activar o desactivar fácilmente para una actividad específica.

Para ello:

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

   ![](assets/audit-trail_4.png)

1. Seleccione una de las siguientes opciones en función de la entidad que desee desactivar:

   * Opción **[!UICONTROL XtkAudit_Workflows]** para administrar la pista de auditoría de los flujos de trabajo.
   * Opción **[!UICONTROL XtkAudit_Option]** para administrar la pista de auditoría de las opciones.
   * Opción **[!UICONTROL XtkAudit_CusResource]** para administrar la pista de auditoría para los recursos personalizados.
   * Opción **[!UICONTROL XtkAudit_Enable_All]** para administrar la pista de auditoría para cada entidad.

     >[!NOTE]
     >
     >Si la opción **[!UICONTROL XtkAudit_Enable_All]** se establece en 0, la característica **[!UICONTROL Audit trail]** se deshabilitará por completo, independientemente de otros valores de opción individuales.

   ![](assets/audit-trail_5.png)

1. En la página **[!UICONTROL Options]**, establezca **[!UICONTROL Value (integer)]** en 0 si desea deshabilitar **[!UICONTROL Audit trail]** o en 1 para habilitarlo.

   ![](assets/audit-trail_6.png)

1. Haga clic en **[!UICONTROL Save]**.
