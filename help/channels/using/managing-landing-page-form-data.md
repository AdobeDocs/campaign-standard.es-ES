---
title: Administración de datos de formulario de una página de aterrizaje
description: Obtenga información sobre cómo administrar los datos de formularios de páginas de aterrizaje.
page-status-flag: never-activated
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '394'
ht-degree: 100%

---


# Administración de datos de formulario de una página de aterrizaje{#managing-landing-page-form-data}

## Cambio de las propiedades de datos de un formulario de una página de aterrizaje{#changing-a-landing-page-form-data-properties}

Puede vincular campos de base de datos a la zona de entrada, el botón de opción o los bloques de tipo casilla de verificación. Para ello, seleccione el bloque e introduzca los **[!UICONTROL Form data]** en la paleta.

![](assets/delivery_content_9.png)

* La zona de entrada de **Campo** permite seleccionar un campo de base de datos para vincularlo al campo de formulario.
* La opción **Obligatorio** le permite autorizar el envío de la página únicamente si el usuario ha rellenado el campo. Si no se rellena un campo obligatorio, aparece un mensaje de error.

## Asignación de campos de formulario {#mapping-form-fields}

Los campos de entrada se utilizan para almacenar o actualizar datos en la base de datos de Campaign. Para esto, debe vincular campos de base de datos con la zona de entrada, el botón de opción o los bloques de tipo casilla de verificación. Para ello:

1. Seleccione un bloque en la página de aterrizaje.
1. Complete la parte **[!UICONTROL Form data]** de la paleta.

   ![](assets/editing_lp_content_4.png)

1. Elija un campo de base de datos para establecer un vínculo con el campo de formulario en la zona de selección **[!UICONTROL Field]**. Las páginas de aterrizaje solo se pueden asignar con **Perfiles**.

1. Seleccione la opción **[!UICONTROL Mandatory]** si es necesario. La página solo se puede enviar si el usuario ha completado este campo. Si no se completa un campo obligatorio, aparecerá un mensaje de error cuando el usuario valida la página.

1. Defina el tipo de campo eligiendo, por ejemplo, **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]** en el área de selección **[!UICONTROL HTML type of the field]**.
Si elige una **[!UICONTROL Checkbox]** obligatoria, asegúrese de que es del tipo **[!UICONTROL Field]**.

>[!NOTE]
>
>Los campos predeterminados de las páginas de aterrizaje integradas están preconfigurados. Puede modificarlos según sea necesario.

## Almacenamiento y reconciliación de datos{#data-storage-and-reconciliation}

Los parámetros de reconciliación de datos le permiten definir cómo se administran los datos introducidos en la página de aterrizaje una vez que los ha enviado un usuario.

Para ello:

1. Edite las propiedades de página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del panel de página de aterrizaje y muestre los parámetros de **[!UICONTROL Job]**.

   ![](assets/lp_parameters_4.png)

1. Seleccione la **[!UICONTROL Reconciliation key]**: estos campos de base de datos como, por ejemplo, correo electrónico, nombre y apellidos, se utilizan para determinar si el visitante tiene un perfil que ya se conoce en la base de datos de Adobe Campaign. Esto le permite actualizar o crear un perfil según los parámetros de la estrategia de actualización definidos.
1. Defina el **[!UICONTROL Form parameter mapping]**: esta sección le permite asignar los parámetros del campo de página de aterrizaje y los que se utilizan en la clave de reconciliación.
1. Seleccione la **[!UICONTROL Update strategy]**: si la clave de reconciliación recupera un perfil existente en la base de datos, puede elegir que este perfil se actualice con los datos introducidos en el formulario o evitar esta actualización.
