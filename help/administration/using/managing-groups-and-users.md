---
title: Administración de grupos y usuarios
description: Obtenga información sobre cómo crear grupos de seguridad y administrar usuarios.
page-status-flag: never-activated
uuid: b3a3a2e3-9d69-4231-b724-8f37419f7a61
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 12f896ab-ee79-4d96-976d-cf34643491b4
context-tags: user,overview;user,main;security,overview;security,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e31e8c63fa94d190211c7a51e7f1091657c9f479

---


# Administración de grupos y usuarios{#managing-groups-and-users}

## Acerca de los grupos de seguridad {#about-security-groups}

Los grupos de seguridad son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de la organización.

Los usuarios siempre deben estar vinculados a un grupo de seguridad. Esto le permitirá asignarles funciones y unidades organizativas específicas.

Para obtener más información sobre las funciones, las tablas de la página siguiente presentan las diferentes operaciones disponibles según las funciones de un usuario: Autorizaciones [de Adobe Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Los grupos de seguridad predeterminados son:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Si un usuario no está vinculado a ningún grupo de seguridad, no podrá acceder a Adobe Campaign.

Para restringir el acceso de un usuario, no agregue el usuario al grupo de usuarios de Campaign Standard, ya que está vinculado a la unidad organizativa **[!UICONTROL All]**.

>[!NOTE]
>
>De forma predeterminada, la unidad organizativa se asigna al grupo de **[!UICONTROL All (all)]****[!UICONTROL Administrators]** seguridad. Es de sólo lectura y no se puede modificar.

## Creación de un grupo de seguridad y asignación de usuarios {#creating-a-security-group-and-assigning-users}

>[!IMPORTANT]
>
>Tenga en cuenta que en la Consola de administración, los grupos de seguridad se denominan perfiles.

Puede crear sus propios grupos de seguridad si los grupos predeterminados no son suficientes para administrar a los usuarios. Pueden ser administrados por administradores que tienen acceso a los menús de administración de Adobe Campaign y a la consola de administración. Para obtener más información sobre la Consola de administración, consulte esta [documentación](https://helpx.adobe.com/enterprise/managing/user-guide.html).

En este caso, primero debemos asignar los dos grupos predeterminados usuario y administrador estándar a nuestros usuarios. Estos grupos de seguridad restringirán algunas funciones de Adobe Campaign: el usuario estándar tiene acceso básico a Adobe Campaign, mientras que el administrador puede acceder a los menús de administración, por ejemplo.

Tenga en cuenta que los cambios realizados en los grupos de seguridad en la consola de administración se sincronizarán en cuanto los usuarios inicien sesión en Adobe Campaign.

A continuación, queremos crear un conjunto de grupos de seguridad Geometrixx y Geometrixx Clothes que restringirán el acceso en función de las unidades organizativas de nuestro usuario y administrador estándar.

![](assets/ootb_security_group_1.png)

Primero debe asignar uno de los grupos de seguridad integrados a los usuarios:

1. En la consola de administración, seleccione la instancia y, a continuación, la ficha **Usuarios** .

   ![](assets/manage_security_group_2.png)

1. Haga clic en el **[!UICONTROL Add user]**botón e introduzca la dirección de correo electrónico del usuario.
1. En la **[!UICONTROL Assign Products]**ficha, seleccione la instancia y, a continuación, el grupo de seguridad**[!UICONTROL Administrators]** predeterminado en la lista desplegable. Esto permitirá al usuario tener acceso a los menús de administración y crear los siguientes grupos de seguridad.

   ![](assets/ootb_security_group_2.png)

1. Haga clic **[!UICONTROL Save]**y siga los mismos procedimientos para asignar el grupo de seguridad**[!UICONTROL Standard Users]** integrado al nuevo usuario.

   ![](assets/ootb_security_group_3.png)

Una vez que los dos usuarios están conectados a los grupos de seguridad **[!UICONTROL Administrators]**y**[!UICONTROL Standard users]** integrados que asignan funciones a nuestros usuarios, el usuario administrador puede crear los dos grupos de seguridad **Geometrixx** y **Geometrixx Clothes** que asignarán unidades organizativas a nuestros usuarios además de los grupos de seguridad integrados.

1. En la consola de administración, seleccione la instancia y, a continuación, la ficha **Productos** .
1. Haga clic en el botón **Nuevo perfil** para crear el grupo de seguridad de **Geometrixx** .

   ![](assets/create_security_1.png)

1. Escriba la **[!UICONTROL Profile name]**siguiendo esta sintaxis exacta:**[!UICONTROL Campaign Standard- instance name - ID of the security group]** y haga clic en **[!UICONTROL Done]**.

   El ID seleccionado se utilizará al crear el grupo de seguridad en Adobe Campaign.

   >[!NOTE]
   >
   >Si la sintaxis anterior no parece funcionar con una instancia anterior, debe reemplazarse por **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. A continuación, siga los mismos procedimientos para crear el grupo de seguridad de ropa de **Geometrixx** .
1. Asigne su grupo de seguridad al usuario seleccionando la **[!UICONTROL Users]**ficha.

   ![](assets/manage_security_group_2.png)

1. Haga clic en el usuario creado anteriormente y, a continuación, en el ![](assets/managing_security_group_10.png) icono de la **[!UICONTROL Products]**categoría.

   Seleccione **[!UICONTROL Edit products assigned directly]**para empezar a asignar un nuevo grupo de seguridad a su usuario.

   ![](assets/manage_security_group_8.png)

1. En la **[!UICONTROL Assign Products]**ficha, seleccione la instancia y, a continuación, los grupos de seguridad creados anteriormente Geometrixx en la lista desplegable para asignarla al usuario administrador.

   Haga clic **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Si un usuario está en varios grupos:

   * Las funciones de los diferentes grupos se acumulan. Aquí, los usuarios están en dos grupos diferentes: una que actuará en funciones y la otra en unidades.
   * Es la unidad que es la más alta de la jerarquía que se utilizará (consulte el ejemplo en la sección Unidades [](../../administration/using/organizational-units.md) organizativas).
   * El usuario ya no podrá conectarse si las unidades tienen el mismo nivel equivalente y están en ramas paralelas en la jerarquía.

1. Siga los mismos procedimientos para asignar el grupo de seguridad Ropa de Geometrixx a su usuario estándar.

   ![](assets/manage_security_group_9.png)

Los grupos de seguridad recién creados ahora se crean en la consola de administración. Para que se sincronicen completamente, también debe crearlos en Adobe Campaign.

El usuario administrador debe crear el conjunto de grupos de seguridad que se utilizan para asignar unidades organizativas: Ropa de Geometrixx y Geometrixx. Para aprender a crear unidades organizativas, consulte [Creación y administración de unidades](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Haga clic en el **[!UICONTROL Adobe Campaign]**logotipo, en la esquina superior izquierda, y seleccione**[!UICONTROL Administration > Users & Security > Security groups]**.
1. Cree el nuevo grupo de seguridad y especifique su **[!UICONTROL Label]**y**[!UICONTROL ID]**.

   El ID debe ser el mismo que el elegido en la consola de administración.

1. En el **[!UICONTROL User access]**campo, asigne una unidad organizativa. Aquí, el grupo de seguridad de Geometrixx se asigna a la unidad organizativa**[!UICONTROL All]** .

   ![](assets/manage_security_group_6.png)

1. También puede asignar funciones a su grupo de seguridad. En nuestro caso, este paso no es necesario, ya que los grupos de seguridad integrados **[!UICONTROL Administrators]**se utilizan**[!UICONTROL Standard users]** para asignar funciones.
1. Siga los mismos procedimientos para crear la última ropa de seguridad de Geometrixx y asignar la unidad organizativa de la ropa de Geometrixx.

   ![](assets/manage_security_group_7.png)

Los usuarios ahora están asignados a un grupo de seguridad y pueden conectarse a Adobe Campaign.

>[!IMPORTANT]
>
>Si los usuarios se eliminan de un grupo de seguridad en la consola de administración, seguirán formando parte del grupo de seguridad de Adobe Campaign y ya no podrán iniciar sesión en Adobe Campaign. En este caso, elimine las direcciones de correo electrónico de los usuarios en la consola de administración para evitar que reciban información confidencial.

