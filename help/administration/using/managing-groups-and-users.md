---
title: Administración de grupos y usuarios
seo-title: Administración de grupos y usuarios
description: Administración de grupos y usuarios
seo-description: Descubra cómo crear grupos de seguridad y administrar usuarios.
page-status-flag: no activado nunca
uuid: b 3 a 3 a 2 e 3-9 d 69-4231-b 724-8 f 37419 f 7 a 61
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: usuarios y seguridad
discoiquuid: 12 f 896 ab-ee 79-4 d 96-976 d-cf 34643491 b 4
context-tags: user, overview; user, main; security, overview; seguridad, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Managing groups and users{#managing-groups-and-users}

## About security groups {#about-security-groups}

Los grupos de seguridad son conjuntos de usuarios que comparten las mismas funciones y derechos dentro de su organización.

Los usuarios deben estar siempre vinculados a un grupo de seguridad. Esto le permitirá asignarles funciones específicas y unidades de organización.

For more information on roles, the tables in the following page present the different operations available according to a user's role(s): [Adobe Campaign Standard authorizations](https://docs.campaign.adobe.com/doc/standard/en/Technotes/AdobeCampaign-ACSRights.pdf).

Los grupos de seguridad predeterminados son:

* **[!UICONTROL Administrators]**
* **[!UICONTROL Delivery supervisors]**
* **[!UICONTROL Message Center agents]**
* **[!UICONTROL Standard Users]**
* **[!UICONTROL Workflow supervisors]**

Si un usuario no está vinculado a ningún grupo de seguridad, no podrá acceder a Adobe Campaign.

To restrict a user's access, do not add the user to the Campaign Standard users group as this is linked to **[!UICONTROL All]** organizational unit.

## Creating a security group and assigning users {#creating-a-security-group-and-assigning-users}

>[!CAUTION]
>
>Tenga en cuenta que, en la Consola de administración, los grupos de seguridad se denominan perfiles.

Puede crear sus propios grupos de seguridad si los grupos predeterminados no son suficientes para administrar a los usuarios. Pueden gestionarlos Administradores que tengan acceso tanto a los menús de administración de Adobe Campaign como a la Consola de administración. For more information on the Admin console, refer to this [documentation](https://helpx.adobe.com/enterprise/managing/user-guide.html).

En este caso, primero debemos asignar los dos grupos predeterminados de usuario y administrador Estándar a nuestros usuarios. Estos grupos de seguridad restringirán algunas funcionalidades de Adobe Campaign: El usuario estándar tiene acceso básico a Adobe Campaign, mientras que el administrador puede acceder a los menús de administración por ejemplo.

Tenga en cuenta que los cambios realizados en los grupos de seguridad de la consola de administración se sincronizarán en cuanto los usuarios inicien sesión en Adobe Campaign.

Luego, queremos crear un conjunto de grupos de seguridad Geometrixx y Geometrixx Ropa que restringirán el acceso según las unidades organizativas de nuestro usuario y administrador estándar.

![](assets/ootb_security_group_1.png)

Primero debe asignar uno de los grupos de seguridad predeterminados a los usuarios:

1. In the Admin console, select your instance then the **Users** tab.

   ![](assets/manage_security_group_2.png)

1. Click the **[!UICONTROL Add user]** button and enter your user's email address.
1. In the **[!UICONTROL Assign Products]** tab, select your instance then the **[!UICONTROL Administrators]** out-of-the-box security group from the drop-down list. Esto permitirá al usuario tener acceso a los menús de administración y crear los siguientes grupos de seguridad.

   ![](assets/ootb_security_group_2.png)

1. Click **[!UICONTROL Save]** and follow the same procedures to assign the **[!UICONTROL Standard Users]** out-of-the-box security group to your new user.

   ![](assets/ootb_security_group_3.png)

Once your two users are attached to the **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** out-of-the-box security groups which assign roles to our users, the Administrator user can now create the two security groups **Geometrixx** and **Geometrixx Clothes** that will assign organizational units to our users in addition to the out-of-the-box security groups.

1. In the Admin console, select your instance then the **Products** tab.
1. Click the **New Profile** button to create the **Geometrixx** security group.

   ![](assets/create_security_1.png)

1. Type the **[!UICONTROL Profile name]** by following this exact syntax: **[!UICONTROL Campaign Standard- instance name - ID of the security group]** and click **[!UICONTROL Done]**.

   El ID elegido se utilizará al crear el grupo de seguridad en Adobe Campaign.

   >[!NOTE]
   >
   >If the above syntax doesn't seem to work with an older instance, it needs to be replaced by **[!UICONTROL Campaign - instance name - ID of the security group]**.

   ![](assets/manage_security_group_1.png)

1. Then, follow the same procedures to create the **Geometrixx Clothes** security group.
1. Assign your security group to your user by selecting the **[!UICONTROL Users]** tab.

   ![](assets/manage_security_group_2.png)

1. Click your previously created user then the ![](assets/managing_security_group_10.png) icon in the **[!UICONTROL Products]** category.

   Select **[!UICONTROL Edit products assigned directly]** to start assigning new security group to your user.

   ![](assets/manage_security_group_8.png)

1. In the **[!UICONTROL Assign Products]** tab, select your instance then your previously created security groups Geometrixx from the drop-down list to assign it to your Administrator user.

   Click **[!UICONTROL Save]**.

   ![](assets/manage_security_group_3.png)

   Si un usuario está en varios grupos:

   * Se acumulan las funciones de los distintos grupos. Aquí, los usuarios están en dos grupos diferentes: uno que actuará sobre funciones el otro en unidades.
   * It is the unit that is the highest in the hierarchy that will be used (see example in the [Organizational units](../../administration/using/organizational-units.md) section).
   * El usuario ya no podrá conectarse si las unidades tienen el mismo nivel equivalente y están en ramas paralelas en la jerarquía.

1. Siga los mismos procedimientos para asignar el grupo de seguridad de Geometrixx Ropa a su usuario estándar.

   ![](assets/manage_security_group_9.png)

Los grupos de seguridad recién creados ahora se crean en la Consola de administración. Para que se sincronicen completamente, también debe crearlas en Adobe Campaign.

El usuario de administrador tiene que crear el conjunto de grupos de seguridad que se utilizan para asignar unidades de organización: Geometrixx y Geometrixx Ropa. To learn how to create organizational units, see [Creating and managing units](../../administration/using/organizational-units.md#creating-and-managing-units) .

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Administration > Users & Security > Security groups]**.
1. Create your new security group and specify its **[!UICONTROL Label]** and **[!UICONTROL ID]**.

   El ID debe ser el mismo que el elegido en la Consola de administración.

1. In the **[!UICONTROL User access]** field, assign organizational unit. Here, the Geometrixx security group is assigned the **[!UICONTROL All]** organizational unit.

   ![](assets/manage_security_group_6.png)

1. También puede asignar funciones a su grupo de seguridad. In our case, this step is not needed since the out-of-the-box security groups **[!UICONTROL Administrators]** and **[!UICONTROL Standard users]** are used to assign roles.
1. Siga los mismos procedimientos para crear la última seguridad Geometrixx Ropa y asigne la unidad organizativa de Ropa de Geometrixx.

   ![](assets/manage_security_group_7.png)

Ahora los usuarios se asignan a un grupo de seguridad y pueden conectarse a Adobe Campaign.

>[!CAUTION]
>
>Si los usuarios se eliminan de un grupo de seguridad en la consola de administración, permanecerán en el grupo de seguridad de Adobe Campaign y ya no podrán iniciar sesión en Adobe Campaign. En este caso, elimine las direcciones de correo electrónico de los usuarios en la consola de administración para evitar que reciban información confidencial.

