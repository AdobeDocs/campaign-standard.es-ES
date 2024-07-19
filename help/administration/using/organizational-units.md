---
title: Unidades organizativas
description: Defina los niveles de acceso de los usuarios mediante las unidades organizativas
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

Cada objeto y usuario de la plataforma está vinculado a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para proporcionar a los usuarios una vista filtrada. La unidad de un usuario define su nivel de acceso para diferentes objetos de la plataforma.

>[!IMPORTANT]
>
>Si un usuario no está vinculado a ninguna unidad, no podrá conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule a la unidad **[!UICONTROL All]**. Se recomienda agregar la opción **Campos de administración de autorización de acceso** antes de importar los perfiles. Para obtener más información, consulte [esta sección](../../administration/using/organizational-units.md#partitioning-profiles).
>
>De forma predeterminada, la **[!UICONTROL All (all)]** unidad organizativa se asigna al grupo de seguridad **[!UICONTROL Administrators]**. Es de solo lectura y no se puede modificar.

Un usuario tiene acceso de sólo lectura a todos los objetos de las unidades principales. Este usuario tiene acceso de lectura y escritura a todos los objetos de su unidad y unidades secundarias. Un usuario no tiene acceso a objetos en ramas paralelas.

De manera predeterminada, solo están disponibles las unidades **[!UICONTROL All]**.

Cuando al usuario se le asigna una unidad organizativa, esta unidad se aplica siempre a los objetos que el usuario ha creado.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario está en varios grupos vinculados a diferentes unidades, se aplican determinadas reglas. Para obtener más información, consulte la sección [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md).

## Creación y administración de unidades {#creating-and-managing-units}

Las unidades organizativas permiten filtrar la instancia en función de la organización a la que estén vinculados los usuarios. Esta unidad puede representar una región, un país o incluso una marca en su instancia.

Aquí hemos creado grupos de seguridad con diferentes funciones para dos usuarios: a un usuario se le asignan los grupos de seguridad Administradores y Geometrixx, al otro usuario pertenece a los grupos de seguridad Usuario estándar y Geometrixx. Vea [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para ver el ejemplo completo.

Ahora necesitamos crear las unidades organizativas para los grupos de seguridad de Geometrixx Clothes y Geometrixx:

1. En el menú avanzado de la campaña de Adobe, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Haga clic en **[!UICONTROL Create]** para comenzar a configurar la unidad organizativa.

   ![](assets/manage_units_1.png)

1. Cambie **[!UICONTROL Label]** y **[!UICONTROL ID]** predeterminados a Geometrixx.
1. A continuación, vincule esta unidad a una unidad principal. Aquí, elegimos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finalmente, haga clic en **[!UICONTROL Create]** para comenzar a asignar la nueva unidad organizativa al grupo de seguridad.
1. Siga el mismo procedimiento para la unidad Geometrixx Clothes, excepto que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de la asignación de diferentes unidades a diferentes grupos de seguridad, el usuario asignado al administrador y a los grupos de Geometrixx creará dos plantillas de correo electrónico para ver a qué puede acceder o no el otro usuario asignado al usuario estándar y a Geometrixx Clothes.

1. En el menú avanzado, seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplique una plantilla existente y personalícela según sea necesario. Para obtener más información, consulte la sección [Acerca de las plantillas](../../start/using/marketing-activity-templates.md).
1. Cuando se cree la plantilla, seleccione el icono **[!UICONTROL Edit properties]** para asignar unidades a la plantilla.

   ![](assets/manage_units_6.png)

1. En el menú desplegable **[!UICONTROL Access authorization]**, seleccione la unidad organizativa.

   Aquí vamos a crear una plantilla con la Geometrixx de unidad organizativa creada anteriormente.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad organizativa Geometrixx Clothes creada anteriormente.

Los usuarios asignados a los grupos **Usuario estándar** y **Ropa de Geometrixx** podrán ver ambas plantillas. Debido a la estructura jerárquica de las unidades organizativas, tendrán acceso de lectura y escritura a la plantilla vinculada a la unidad de Geometrixx Clothes y acceso de solo lectura a la plantilla vinculada a la unidad de Geometrixx.

![](assets/manage_units_7.png)

Dado que la unidad Geometrixx Clothes es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando los usuarios intentan modificar la plantilla de Geometrixx:

![](assets/manage_units_8.png)

Las unidades organizativas pueden restringir el acceso a diferentes funciones, como los perfiles. Por ejemplo, si nuestros usuarios de Geometrixx Clothes acceden a la pestaña **[!UICONTROL Profiles]**, podrán acceder y modificar completamente los perfiles con la unidad organizativa de Geometrixx Clothes.

Mientras que los perfiles con la unidad organizativa de Geometrixx serán de sólo lectura, aparecerá el siguiente error si los usuarios intentan modificar un perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Partición de perfiles {#partitioning-profiles}

>[!IMPORTANT]
>
>Se recomienda añadir esta opción antes de importar cualquier perfil, ya que los usuarios no pueden acceder a los perfiles sin unidades organizativas.
>
>Si ya ha importado la base de datos de clientes, es necesario realizar una actualización para establecer los valores de las unidades organizativas en los perfiles ya importados.

Si su organización necesita aislar los perfiles contactados por cada una de sus diferentes marcas, puede dividir los perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y deben añadirse.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **Administración > Desarrollo > Recursos personalizados**.
1. Seleccione **Perfil** o cree un nuevo recurso personalizado para ampliar los perfiles. Para obtener más información sobre cómo ampliar los perfiles, consulte esta [página](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Marque la casilla **Agregar campos de administración de autorización de acceso** para agregar las unidades organizativas en la extensión **Perfil**.

   ![](assets/user_management_9.png)

1. Haga clic en **[!UICONTROL Save]**.
1. Actualice la estructura volviendo a publicar los recursos personalizados. Para obtener más información sobre el proceso de publicación, consulte [Actualización de la estructura](../../developing/using/updating-the-database-structure.md).

El campo de unidad organizativa se agrega a los perfiles en la sección **[!UICONTROL Access authorization]**.

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)
