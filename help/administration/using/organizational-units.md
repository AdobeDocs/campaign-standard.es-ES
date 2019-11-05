---
title: Unidades organizativas
description: Defina los niveles de acceso de los usuarios mediante unidades organizativas.
page-status-flag: nunca activado
uuid: 8c82ffea-cef4-4a89-b823-d8b7bae1db4f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: usuarios y seguridad
discoiquuid: 6f60c653-1d12-4d27-9bc8-ce8c19bca466
context-tags: orgUnit,overview;orgUnit,main;geoUnit,overview;geoUnit,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Unidades organizativas{#organizational-units}

## Acerca de las unidades {#about-units}

Cada objeto y usuario de la plataforma está vinculado a una unidad organizativa. Esta unidad permite definir una estructura jerárquica para proporcionar a los usuarios una vista filtrada. La unidad del usuario define su nivel de acceso para distintos objetos de plataforma.

>[!CAUTION]
>
>Si un usuario no está vinculado a ninguna unidad, no podrá conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule a la **[!UICONTROL All]** unidad.

Un usuario tiene acceso de solo lectura a todos los objetos de las unidades principales. Tiene acceso de lectura y escritura a todos los objetos de su unidad y unidades infantiles. Un usuario no tiene acceso a objetos en ramas paralelas.

De forma predeterminada, solo están disponibles las **[!UICONTROL All]** unidades.

Cuando se asigna al usuario una unidad organizativa, esta unidad siempre se aplicará a los objetos que el usuario haya creado.

![](assets/user_management_2.png)

>[!NOTE]
>
>Cuando un usuario está en varios grupos vinculados a distintas unidades, se aplican determinadas reglas. Para obtener más información, consulte la sección [Administración de grupos y usuarios](../../administration/using/managing-groups-and-users.md) .

## Creación y administración de unidades {#creating-and-managing-units}

Las unidades organizativas permiten filtrar la instancia en función de la organización con la que estén vinculados los usuarios. Esta unidad puede representar una región, un país o incluso una marca en su caso.

Aquí, anteriormente, creamos grupos de seguridad con diferentes funciones para dos usuarios: a un usuario se le asignan los grupos de seguridad Administradores y Geometrixx, el otro usuario pertenece a los grupos de seguridad Usuario estándar y Ropa de Geometrixx Véase [Creación de un grupo de seguridad y asignación de usuarios](../../administration/using/managing-groups-and-users.md#creating-a-security-group-and-assigning-users) para el ejemplo completo.

Ahora necesitamos crear las unidades organizativas para los grupos de seguridad Ropa de Geometrixx y Geometrixx:

1. En el menú avanzado de campaña de Adobe, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Users & security]** &gt; **[!UICONTROL Organizational units]**.
1. Haga clic en **[!UICONTROL Create]** para comenzar a configurar la unidad organizativa.

   ![](assets/manage_units_1.png)

1. Cambie el valor predeterminado **[!UICONTROL Label]** y **[!UICONTROL ID]** a Geometrixx.
1. A continuación, conecte esta unidad a una unidad principal. Aquí elegimos **[!UICONTROL All]**.

   ![](assets/manage_units_2.png)

1. Por último, haga clic en **[!UICONTROL Create]** para empezar a asignar la nueva unidad organizativa al grupo de seguridad.
1. Siga el mismo procedimiento para la unidad de vestimenta de Geometrixx, con la salvedad de que su unidad principal debe ser la unidad creada anteriormente, Geometrixx.

   ![](assets/manage_units_3.png)

Para ver el impacto de asignar diferentes unidades a diferentes grupos de seguridad, el usuario asignado a los grupos Administrador y Geometrixx creará dos plantillas de correo electrónico para ver a qué puede o no acceder el otro usuario asignado a la ropa de usuario estándar y de Geometrixx.

1. En el menú avanzado, seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Delivery Templates]**.
1. Duplique una plantilla existente y personalícela según sea necesario. For more on this, refer to the [About templates](../../start/using/about-templates.md) section.
1. Cuando se cree la plantilla, seleccione el **[!UICONTROL Edit properties]** icono para asignar unidades a la plantilla.

   ![](assets/manage_units_6.png)

1. En el menú **[!UICONTROL Access authorization]** desplegable, seleccione la unidad organizativa.

   Aquí vamos a crear una plantilla con la unidad organizativa creada anteriormente Geometrixx.

   ![](assets/manage_units_5.png)

1. Siga los mismos procedimientos para crear la segunda plantilla asignada a la unidad organizativa de Ropa de Geometrixx creada anteriormente.

El usuario asignado a los grupos Usuarios estándar y Ropa de Geometrixx podrá ver ambas plantillas. Debido a la estructura jerárquica de las unidades organizativas, tendrá acceso de lectura y escritura a la plantilla vinculada a la unidad de ropa de Geometrixx y acceso de sólo lectura a la plantilla vinculada a la unidad Geometrixx.

![](assets/manage_units_7.png)

Dado que la unidad Ropa de Geometrixx es una unidad secundaria de Geometrixx, aparece el siguiente mensaje cuando el usuario intenta modificar la plantilla de Geometrixx:

![](assets/manage_units_8.png)

Las unidades organizativas pueden restringir el acceso a diferentes funciones, como perfiles. Por ejemplo, si nuestro usuario de Ropa Geometrixx accede a la **[!UICONTROL Profiles]** ficha, podrá acceder y modificar completamente los perfiles con la unidad organizativa de Ropa Geometrixx.

Mientras que los perfiles con la unidad organizativa de Geometrixx serán de solo lectura, aparecerá el siguiente error si el usuario intenta modificar un perfil: **[!UICONTROL You do not have the rights needed to modify the 'profile' resource of ID]**.

![](assets/manage_units_10.png)

## Perfiles de partición {#partitioning-profiles}

Si su organización necesita aislar los perfiles contactados por cada una de sus distintas marcas, puede particionar los perfiles por sus unidades organizativas.

De forma predeterminada, los campos de unidad organizativa no están disponibles en los perfiles y es necesario agregarlos.

Los usuarios no pueden acceder a los perfiles sin unidades organizativas.

>[!CAUTION]
>
>Se recomienda agregar esta opción antes de importar perfiles. Si ya ha importado la base de datos de clientes, se necesita una actualización para establecer los valores de unidad organizativa en los perfiles ya importados.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **Administración &gt; Desarrollo &gt; Recursos** personalizados.
1. Seleccione **Perfil** o cree un nuevo recurso personalizado para ampliar los perfiles.
1. Marque la casilla **Agregar campos** de administración de autorización de acceso para agregar las unidades organizativas en la extensión **Perfil** .

   ![](assets/user_management_9.png)

1. Click **[!UICONTROL Save]**.
1. Actualice la estructura volviendo a publicar los recursos personalizados. Para obtener más información sobre el proceso de publicación, consulte [Actualización de la sección de estructura](../../developing/using/data-model-concepts.md) .

El campo de unidad organizativa se agrega a los perfiles en la **[!UICONTROL Access authorization]** sección .

![](assets/user_management_10.png)

**Temas relacionados**:

* [Acerca de las unidades](../../administration/using/organizational-units.md#about-units)
* [Acerca de la administración de acceso](../../administration/using/about-access-management.md)

