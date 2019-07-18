---
title: Unidades organizativas
seo-title: Unidades organizativas
description: Unidades organizativas
seo-description: Defina los niveles de acceso de los usuarios mediante las unidades de organización.
page-status-flag: no activado nunca
uuid: 8 c 82 ffea-cef 4-4 a 89-b 823-d 8 b 7 bae 1 db 4 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: usuarios y seguridad
discoiquuid: 6 f 60 c 653-1 d 12-4 d 27-9 bc 8-ce 8 c 19 bca 466
context-tags: Orgunit, overview; Orgunit, main; Geounit, overview; Geounit, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Organizational units{#organizational-units}

## About units {#about-units}

Cada objeto y usuario de la plataforma se vincula a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para proporcionar a los usuarios una vista filtrada. La unidad de usuario define su nivel de acceso para diferentes objetos de plataforma.

>[!CAUTION]
>
>Si un usuario no está vinculado a ninguna unidad, ese usuario no podrá conectarse a Adobe Campaign. If you would like to restrict access for a particular user or group of users, do not link it to the **[!UICONTROL All]** unit.

Un usuario tiene acceso de solo lectura a todos los objetos de las unidades principales. Tiene acceso de lectura y escritura a todos los objetos de su unidad y de las unidades secundarias. Un usuario no tiene acceso a objetos en ramas paralelas.

By default, only the **[!UICONTROL All]** units are available.

Cuando se asigna una unidad organizativa al usuario, esta unidad siempre se aplicará a los objetos que ha creado el usuario.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario se encuentra en varios grupos vinculados a diferentes unidades, se aplican determinadas reglas. For more information, refer to the [Managing groups and users](../../administration/using/managing-groups-and-users.md) section.

## Creating and managing units {#creating-and-managing-units}

Las unidades organizativas le permiten filtrar su instancia según la organización a la que estén vinculados los usuarios. Esta unidad puede representar una región, país o incluso una marca en su instancia.

Here, we previously created security groups with different roles to two users: one user is assigned the security groups Administrators and Geometrixx, the other user belongs to the security groups Standard user and Geometrixx Clothes See [Creating a security group and assigning users](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) for the full example.

Ahora es necesario crear las unidades de organización para los grupos de seguridad de Geometrixx Ropa y Geometrixx:

1. From Adobe campaign advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Click **[!UICONTROL Create]** to start configuring your organizational unit.

   ![](assets/manage_units_1.png)

1. Change the default **[!UICONTROL Label]** and **[!UICONTROL ID]** to Geometrixx.
1. A continuación, vincule esta unidad a una unidad principal. Here, we chose **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finally, click **[!UICONTROL Create]** to start assigning your new organizational unit to security group.
1. Siga el mismo procedimiento para la unidad de Ropa de Geometrixx, excepto que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de asignar diferentes unidades a un grupo de seguridad diferente, el usuario asignado a los grupos Administrador y Geometrixx creará dos plantillas de correo electrónico para ver lo que el otro usuario asignado a la Ropa de usuario estándar y Geometrixx puede o no tener acceso.

1. From the advanced menu, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. Duplique una plantilla existente y la personalice según sea necesario. For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. When the template is created, select the **[!UICONTROL Edit properties]** icon to assign units to your template.

   ![](assets/manage_units_6.png)

1. In the **[!UICONTROL Access authorization]** drop down menu, select the organizational unit.

   Aquí vamos a crear una plantilla con la unidad organizativa creada anteriormente Geometrixx.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad de organización de Geometrixx Ropa creada anteriormente.

El usuario asignado a los grupos de Mobile User y Geometrixx Ropa podrá ver ambas plantillas. Debido a la estructura jerárquica de las unidades de la organización, tendrá acceso de lectura y escritura a la plantilla vinculada a la unidad de Ropa de Geometrixx y solo acceso de solo lectura a la plantilla vinculada a la unidad Geometrixx.

![](assets/manage_units_7.png)

Como la unidad de Ropa de Geometrixx es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando el usuario intenta modificar la plantilla Geometrixx:

![](assets/manage_units_8.png)

Las unidades de organización pueden restringir el acceso a diferentes funciones, como perfiles. For example, if our Geometrixx Clothes user access the **[!UICONTROL Profiles]** tab, he will be able to fully access and modify the profiles with the Geometrixx Clothes organizational unit.

Whereas the profiles with the Geometrixx organizational unit will be read only, the following error will appear if our user tries to modify one profile: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partitioning profiles {#partitioning-profiles}

Si su organización necesita aislar los perfiles de cada una de sus marcas, puede dividir sus perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y deben agregarse.

Los usuarios no pueden acceder a perfiles sin unidades organizativas.

>[!CAUTION]
>
>Recomendamos agregar esta opción antes de importar cualquier perfil. Si ya ha importado la base de datos de clientes, es necesario actualizar para definir los valores de unidad organizativa en los perfiles ya importados.

1. From the advanced menu, via the Adobe Campaign logo, select **Administration &gt; Development &gt; Custom resources**.
1. Select **Profile** or create a new custom resource to extend the profiles.
1. Check the **Add access authorization management fields** box to add the organizational units in the **Profile** extension.

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. Actualice la estructura volviendo a publicar los recursos personalizados. For more information about the publication process, refer to [Updating the structure](../../developing/using/data-model-concepts.md) section.

The organizational unit field is added to your profiles in the **[!UICONTROL Access authorization]** section.

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)

