---
title: Permiso de mensajería transaccional
description: Obtenga información sobre los permisos vinculados a eventos transaccionales.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
hide: true
hidefromtoc: true
feature: Transactional Messaging
role: User
level: Intermediate
source-git-commit: d7e0912dd7d19a1f5dd2172235f28a40e130cac1
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---

# Permiso de mensajería transaccional {#transactional-message-permission}

Actualmente, en Adobe Campaign Standard, los usuarios sin el grupo de seguridad Administrador no pueden acceder, crear ni publicar eventos, lo que provoca problemas para los usuarios empresariales que necesitan configurar y publicar eventos pero carecen de derechos de administrador.

Hemos implementado las siguientes mejoras en el control de acceso de mensajería transaccional:

* Un nuevo **[!UICONTROL Role]**, llamado **usuario de MC**, se ha agregado para permitir que los usuarios que no son administradores administren eventos transaccionales. La variable **usuario de MC** otorga a estos usuarios la capacidad de acceder, crear, publicar y cancelar la publicación de eventos y mensajes transaccionales.

* Los envíos secundarios ahora se establecen en la variable **[!UICONTROL Organizational unit]** del grupo de seguridad al que pertenece el usuario que crea la plantilla de mensaje, en lugar de limitarse al **[!UICONTROL Organizational unit]** del **Agente del centro de mensajes (mcExec)** grupo de seguridad.

* El valor predeterminado **Ejecución del centro de mensajes (mcExec)** campaign, que recopila los envíos secundarios de mensajes transaccionales, ahora se establece en la unidad organizativa **Todo** que permite a todos los usuarios ver informes de envíos secundarios.

Para asignar la variable **usuario de MC** función:

1. Cree una nueva **[!UICONTROL Security group]** o actualizar uno existente. [Más información](../../administration/using/managing-groups-and-users.md).

1. Haga clic en **[!UICONTROL Create element]** para asignar funciones al grupo de seguridad.

   ![](assets/event_access_1.png)

1. Seleccione el usuario de MC **[!UICONTROL Role]** y haga clic en **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Proceda con precaución al asignar la función de usuario de MC a los operadores, ya que esto les otorga la capacidad de cancelar la publicación de eventos.

   ![](assets/event_access_2.png)

1. Una vez configurada, haga clic en **[!UICONTROL Save]**.

Usuarios vinculados a esto **[!UICONTROL Security group]** ahora puede acceder, crear y publicar eventos y mensajes transaccionales.

La siguiente tabla describe el impacto de esta función en el control de acceso:

| Objetos | Antes de este cambio | Después de este cambio |
|:-: | :--: | :-:|
| Campaña de Message Center Execution (mcExec) | **Ejecución del centro de mensajes (mcExec)** la campaña se establece en la unidad organizativa de **Agente del centro de mensajes (mcExec)** grupo de seguridad. | **Ejecución del centro de mensajes (mcExec)** campaña se establece en la unidad organizativa **Todo** para permitir que todos los envíos secundarios se asocien a esta campaña.</br> Todos los usuarios pueden ver los informes de los envíos secundarios, pero solo tendrán acceso de solo lectura al contenido del envío. |
| Entregas secundarias | Los envíos secundarios se establecen en la variable **Unidad organizativa** del **Agente del centro de mensajes (mcExec)** grupo de seguridad. | Los envíos secundarios se establecerán en la variable **Unidad organizativa** del grupo de seguridad al que pertenece el usuario que crea la plantilla de mensaje. |
| Plantilla de mensaje | Las plantillas de mensaje se establecen en la variable **Unidad organizativa** del **Agente del centro de mensajes (mcExec)** grupo de seguridad. | Las plantillas de mensaje se configurarán en la variable **Unidad organizativa** del grupo de seguridad al que pertenece el usuario que crea la plantilla de mensaje. |
| Eventos transaccionales | Solo los usuarios dentro de la variable **Administrador** grupo de seguridad puede crear y publicar eventos. | La variable **usuario de MC** permite a los usuarios crear y publicar eventos. |
| Plantillas de mensaje transaccional | Las plantillas de mensajes transaccionales se establecen en la unidad organizativa **Todo**. | La plantilla de mensaje de transacción se establecerá en **Unidad organizativa** del grupo de seguridad al que pertenece el usuario que crea la plantilla de mensaje. |