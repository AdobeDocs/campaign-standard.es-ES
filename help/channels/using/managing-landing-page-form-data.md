---
title: Administración de datos de formulario de una página de aterrizaje
description: Obtenga información sobre cómo administrar los datos del formulario de página de aterrizaje.
page-status-flag: nunca activado
uuid: 5b222ea2-6628-457f-a618-bfc0e5eb93dd
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: landing-pages
discoiquuid: 899c7152-f415-4df9-b4b4-5ff3470a4e32
context-tags: landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Administración de datos de formulario de una página de aterrizaje{#managing-landing-page-form-data}

## Cambio de las propiedades de datos de un formulario de página de aterrizaje{#changing-a-landing-page-form-data-properties}

Puede vincular campos de base de datos a zonas de entrada, botones de opción o bloques de tipo de casilla de verificación. Para ello, seleccione el bloque e introduzca el **[!UICONTROL Form data]** en la paleta.

![](assets/delivery_content_9.png)

* The **Field** input zone lets you select a database field to link with the form field.
* The **Mandatory** option lets you only authorize the page's submission if the user has filled in the field. Si no se rellena un campo obligatorio, aparecerá un mensaje de error.

## Asignación de campos de formulario {#mapping-form-fields}

Los campos de entrada se utilizan para almacenar o actualizar datos en la base de datos de Campaign. Para ello, debe vincular los campos de la base de datos con la zona de entrada, el botón de radio o los bloques de tipo de casilla de verificación. Para ello:

1. Seleccione un bloque en la página de aterrizaje.
1. Complete la **[!UICONTROL Form data]** parte de la paleta.

   ![](assets/editing_lp_content_4.png)

1. Elija un campo de base de datos para establecer un vínculo con el campo de formulario en la zona de **[!UICONTROL Field]** selección.

   Cuando se selecciona la **[!UICONTROL Mandatory]** opción, la página solo se puede enviar si el usuario ha completado este campo. Si no se completa un campo obligatorio, aparecerá un mensaje de error cuando el usuario valide la página.

   >[!NOTE]
   >
   >Las páginas de aterrizaje solo se pueden asignar con **perfiles**.

1. Defina el tipo de campo eligiendo, por ejemplo **[!UICONTROL Text]**, **[!UICONTROL Number]** o **[!UICONTROL Date]** en el área de **[!UICONTROL HTML type of the field]** selección.

>[!NOTE]
>
>Los campos predeterminados de las páginas de aterrizaje integradas están preconfigurados. Puede modificarlas según sea necesario.

## Vinculación de un formulario a un servicio {#linking-a-form-to-a-service}

Puede vincular un formulario a un servicio para que los perfiles se puedan suscribir a un servicio específico al validar las páginas de aterrizaje.

Los parámetros para vincular una página de aterrizaje permiten especificar el tipo de acción realizado y si la página de aterrizaje está vinculada específicamente a un único servicio o si es genérica.

Para seleccionar el servicio que desea vincular, debe:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del tablero de la página de aterrizaje y muestre los **[!UICONTROL Job]** parámetros.

   ![](assets/lp_edit_properties_button.png)

1. Elija **[!UICONTROL Subscription]** en la lista **[!UICONTROL Specific actions]** desplegable.

   ![](assets/lp_parameters_5.png)

1. Seleccione **[!UICONTROL Specific service]** para vincular la página de aterrizaje a un solo servicio. No seleccione esta opción si desea utilizar varios servicios con la página de aterrizaje.

   Utilice la **[!UICONTROL Specified service in the URL]** opción para permitir que la página de aterrizaje se utilice en varios servicios. Por lo tanto, debe hacer referencia a la página de aterrizaje al configurar el servicio.

## Almacenamiento y reconciliación de datos{#data-storage-and-reconciliation}

Los parámetros de reconciliación de datos permiten definir cómo se administran los datos introducidos en la página de aterrizaje una vez que los ha enviado un usuario.

Para ello:

1. Edite las propiedades de la página de aterrizaje a las que se accede mediante el icono ![](assets/edit_darkgrey-24px.png) del tablero de la página de aterrizaje y muestre los **[!UICONTROL Job]** parámetros.

   ![](assets/lp_parameters_4.png)

1. Seleccione el **[!UICONTROL Reconciliation key]**: estos campos de base de datos (por ejemplo: correo electrónico, nombre y apellidos) se utilizan para determinar si el visitante tiene un perfil que ya se conoce en la base de datos de Adobe Campaign. Esto le permite actualizar o crear un perfil, según los parámetros de la estrategia de actualización definidos.
1. Defina el **[!UICONTROL Form parameter mapping]**: esta sección le permite asignar los parámetros de campo de página de aterrizaje y los utilizados en la clave de reconciliación.
1. Seleccione el **[!UICONTROL Update strategy]**: si la clave de reconciliación recupera un perfil de base de datos existente, puede elegir que este perfil se actualice con los datos introducidos en el formulario o evitar esta actualización.
