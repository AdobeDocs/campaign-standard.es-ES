---
solution: Campaign Standard
product: campaign
title: Unidades organizativas
description: Defina los niveles de acceso de los usuarios mediante unidades organizativas.
audience: administration
content-type: reference
topic-tags: users-and-security
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 824c91669bd717e5bf31dab9005e4c3b9e497edf
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---


# Unidades organizativas{#organizational-units}

## Acerca de las unidades {#about-units}

Cada objeto y usuario de la plataforma está vinculado a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para dar a los usuarios una vista filtrada. La unidad de un usuario define su nivel de acceso para diferentes objetos de plataforma.

>[!IMPORTANT]
>
>Si un usuario no está vinculado a ninguna unidad, no podrá conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule a la unidad **[!UICONTROL All]**. Se recomienda agregar la opción **Campos de administración de autorización de acceso** antes de importar perfiles. Para obtener más información, consulte [esta sección](../../administration/using/organizational-units.md#partitioning-profiles).
>
>De forma predeterminada, la **[!UICONTROL All (all)]** unidad organizativa se asigna al grupo de seguridad **[!UICONTROL Administrators]**. Es de solo lectura y no se puede modificar.

Un usuario tiene acceso de solo lectura a todos los objetos de las unidades principales. Tiene acceso de lectura y escritura a todos los objetos de su unidad y unidades infantiles. Un usuario no tiene acceso a objetos en ramas paralelas.

De forma predeterminada, solo están disponibles las **[!UICONTROL All]** unidades.

Cuando al usuario se le asigna una unidad organizativa, esta unidad siempre se aplicará a los objetos que el usuario haya creado.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario se encuentra en varios grupos vinculados a distintas unidades, se aplican determinadas reglas. Para obtener más información, consulte la sección [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md).

## Creación y administración de unidades {#creating-and-managing-units}

Las unidades organizativas permiten filtrar la instancia en función de la organización con la que estén vinculados los usuarios. Esta unidad puede representar una región, un país o incluso una marca en su caso.

Aquí, anteriormente, creamos grupos de seguridad con diferentes funciones para dos usuarios: a un usuario se le asignan los grupos de seguridad Administradores y Geometrixx, el otro usuario pertenece a los grupos de seguridad Usuarios estándar y Ropa de Geometrixx Véase [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para el ejemplo completo.

Ahora necesitamos crear las unidades organizativas para los grupos de seguridad de ropa de Geometrixx y Geometrixx:

1. En el menú avanzado de campaña de Adobe, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Haga clic en **[!UICONTROL Create]** para obtener inicios para configurar la unidad organizativa.

   ![](assets/manage_units_1.png)

1. Cambie los valores predeterminados **[!UICONTROL Label]** y **[!UICONTROL ID]** a Geometrixx.
1. A continuación, vincule esta unidad a una unidad principal. Aquí elegimos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Por último, haga clic en **[!UICONTROL Create]** para que el inicio asigne la nueva unidad organizativa al grupo de seguridad.
1. Siga el mismo procedimiento para la unidad Ropa de Geometrixx, excepto que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de asignar diferentes unidades a diferentes grupos de seguridad, el usuario asignado a los grupos Administrador y Geometrixx creará dos plantillas de correo electrónico para ver a qué puede o no acceder el otro usuario asignado a Usuarios estándar y Ropa de Geometrixx.

1. En el menú avanzado, seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplicado una plantilla existente y personalícela según sea necesario. Para obtener más información, consulte la sección [Acerca de las plantillas](../../start/using/marketing-activity-templates.md).
1. Cuando se cree la plantilla, seleccione el icono **[!UICONTROL Edit properties]** para asignar unidades a la plantilla.

   ![](assets/manage_units_6.png)

1. En el menú desplegable **[!UICONTROL Access authorization]**, seleccione la unidad organizativa.

   Aquí vamos a crear una plantilla con la Geometrixx de unidad organizativa creada anteriormente.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad organizativa de ropa de Geometrixx creada anteriormente.

El usuario asignado a los grupos Usuarios estándar y Ropa de Geometrixx podrá ver ambas plantillas. Debido a la estructura jerárquica de las unidades organizativas, tendrá acceso de lectura y escritura a la plantilla vinculada a la unidad Ropa de Geometrixx y sólo acceso de sólo lectura a la plantilla vinculada a la unidad de Geometrixx.

![](assets/manage_units_7.png)

Dado que la unidad Ropa de Geometrixx es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando el usuario intenta modificar la plantilla de Geometrixx:

![](assets/manage_units_8.png)

Las unidades organizativas pueden restringir el acceso a diferentes funciones, como perfiles. Por ejemplo: si el usuario de la ropa de Geometrixx accede a la ficha **[!UICONTROL Profiles]**, podrá acceder y modificar completamente los perfiles con la unidad organizativa de la ropa de Geometrixx.

Mientras que los perfiles con la unidad organizativa de la Geometrixx serán de solo lectura, aparecerá el siguiente error si nuestro usuario intenta modificar un perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Perfiles de partición {#partitioning-profiles}

>[!IMPORTANT]
>
>Se recomienda agregar esta opción antes de importar perfiles, ya que los usuarios no pueden acceder a perfiles sin unidades organizativas.
>
>Si ya ha importado la base de datos de clientes, se necesita una actualización para establecer los valores de unidad organizativa en los perfiles ya importados.

Si su organización necesita aislar los perfiles con los que se ha puesto en contacto cada una de sus distintas marcas, puede dividir sus perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y es necesario agregarlos.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Administración > Desarrollo > Recursos personalizados**.
1. Seleccione **Perfil** o cree un nuevo recurso personalizado para extender los perfiles. Para obtener más información sobre cómo extender los perfiles, consulte esta [página](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource).
1. Marque la casilla **Añadir campos de administración de autorización de acceso** para agregar las unidades organizativas en la extensión **Perfil**.

   ![](assets/user_management_9.png)

1. Haga clic en **[!UICONTROL Save]**.
1. Actualice la estructura volviendo a publicar los recursos personalizados. Para obtener más información sobre el proceso de publicación, consulte la sección [Actualización de la estructura](../../developing/using/updating-the-database-structure.md).

El campo de unidad organizativa se agrega a sus perfiles en la sección **[!UICONTROL Access authorization]**.

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)

