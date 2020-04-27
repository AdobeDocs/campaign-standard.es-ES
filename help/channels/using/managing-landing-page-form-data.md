---
title: Administración de datos de formulario de una página de aterrizaje
description: Obtenga información sobre cómo administrar los datos de formularios de página de aterrizaje.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 8c24e048c698f7ad699e83a753c114fcfd25f6a0

---


# Administración de datos de formulario de una página de aterrizaje{#managing-landing-page-form-data}

## Cambio de las propiedades de datos de un formulario de página de aterrizaje{#changing-a-landing-page-form-data-properties}

Puede vincular campos de base de datos a zonas de entrada, botones de opción o bloques de tipo de casilla de verificación. Para ello, seleccione el bloque e introduzca el **[!UICONTROL Form data]** en la paleta.

![](assets/delivery_content_9.png)

* The **Field** input zone lets you select a database field to link with the form field.
* The **Mandatory** option lets you only authorize the page&#39;s submission if the user has filled in the field. Si no se rellena un campo obligatorio, aparecerá un mensaje de error.

## Asignación de campos de formulario {#mapping-form-fields}

Los campos de entrada se utilizan para almacenar o actualizar datos en la base de datos de Campañas. Para ello, debe vincular los campos de la base de datos con la zona de entrada, el botón de radio o los bloques de tipo de casilla de verificación. Para ello:

1. Seleccione un bloque en la página de aterrizaje.
1. Complete la **[!UICONTROL Form data]** parte de la paleta.

   ![](assets/editing_lp_content_4.png)

1. Elija un campo de base de datos para establecer un vínculo con el campo de formulario en la zona de **[!UICONTROL Field]** selección. Las Páginas de aterrizaje solo se pueden asignar con **Perfiles**.

1. Seleccione la **[!UICONTROL Mandatory]** opción si es necesario. La página solo se puede enviar si el usuario ha completado este campo. Si no se completa un campo obligatorio, aparecerá un mensaje de error cuando el usuario valide la página.

1. Defina el tipo de campo eligiendo, por ejemplo **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]** en el área de **[!UICONTROL HTML type of the field]** selección.
Si elige una opción obligatoria **[!UICONTROL Checkbox]**, asegúrese de que es de **[!UICONTROL Field]** tipo.

>[!NOTE]
>
>Los campos predeterminados de las páginas de aterrizaje integradas están preconfigurados. Puede modificarlas según sea necesario.

## almacenamiento y reconciliación de datos{#data-storage-and-reconciliation}

Los parámetros de reconciliación de datos permiten definir cómo se administran los datos introducidos en la página de aterrizaje una vez que los ha enviado un usuario.

Para ello:

1. Edite las propiedades de página de aterrizaje a las que se accede mediante el ![](assets/edit_darkgrey-24px.png) icono del panel de página de aterrizaje y muestre los **[!UICONTROL Job]** parámetros.

   ![](assets/lp_parameters_4.png)

1. Seleccione el **[!UICONTROL Reconciliation key]**: estos campos de base de datos (por ejemplo: correo electrónico, nombre, apellidos) se utilizan para determinar si el visitante tiene un perfil que ya se conoce en la base de datos de Adobe Campaign. Esto le permite actualizar o crear un perfil, según los parámetros de la estrategia de actualización definidos.
1. Defina el **[!UICONTROL Form parameter mapping]**: esta sección le permite asignar los parámetros del campo de página de aterrizaje y los que se utilizan en la clave de reconciliación.
1. Seleccione el **[!UICONTROL Update strategy]**: si la clave de reconciliación recupera un perfil de base de datos existente, puede elegir que este perfil se actualice con los datos introducidos en el formulario o evitar esta actualización.
