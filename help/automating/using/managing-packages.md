---
title: Administración de paquetes
seo-title: Administración de paquetes
description: Administración de paquetes
seo-description: Los administradores pueden definir paquetes para intercambiar recursos entre distintas instancias de Adobe Campaign a través de archivos XML estructurados.
page-status-flag: no activado nunca
uuid: d 041 f 549-bfc 5-4 e 6 b -87 bf-a 63 c 7 c 224 bca
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: importar y exportar datos
discoiquuid: c 3015 cdc -8432-4 e 57-8 ac 0-43 ae 7827 e 3 b 0
context-tags: Packagedef, overview; Packageinstall, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Managing packages{#managing-packages}

Los administradores pueden definir paquetes para intercambiar recursos entre distintas instancias de Adobe Campaign a través de archivos XML estructurados. Pueden ser parámetros o datos de configuración.

Esto puede resultar útil para transferir datos de un servidor a otro o para replicar la configuración de una instancia.

Packages are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]** or **[!UICONTROL Package imports]** menus. Los dos menús funcionan de forma similar.

Los elementos de cada lista se muestran de forma predeterminada según su modificación o fecha de instalación, de las más recientes a las menos recientes.

![](assets/packages_1.png)

Para mostrar y modificar el contenido de un elemento, haga clic en su etiqueta. Refer to the [Exporting a package](../../automating/using/managing-packages.md#exporting-a-package) and [Importing a package](../../automating/using/managing-packages.md#importing-a-package) sections.

## Package exports {#package-exports}

### Standard packages {#standard-packages}

**[!UICONTROL Platform]** y **[!UICONTROL Administration]** son dos paquetes integrados, cada uno de los cuales contiene una lista predefinida de recursos que exportar. Se pueden abrir en modo de solo lectura y solo son adecuados para la exportación.

![](assets/packages_14.png)

>[!CAUTION]
>
>La exportación de paquetes no está autorizada si los recursos exportados tienen ID predeterminados. Por lo tanto, los ID de recursos exportables deben cambiarse empleando un nombre distinto de las plantillas proporcionadas como estándar por Adobe Campaign Standard. Por ejemplo, para exportar perfiles de prueba, no se debe utilizar un ID que contenga el valor "SDM" o "sdm". Al intentar exportar paquetes que contengan ID predeterminados, se pueden ver errores como: " El tipo de entidad'Marcas (marca)' utiliza un ID predeterminado (' BRD 1 ') que puede provocar un conflicto al importar el paquete. Cambie este nombre y repita la operación. "

The package export steps are described in the [Exporting a package](../../automating/using/managing-packages.md#exporting-a-package) section.

* **[!UICONTROL Platform]** El paquete recupera todos los recursos añadidos durante la configuración técnica: recursos personalizados, conjuntos de recursos personalizados, activadores y opciones de aplicación con **[!UICONTROL System]** el tipo.
* **[!UICONTROL Administration]** El paquete recupera todos los objetos añadidos durante la configuración comercial como: plantillas de campaña, plantillas de contenido, plantillas de envío, plantillas de página de aterrizaje, plantillas de programa y plantillas de flujo de trabajo.

   It also includes the following objects: content blocks, target mappings, external accounts, organizational units, application options with the **[!UICONTROL User]** type, roles, typologies, typology rules and users.

>[!NOTE]
>
>El contenido de estos dos paquetes no puede modificarse. Por el contrario, estos paquetes siempre contienen los datos más actualizados disponibles. [Puede crear sus propios paquetes](../../automating/using/managing-packages.md#creating-a-package) para exportar elementos específicos.

### Creating a package {#creating-a-package}

Debe crear un paquete si necesita exportar conjuntos específicos de datos.

Para crear un paquete, necesita los derechos de administración.

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]**, click the **[!UICONTROL Create]** button in the list of package contents.

   El elemento se crea inmediatamente. Para cancelar la creación, vuelva a la lista y marque el cuadro correspondiente para eliminarlo.

1. En la pantalla de contenido del paquete, especifique un nombre y un ID.
1. Click the **[!UICONTROL Edit properties]** button if you would like to add a description and restrict access to certain users.

   ![](assets/packages_18.png)

1. Use the **[!UICONTROL Create element]** button in the **[!UICONTROL Export content]** tab to select the resources you wish to export.

   ![](assets/packages_2.png)

1. Los recursos se muestran en orden alfabético y se pueden filtrar por nombre. Su nombre técnico se muestra entre corchetes. Seleccione un elemento de la lista y confirme.

   ![](assets/packages_3.png)

1. The resource name is displayed in the **[!UICONTROL Export content]** tab. To modify a resource, check the corresponding box and use the **[!UICONTROL Show detail of the element selected]** button.

   ![](assets/packages_4.png)

1. El uso del editor de consultas permite filtrar los elementos que se exportarán. For more on this, refer to the [Editing queries](../../automating/using/editing-queries.md#creating-queries) section.

   ![](assets/packages_5.png)

   >[!NOTE]
   >
   >Puede exportar hasta 5000 objetos por medio.

1. Una vez que haya especificado todos los recursos que desee exportar, guarde su selección.

El paquete ahora se crea y está listo para exportarse.

### Exporting a package {#exporting-a-package}

Exportar un paquete permite guardar un estado específico de un recurso que podrá volver a importar en otra instancia o posterior en la misma instancia.

>[!CAUTION]
>
>La exportación de paquetes no está autorizada si los recursos exportados tienen ID predeterminados. Por lo tanto, los ID de recursos exportables deben cambiarse empleando un nombre distinto de las plantillas proporcionadas como estándar por Adobe Campaign Standard. Por ejemplo, para exportar perfiles de prueba, no se debe utilizar un ID que contenga el valor "SDM" o "sdm".

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package exports]**, select a package to access its detail.
1. Compruebe que el paquete contiene los datos que necesita.
1. Click the **[!UICONTROL Start export]** button.

El archivo exportado se almacena en la carpeta de descarga del navegador en uso. Se denomina automáticamente "package_xxx.xml", por lo que "xxx" corresponde al ID del paquete.

Cuando la operación ha finalizado, aparecen varias secciones:

* **[!UICONTROL Export status]**: esta sección muestra si la operación se ha llevado a cabo correctamente.

   ![](assets/packages_6.png)

* You can consult the different steps of the export via the **[!UICONTROL Log]** tab. Contiene los estados de todas las exportaciones anteriores.

   ![](assets/packages_7.png)

>[!NOTE]
>
>When selecting an element from the package content list that has already been exported, the **[!UICONTROL Log]** and **[!UICONTROL Last export]** tabs are still available.

## Package imports {#package-imports}

### System updates {#system-updates}

La lista de importación de paquetes anterior contiene las importaciones automáticas vinculadas a las actualizaciones realizadas por Adobe.

![](assets/packages_15.png)

The **[!UICONTROL Execution logs]** tab stores all of the import steps. Un panel lateral muestra la información general.

![](assets/packages_11.png)

>[!NOTE]
>
>Estos elementos son accesibles en modo de solo lectura.

### Importing a package {#importing-a-package}

Un administrador puede importar manualmente un paquete procedente de una exportación ejecutada anteriormente desde una instancia de Adobe Campaign. For more on this, refer to the [Package exports](../../automating/using/managing-packages.md#package-exports) section.

La importación manual del paquete consiste en dos pasos: primero, debe cargar un archivo, luego puede importar su contenido.

1. From **[!UICONTROL Administration]** &gt; **[!UICONTROL Deployment]** &gt; **[!UICONTROL Package imports]**, click the **[!UICONTROL Create]** button in the package import list.

   El elemento se crea inmediatamente. Para cancelar la creación, vuelva a la lista y marque el cuadro correspondiente para eliminarlo.

1. Especifique un nombre y un ID para la nueva importación.
1. Select the file you wish to upload by dragging and dropping it, or by clicking the **[!UICONTROL Select from folder]** link.

   Los archivos importados deben ser XML o ZIP (con un archivo XML).

   ![](assets/packages_16.png)

   >[!NOTE]
   >
   >Para reemplazar el documento cargado, empiece por eliminar el archivo a través del icono X a la derecha del nombre y, a continuación, repita la operación.

1. Once the file is uploaded, import its content into the database by using the **[!UICONTROL Start import]** button.

   ![](assets/packages_19.png)

Cuando la operación ha finalizado, aparecen varias secciones:

* **[!UICONTROL Import status]**: esta sección muestra si la operación se ha llevado a cabo correctamente.
* You can consult the different steps of the import via the **[!UICONTROL Execution logs]** tab. Esto es especialmente importante para ver errores.

   ![](assets/packages_20.png)

Una vez importado el paquete, no puede volver a importarlo desde el mismo elemento. Solo puede modificar su etiqueta y su ID.

Para volver a importar el mismo paquete, tiene que volver a la lista de importación del paquete, crear un elemento y, a continuación, cargar nuevamente el archivo seleccionado.
