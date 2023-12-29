---
title: Permiso de mensajería transaccional
description: Obtenga información sobre los permisos vinculados a eventos transaccionales.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: 995da330-6c86-444b-86b2-61d887f37db4
source-git-commit: 7247fe596494690ac0676196fbb72c6139aeb0c7
workflow-type: tm+mt
source-wordcount: '797'
ht-degree: 1%

---

# Mejoras de eventos transaccionales {#transactional-event-improvements}

>[!AVAILABILITY]
>
>Actualmente, estas funciones solo están disponibles para un conjunto de organizaciones (disponibilidad limitada). Para obtener más información, póngase en contacto con su representante Adobe.

Actualmente, en Adobe Campaign Standard, los usuarios sin el grupo de seguridad Administrador no pueden acceder, crear ni publicar eventos transaccionales, lo que provoca problemas para los usuarios empresariales que necesitan configurar y publicar eventos pero carecen de derechos de administrador. Además, no es posible duplicar eventos transaccionales.

Hemos implementado las siguientes mejoras en el control de acceso de la mensajería transaccional:

* Un nuevo **[!UICONTROL Role]**, llamado **Usuario de MC**, se ha agregado para permitir a los usuarios que no son administradores administrar la configuración de eventos transaccionales. El **Usuario de MC** Esta función permite a estos usuarios acceder, crear, publicar y cancelar la publicación de mensajes y eventos transaccionales.

* Los envíos de ejecución (es decir, los mensajes técnicos que se crean cada vez que se edita y publica de nuevo un mensaje transaccional, o una vez al mes de forma predeterminada) ahora se establecen en **[!UICONTROL Organizational unit]** del grupo de seguridad al que pertenece el usuario que crea el evento, en lugar de estar restringido al **[!UICONTROL Organizational unit]** de la **Agente del Centro de mensajes (mcExec)** grupo de seguridad.

* **Administradores** ahora puede duplicar eventos transaccionales publicados, así como usuarios con la variable **Usuario de MC** función siempre que estén en el mismo **Entidades organizativas** como el usuario que creó el evento.

## Asignar la función de usuario de MC {#assign-role}

Para asignar el **Usuario de MC** función para su grupo de seguridad:

1. Crear un nuevo **[!UICONTROL Security group]** o actualizar uno existente. [Más información](../../administration/using/managing-groups-and-users.md).

1. Clic **[!UICONTROL Create element]** para asignar funciones a su grupo de seguridad.

   ![](assets/event_access_1.png)

1. Seleccione el usuario de MC **[!UICONTROL Role]** y haga clic en **[!UICONTROL Confirm]**.

   >[!IMPORTANT]
   >
   > Proceda con precaución al asignar la función Usuario de MC a operadores, ya que esto les permite cancelar la publicación de eventos.

   ![](assets/event_access_2.png)

1. Una vez configurada, haga clic en **[!UICONTROL Save]**.

Usuarios vinculados a esto **[!UICONTROL Security group]** Ahora puede acceder, crear y publicar eventos transaccionales y mensajes.

## Asignar el grupo de seguridad de usuario de MC {#assign-group}

1. En el Admin Console, seleccione **Productos** pestaña.

1. Seleccionar **Adobe Campaign Standard** a continuación, elija su instancia.

1. Desde el **Perfiles de producto** , seleccione la **Usuario de MC** grupo.

1. Clic **Agregar usuario** e introduzca el nombre, el grupo de usuarios o la dirección de correo electrónico del perfil que desea agregar a este perfil de producto.

1. Una vez añadido, haga clic en **Guardar**.

Usuarios añadidos a esto **[!UICONTROL Security group]** Ahora puede acceder, crear y publicar eventos transaccionales y mensajes.

## Duplicar eventos transaccionales {#duplicate-transactional-events}

Un usuario con **Administrador** grupo de seguridad<!--([Functional administrators](../../administration/using/users-management.md#functional-administrators)?)--> ahora puede duplicar una configuración de evento si el evento se ha **publicado**.

Además, los usuarios que no son administradores con **Usuario de MC** La función ahora puede acceder a las configuraciones de evento, pero su permiso para duplicar está determinado por la variable **Entidades organizativas** pertenecen a. Si el usuario actual y el usuario que creó el evento pertenecen a la misma jerarquía de unidades organizativas, se permite la duplicación.

Por ejemplo, si un usuario que pertenece a la unidad organizativa &quot;Ventas Francia&quot; crea una configuración de evento:

* Otro usuario cuya unidad organizativa sea &quot;Ventas de París&quot; podrá duplicar este evento, ya que &quot;Ventas de París&quot; es parte de la unidad organizativa &quot;Ventas de Francia&quot;.

* Sin embargo, un usuario cuya unidad organizativa sea &quot;Ventas de San Francisco&quot; no podrá hacerlo, ya que &quot;Ventas de San Francisco&quot; se encuentra bajo la unidad organizativa &quot;Ventas EE. UU.&quot;, que es independiente de la unidad organizativa &quot;Ventas Francia&quot;.

Para duplicar una configuración de evento, siga los pasos a continuación.

1. Haga clic en **Adobe** , en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.

1. Pase el ratón sobre la configuración de evento publicada que desee y seleccione **[!UICONTROL Duplicate element]** botón.

   ![](assets/message-center_duplicate-button.png)

   >[!CAUTION]
   >
   >No se puede duplicar una configuración de evento que no se ha publicado. [Más información](publishing-transactional-event.md)

1. Se muestra automáticamente el evento duplicado. Contiene la misma configuración que definió para el evento original, pero tiene el **[!UICONTROL Draft]** estado.

   ![](assets/message-center_duplicated-draft-event.png)

1. El mensaje transaccional correspondiente se crea automáticamente. Para acceder a él, vaya a **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_duplicated-message.png)

1. Abra el mensaje recién duplicado. Contiene el mismo diseño que definió para el mensaje original, pero tiene el **[!UICONTROL Draft]** estado, incluso si se publicó el mensaje transaccional original.

   ![](assets/message-center_duplicated-draft-message.png)

1. Ahora puede editar y personalizar este mensaje. Consulte [Edición de mensajes transaccionales](../../channels/using/editing-transactional-message.md).

## Impactos {#impacts}

En la tabla siguiente se describen los efectos de estas mejoras:

| Objetos | Antes de este cambio | Después de este cambio |
|:-: | :--: | :-:|
| Eventos transaccionales | Solo los usuarios dentro de **Administrador** grupo de seguridad puede crear y publicar eventos. | El **Usuario de MC** Esta función permite a los usuarios crear y publicar eventos. |
| Mensajes transaccionales | Los mensajes transaccionales se establecen en **Entidades organizativas** de la **Agente del Centro de mensajes (mcExec)** grupo de seguridad. | Los mensajes transaccionales se establecen en **Entidades organizativas** del grupo de seguridad al que pertenece el usuario que crea el evento/mensaje transaccional. |
| Entregas de ejecución | Los envíos de ejecución se establecen en **Entidades organizativas** de la **Agente del Centro de mensajes (mcExec)** grupo de seguridad. | Los envíos de ejecución se establecen en **Entidades organizativas** del grupo de seguridad al que pertenece el usuario que crea el evento/mensaje transaccional. |
| Eventos transaccionales publicados | La duplicación no es posible para ningún usuario. | <ul><li>Usuarios con **Administrador** el grupo de seguridad puede duplicar eventos publicados.</li> <li>Usuarios con **Usuario de MC** La función puede duplicar eventos publicados siempre que estén en el mismo **Entidades organizativas** como el usuario que creó el evento.</li></ul> |


<!--Transactional Message Templates| Transactional Message templates are set to the Organizational unit **All**. | Transaction Message Template will be set to the **Organizational unit** of the security group to which the user creating the message template belongs.-->