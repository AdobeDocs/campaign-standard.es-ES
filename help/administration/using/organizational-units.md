---
title: Unidades organizativas
description: Defina los niveles de acceso de los usuarios mediante unidades organizativas.
page-status-flag: never-activated
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: users-and-security
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 4%

---


# Unidades organizativas{#organizational-units}

## Acerca de las unidades {#about-units}

Cada objeto y usuario de la plataforma está vinculado a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para dar a los usuarios una vista filtrada. La unidad de un usuario define su nivel de acceso para diferentes objetos de plataforma.

>[!IMPORTANT]
>
>Si un usuario no está vinculado a ninguna unidad, no podrá conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule a la **[!UICONTROL All]** unidad.
>
>De forma predeterminada, la **[!UICONTROL All (all)]** unidad organizativa se asigna al grupo de seguridad **[!UICONTROL Administrators]**. Es de solo lectura y no se puede modificar.

Un usuario tiene acceso de solo lectura a todos los objetos de las unidades principales. Tiene acceso de lectura y escritura a todos los objetos de su unidad y unidades infantiles. Un usuario no tiene acceso a objetos en ramas paralelas.

De forma predeterminada, solo están disponibles las **[!UICONTROL All]** unidades.

Cuando al usuario se le asigna una unidad organizativa, esta unidad siempre se aplicará a los objetos que el usuario haya creado.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario se encuentra en varios grupos vinculados a distintas unidades, se aplican determinadas reglas. Para obtener más información, consulte la sección [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md) .

## Creating and managing units {#creating-and-managing-units}

Las unidades organizativas permiten filtrar la instancia en función de la organización con la que estén vinculados los usuarios. Esta unidad puede representar una región, un país o incluso una marca en su caso.

Aquí, anteriormente, creamos grupos de seguridad con diferentes funciones para dos usuarios: a un usuario se le asignan los grupos de seguridad Administradores y Geometrixx, el otro usuario pertenece a los grupos de seguridad Usuarios estándar y Ropa de Geometrixx Véase [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para el ejemplo completo.

Ahora necesitamos crear las unidades organizativas para los grupos de seguridad de ropa de Geometrixx y Geometrixx:

1. En el menú avanzado de campaña de Adobe, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Users & security]** > **[!UICONTROL Organizational units]**.
1. Haga clic en **[!UICONTROL Create]** para configurar el inicio de su unidad organizativa.

   ![](assets/manage_units_1.png)

1. Cambie el valor predeterminado **[!UICONTROL Label]** y **[!UICONTROL ID]** a Geometrixx.
1. A continuación, vincule esta unidad a una unidad principal. Aquí elegimos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Finalmente, haga clic en **[!UICONTROL Create]** el inicio para asignar la nueva unidad organizativa al grupo de seguridad.
1. Siga el mismo procedimiento para la unidad Ropa de Geometrixx, excepto que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de asignar diferentes unidades a diferentes grupos de seguridad, el usuario asignado a los grupos Administrador y Geometrixx creará dos plantillas de correo electrónico para ver a qué puede o no acceder el otro usuario asignado a Usuarios estándar y Ropa de Geometrixx.

1. En el menú avanzado, seleccione **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Delivery Templates]**.
1. Duplicado una plantilla existente y personalícela según sea necesario. Para obtener más información, consulte la sección [Acerca de las plantillas](../../start/using/marketing-activity-templates.md).
1. Cuando se cree la plantilla, seleccione el **[!UICONTROL Edit properties]** icono para asignar unidades a la plantilla.

   ![](assets/manage_units_6.png)

1. En el menú **[!UICONTROL Access authorization]** desplegable, seleccione la unidad organizativa.

   Aquí vamos a crear una plantilla con la Geometrixx de unidad organizativa creada anteriormente.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad organizativa de ropa de Geometrixx creada anteriormente.

El usuario asignado a los grupos Usuarios estándar y Ropa de Geometrixx podrá ver ambas plantillas. Debido a la estructura jerárquica de las unidades organizativas, tendrá acceso de lectura y escritura a la plantilla vinculada a la unidad Ropa de Geometrixx y sólo acceso de sólo lectura a la plantilla vinculada a la unidad de Geometrixx.

![](assets/manage_units_7.png)

Dado que la unidad Ropa de Geometrixx es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando el usuario intenta modificar la plantilla de Geometrixx:

![](assets/manage_units_8.png)

Las unidades organizativas pueden restringir el acceso a diferentes funciones, como perfiles. Por ejemplo, si nuestro usuario de Ropa de Geometrixx accede a la **[!UICONTROL Profiles]** ficha, podrá acceder y modificar completamente los perfiles con la unidad organizativa de Ropa de Geometrixx.

Mientras que los perfiles con la unidad organizativa de la Geometrixx serán de solo lectura, aparecerá el siguiente error si nuestro usuario intenta modificar un perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Perfiles de partición {#partitioning-profiles}

Si su organización necesita aislar los perfiles con los que se ha puesto en contacto cada una de sus distintas marcas, puede dividir sus perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y es necesario agregarlos.

Los usuarios no pueden acceder a los perfiles sin unidades organizativas.

>[!IMPORTANT]
>
>Se recomienda agregar esta opción antes de importar perfiles. Si ya ha importado la base de datos de clientes, se necesita una actualización para establecer los valores de unidad organizativa en los Perfiles ya importados.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Administración > Desarrollo > Recursos** personalizados.
1. Seleccione **Perfil** o cree un nuevo recurso personalizado para ampliar los perfiles.
1. Marque la casilla **Añadir campos** de administración de autorización de acceso para agregar las unidades organizativas en la extensión de **Perfil** .

   ![](assets/user_management_9.png)

1. Haga clic en **[!UICONTROL Save]**.
1. Actualice la estructura volviendo a publicar los recursos personalizados. Para obtener más información sobre el proceso de publicación, consulte [Actualización de la sección de estructura](../../developing/using/data-model-concepts.md) .

El campo Unidad organizativa se agrega a los perfiles en la **[!UICONTROL Access authorization]** sección.

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)

