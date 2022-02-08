---
title: Unidades organizativas
description: Definir los niveles de acceso de los usuarios mediante unidades organizativas
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: fbab695a-2672-4183-8c3b-78af7aefd5b1
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 5%

---

# Unidades organizativas{#organizational-units}

## Acerca de las unidades {#about-units}

Cada objeto y usuario de la plataforma está vinculado a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para proporcionar a los usuarios una vista filtrada. La unidad de un usuario define su nivel de acceso para diferentes objetos de plataforma.

>[!IMPORTANT]
>
>Si un usuario no está vinculado a ninguna unidad, no podrá conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule al **[!UICONTROL All]** unidad. Se recomienda añadir la opción **Campos de gestión de autorizaciones de acceso** antes de importar cualquier perfil. Para obtener más información, consulte [esta sección](../../administration/using/organizational-units.md#partitioning-profiles).
>
>De forma predeterminada, la **[!UICONTROL All (all)]** unidad organizativa se asigna al grupo de seguridad **[!UICONTROL Administrators]**. Es de solo lectura y no se puede modificar.

Un usuario tiene acceso de solo lectura a todos los objetos de las unidades principales. Este usuario tiene acceso de lectura y escritura a todos los objetos de su unidad y unidades secundarias. Un usuario no tiene acceso a objetos en ramas paralelas.

De forma predeterminada, solo la variable **[!UICONTROL All]** están disponibles.

Cuando al usuario se le asigna una unidad organizativa, esta unidad siempre se aplicará a los objetos que el usuario haya creado.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario está en varios grupos vinculados a diferentes unidades, se aplican ciertas reglas. Para obtener más información, consulte [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md) para obtener más información.

## Creación y administración de unidades {#creating-and-managing-units}

Las unidades organizativas permiten filtrar la instancia según la organización a la que estén vinculados los usuarios. Esta unidad puede representar una región, un país o incluso una marca en su caso.

Aquí, anteriormente, creamos grupos de seguridad con diferentes funciones para dos usuarios: a un usuario se le asignan los grupos de seguridad Administradores y Geometrixx, el otro usuario pertenece a los grupos de seguridad Usuario estándar y Ropa de Geometrixx Véase [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para ver el ejemplo completo.

Ahora necesitamos crear las unidades organizativas para los grupos de seguridad de Ropa de Geometrixx y Geometrixx:

1. En el menú avanzado de campaña de Adobe, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Haga clic en **[!UICONTROL Create]** para comenzar a configurar la unidad organizativa.

   ![](assets/manage_units_1.png)

1. Cambiar el valor predeterminado **[!UICONTROL Label]** y **[!UICONTROL ID]** a Geometrixx.
1. A continuación, vincule esta unidad a una unidad principal. Aquí, elegimos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finalmente, haga clic en **[!UICONTROL Create]** para empezar a asignar la nueva unidad organizativa al grupo de seguridad.
1. Siga el mismo procedimiento para la unidad de ropa de Geometrixx, excepto que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de asignar diferentes unidades a diferentes grupos de seguridad, el usuario asignado a los grupos Administrador y Geometrixx creará dos plantillas de correo electrónico para ver a qué pueden o no acceder el otro usuario asignado a Usuario estándar y Ropa de Geometrixx.

1. En el menú avanzado, seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplique una plantilla existente y personalícela según sea necesario. Para obtener más información, consulte la sección [Acerca de las plantillas](../../start/using/marketing-activity-templates.md).
1. Cuando se cree la plantilla, seleccione la opción **[!UICONTROL Edit properties]** para asignar unidades a la plantilla.

   ![](assets/manage_units_6.png)

1. En el **[!UICONTROL Access authorization]** menú desplegable, seleccione la unidad organizativa.

   Aquí vamos a crear una plantilla con la Geometrixx de unidad organizativa creada anteriormente.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad organizativa de ropa de Geometrixx creada anteriormente.

Los usuarios asignados a **Usuario estándar** y **Ropa de Geometrixx** los grupos podrán ver ambas plantillas. Debido a la estructura jerárquica de las unidades organizativas, tendrán acceso de lectura y escritura a la plantilla vinculada a la unidad Ropa de Geometrixx y solo acceso de sólo lectura a la plantilla vinculada a la unidad de Geometrixx.

![](assets/manage_units_7.png)

Dado que la unidad Ropa de Geometrixx es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando los usuarios intentan modificar la plantilla de Geometrixx:

![](assets/manage_units_8.png)

Las unidades organizativas pueden restringir el acceso a diferentes funciones, como perfiles. Por ejemplo, si nuestros usuarios de Ropa de Geometrixx acceden al **[!UICONTROL Profiles]** , podrán acceder y modificar completamente los perfiles con la unidad organizativa de ropa de Geometrixx.

Mientras que los perfiles con la unidad organizativa de Geometrixx serán de solo lectura, aparecerá el siguiente error si los usuarios intentan modificar un perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partición de perfiles {#partitioning-profiles}

>[!IMPORTANT]
>
>Se recomienda añadir esta opción antes de importar cualquier perfil, ya que los usuarios no pueden acceder a los perfiles sin unidades organizativas.
>
>Si ya ha importado la base de datos de clientes, es necesario actualizar la base de datos para establecer los valores de la unidad organizativa en los perfiles ya importados.

Si la organización necesita aislar los perfiles contactados por cada una de las marcas diferentes, puede dividir los perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y es necesario añadirlos.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **Administración > Desarrollo > Recursos personalizados**.
1. Select **Perfil** o cree un nuevo recurso personalizado para ampliar los perfiles. Para obtener más información sobre cómo ampliar los perfiles, consulte esta [página](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Marque la **Añadir campos de gestión de autorización de acceso** para agregar las unidades organizativas en la variable **Perfil** extensión.

   ![](assets/user_management_9.png)

1. Haga clic en **[!UICONTROL Save]**.
1. Actualice la estructura publicando de nuevo los recursos personalizados. Para obtener más información sobre el proceso de publicación, consulte [Actualización de la estructura](../../developing/using/updating-the-database-structure.md) para obtener más información.

El campo unidad organizativa se agrega a los perfiles en la variable **[!UICONTROL Access authorization]** para obtener más información.

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
