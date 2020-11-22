---
title: Solicitudes de privacidad
description: Obtenga información sobre cómo administrar las solicitudes de privacidad en Adobe Campaign Standard
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 06b886989243405df04b4abef46994afd980f6d8
workflow-type: tm+mt
source-wordcount: '1711'
ht-degree: 20%

---


# Administración de solicitudes de privacidad {#privacy-requests}

For a general presentation on Privacy Management, refer to [this section](../../start/using/privacy-management.md).

Esta información se aplica al RGPD, la CCPA, la PDPA y la LGPD. Para obtener más información sobre estas normativas, consulte [esta sección](../../start/using/privacy-management.md#privacy-management-regulations).

The opt-out for the Sale of Personal Information, which is specific to CCPA, is explained in [this section](#sale-of-personal-information-ccpa).

>[!IMPORTANT]
>
>A partir de la versión 19.4, el uso de la API y la interfaz de Campaign para las solicitudes de Acceso y Eliminación quedarán obsoletas. Para cualquier solicitud de acceso y eliminación de GDPR, CCPA, PDPA o LGPD, debe utilizar el método de integración de [Privacy Core Service](#create-privacy-request) .

## Acerca de las solicitudes de privacidad {#about-privacy-requests}

Para ayudarle a facilitar su preparación para la privacidad, Adobe Campaign le permite gestionar solicitudes de acceso y eliminación. El **derecho de acceso** y el **derecho a ser olvidado** (solicitud de supresión) se describen en [esta sección](../../start/using/privacy-management.md#right-access-forgotten).

Para realizar estas solicitudes, debe utilizar la integración de **Privacy Core Service** . Las solicitudes de privacidad insertadas desde Privacy Core Service a todas las soluciones de Experience Cloud se gestionan automáticamente mediante la Campaña a través de un flujo de trabajo dedicado.

### Requisitos previos {#prerequesites}

Adobe Campaign oferta las herramientas de los controladores de datos para crear y procesar solicitudes de privacidad de datos almacenados en Adobe Campaign. Sin embargo, es responsabilidad del controlador de datos administrar la relación con el sujeto de datos (correo electrónico, atención al cliente o un portal web).

Por ello, es responsabilidad del controlador de datos confirmar la identidad del sujeto de datos que realiza la solicitud y confirmar que la información devuelta al solicitante sea sobre el sujeto de datos.

>[!NOTE]
>
>Para obtener más información sobre los datos personales y las distintas entidades que administran los datos (controlador de datos, procesador de datos y sujeto de datos), consulte [Datos personales y personas](../../start/using/privacy.md#personal-data).

### Áreas de nombres {#namesspaces}

Antes de crear solicitudes de privacidad, debe definir la Área de nombres que utilizará. El área de nombres es la clave que se utiliza para identificar el sujeto de datos en la base de datos de Adobe Campaign. Hay dos Áreas de nombres disponibles: correo electrónico y teléfono móvil. Si necesita una Área de nombres diferente (por ejemplo, un campo personalizado de perfil), siga estos pasos.

Also refer to this [tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=en#privacy) on how to create a namespace.

>[!NOTE]
>
>Si utiliza varias Áreas de nombres, deberá crear una solicitud de privacidad por Área de nombres.

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Namespaces]**.

   ![](assets/privacy-namespaces.png)

1. En la lista de Áreas de nombres, haga clic en **[!UICONTROL Create]**.

   ![](assets/privacy-namespace-create.png)

1. Introduzca un **[!UICONTROL Label]**.

   ![](assets/privacy-namespace-label.png)

1. Si desea utilizar una Área de nombres de servicio de identidad existente, elija **[!UICONTROL Map from Identity Namespace Service]** y seleccione una Área de nombres de la **[!UICONTROL Identity Service Namespaces]** lista.

   ![](assets/privacy-map-from-namespace.png)

   Si desea crear una nueva Área de nombres en **[!UICONTROL Identity Service]** y asignarla en Campaña, seleccione **[!UICONTROL Create new]** e introduzca un nombre en el **[!UICONTROL Identity namespace name]** campo.

   ![](assets/privacy-create-new-namespace.png)

   Para obtener más información sobre Áreas de nombres de identidad, consulte la documentación del [Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=en) .

1. Un área de nombres de servicio de identidad se asigna a un área de nombres en Campaign. Debe especificar cómo se asignará el área de nombres en Campaign.

   Seleccione una asignación de destino (**[!UICONTROL Recipients]**, **[!UICONTROL Real-time event]** o **[!UICONTROL Subscriptions to an application]**). Si desea utilizar varias asignaciones de destino, debe crear una Área de nombres por asignación de destino.

   ![](assets/privacy-namespace-target-mapping.png)

1. Elija el **[!UICONTROL Reconciliation key]**. Este es el campo que se utilizará para identificar el asunto de datos en la base de datos de Adobe Campaign.

   ![](assets/privacy-namespace-reconciliation-key.png)

1. Haga clic en **[!UICONTROL Create]**. Ahora puede crear solicitudes de privacidad basadas en su nueva Área de nombres. Si utiliza varias Áreas de nombres, deberá crear una solicitud de privacidad por Área de nombres.

### Creating a Privacy request {#create-privacy-request}

>[!IMPORTANT]
>
>The **Privacy Core Service** integration is the method you should use for all Access and Delete requests.
>
>A partir de la versión 19.4, el uso de la API y la interfaz de Campaign para las solicitudes de Acceso y Eliminación quedarán obsoletas. Utilice el Privacy Service principal para cualquier solicitud de acceso y eliminación de RGPD, CCPA, PDPA o LGPD.

La integración de Privacy Core Service le permite automatizar sus solicitudes de privacidad en un contexto de varias soluciones a través de una sola llamada de API JSON. Las solicitudes de privacidad insertadas desde Privacy Core Service a todas las soluciones de Experience Cloud se gestionan automáticamente mediante la Campaña a través de un flujo de trabajo dedicado.

Refer to the [Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) documentation to learn how to create Privacy requests from the Privacy Core Service.

Cada trabajo del servicio principal de privacidad se divide en varias solicitudes de privacidad en Campaña, en función de cuántas Áreas de nombres se estén utilizando, una solicitud que corresponde a una Área de nombres. Además, un trabajo se puede ejecutar en varias instancias. Por lo tanto, se crean varios archivos para un trabajo. Por ejemplo, si una solicitud tiene dos Áreas de nombres y se está ejecutando en tres instancias, se envía un total de seis archivos. Un archivo por Área de nombres e instancia.

El patrón para un nombre de archivo es: `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **InstanceName**: Nombre de instancia de Campaign
* **NamespaceId**: ID de Área de nombres de servicio de identidad de la Área de nombres utilizada
* **Clave de reconciliación**: Clave de reconciliación codificada

### Lista de los recursos {#list-of-resources}

Al realizar una solicitud de privacidad de eliminación o acceso, Adobe Campaign busca todos los datos del sujeto de datos en función del valor de **reconciliación** en todos los recursos que tienen un vínculo al recurso de perfiles (tipo propio).

Esta es la lista de recursos predeterminados que se tienen en cuenta al realizar solicitudes de privacidad:

* Perfiles (destinatario)
* Registros de envío de perfil (wideLogRcp)
* Registros de seguimiento de perfil (trackingLogRcp)
* Registros de envío (Suscripciones a una aplicación) (wideLogAppSubRcp)
* Registros de seguimiento (Suscripciones a una aplicación) (trackingLogAppSubRcp)
* Suscripciones a una aplicación (appSubscriptionRcp)
* Historial de suscripciones de perfiles (subHistoRcp)
* Suscripciones de perfil (subscriptionRcp)
* Visitantes (visitante)

Si ha creado recursos personalizados que tienen un vínculo al recurso de perfiles (tipo propio), también se tendrán en cuenta. Por ejemplo, si tiene un recurso de transacción vinculado al recurso de perfiles y un recurso de detalles de transacción vinculado al recurso de transacción, ambos se tendrán en cuenta.

Consulte también [este tutorial](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=en#privacy) sobre cómo modificar los recursos personalizados.

Para que esto funcione, debe seleccionar la **[!UICONTROL Deleting the target record implies deleting records referenced by the link]** opción en el recurso personalizado:

1. Click the Adobe Campaign logo in the top left corner, then select **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]**.

1. Seleccione un recurso personalizado que tenga un vínculo al recurso de perfiles (tipo propio).

1. Haga clic en la **[!UICONTROL Links]** sección .

1. Para cada vínculo, haga clic en el icono de lápiz (**[!UICONTROL Edit properties]**).

1. En la sección **[!UICONTROL Behavior if deleted/duplicated]**, seleccione la opción **[!UICONTROL Deleting the target record implies deleting records referenced by the link]**.

   ![](assets/privacy-cus-resource-option.png)

### Estados de solicitud de privacidad {#privacy-request-statuses}

Estos son los distintos estados de las solicitudes de privacidad:

* **[!UICONTROL New]** / **[!UICONTROL Retry pending]**: en curso, el flujo de trabajo aún no ha procesado la solicitud.
* **[!UICONTROL Processing]** / **[!UICONTROL Retry in progress]**: el flujo de trabajo está procesando la solicitud.
* **[!UICONTROL Delete pending]**:: el flujo de trabajo ha identificado todos los datos de destinatario que se van a eliminar.
* **[!UICONTROL Delete in progress]**:: el flujo de trabajo está procesando la eliminación.
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Complete]**:: el procesamiento de la solicitud ha finalizado sin error.
* **[!UICONTROL Error]**:: el flujo de trabajo ha encontrado un error. El motivo se muestra en la lista de las solicitudes de privacidad de la **[!UICONTROL Request status]** columna. Por ejemplo, **[!UICONTROL Error data not found]** significa que en la base de datos no se han encontrado datos de destinatario que coincidan con los del sujeto de datos **[!UICONTROL Reconciliation value]** .

### Desactivación del proceso de 2 pasos {#disabling-two-step-process}

El Servicio principal de privacidad no admite el procesamiento en dos pasos.

>[!IMPORTANT]
>
>Antes de utilizar la integración del Servicio principal de privacidad para administrar sus solicitudes de privacidad, debe deshabilitar el procesamiento en 2 pasos para las solicitudes de Eliminación desde la interfaz de Campaign Standard.

Si esta opción no está deshabilitada, todas las solicitudes de Eliminación administradas con el Privacy Service principal permanecerán en estado pendiente y no se completarán.

De forma predeterminada, se activa el proceso de dos pasos.

Para cambiar este modo, haga clic en **[!UICONTROL Edit properties]**, en la esquina superior derecha de la **[!UICONTROL Privacy Requests]** pantalla, y desmarque la **[!UICONTROL Activate the 2-step process]** opción.

![](assets/privacy-disable-2-step-process.png)

## Exclusión para la venta de información personal (CCPA) {#sale-of-personal-information-ccpa}

The **California Consumer Privacy Act** (CCPA) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

La configuración y el uso de las solicitudes de acceso y eliminación son comunes al RGPD y a la CCPA. Esta sección presenta la exclusión de la venta de datos personales, que es específica de la CCPA.

In addition to the [Consent management](../../start/using/privacy-management.md#consent-management) tools provided by Adobe Campaign, you have the possibility to track whether a consumer has opted-out for the Sale of Personal Information.

Un consumidor decide, a través de su sistema, que no permite que su información personal se venda a un tercero. En Adobe Campaign, podrá almacenar y rastrear esta información.

>[!NOTE]
>
>Puede aprovechar la exclusión para la venta de información personal a través de la interfaz de Campaña y de la API. No puede utilizarlo a través del servicio principal de privacidad.

>[!IMPORTANT]
>
>Como controlador de datos, es su responsabilidad recibir la solicitud del sujeto de datos y realizar un seguimiento de las fechas de solicitud para CCPA. Como proveedor de tecnología, sólo ofrecemos una manera de optar por la exclusión. Para obtener más información sobre su función como controlador de datos, consulte Datos [personales y Personas](../../start/using/privacy.md#personal-data).

### Requisito previo para tablas personalizadas {#ccpa-prerequisite}

Starting 19.4, the **[!UICONTROL CCPA Opt-Out]** field is provided out-of-the-box in the Campaign interface and API. By default, the field is available for the standard **[!UICONTROL Profile]** resource.

Si utiliza un recurso de perfil personalizado, debe extender el recurso y agregar el campo. We recommend that you use a different name than the out-of-the-box field, for example:  **[!UICONTROL Opt-Out for CCPA]** (optoutccpa). Cuando se crea un nuevo campo, se vuelve compatible con la API de Campaign de forma automática.

For more detailed information on how to extend the profile resource, see [this section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

>[!NOTE]
>
>La modificación de recursos es una operación delicada que sólo deben realizar los usuarios expertos.

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**. Haga clic en el recurso de perfil personalizado. For more on extending a resource, see [this section](../../developing/using/creating-or-extending-the-resource.md).

   ![](assets/privacy-ccpa-extend-cus.png)

1. Haga clic en **[!UICONTROL Add field]** o **[!UICONTROL Create Element]**, agregue la etiqueta, ID y elija el **[!UICONTROL Boolean]** tipo. Para el nombre, utilice **Opción de exclusión para CCPA**. Para el ID, utilice: **optOutCcpa**.

   ![](assets/privacy-ccpa-extend-field.png)

1. En la **[!UICONTROL Screen definition]** ficha, debajo de **[!UICONTROL Detail screen configuration]**, agregue el campo y seleccione **[!UICONTROL Input field]**. Esto hará que el campo esté disponible en la lista y los detalles de perfiles.  For more on configuring the screen definition, see [this section](../../developing/using/configuring-the-screen-definition.md).

   ![](assets/privacy-ccpa-extend-screen.png)

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publishing]**, prepare la publicación y publique las modificaciones. For more on publishing a resource, see [this section](../../developing/using/updating-the-database-structure.md).

   ![](assets/privacy-ccpa-extend-pub.png)

1. Compruebe que el campo está disponible en los detalles de un perfil. Para obtener más información, consulte [esta sección](#usage).

### Uso {#usage}

Es responsabilidad del controlador de datos llenar el valor del campo y seguir las directrices y normas de la CCPA relativas a la venta de datos.

Para rellenar estos valores, se pueden usar varios métodos:

* Uso de la interfaz de la Campaña mediante la edición de los detalles del destinatario (véase más abajo)
* Using the Campaign Privacy API (see the [API documentation](../../api/using/managing-ccpa-opt-out.md))
* a través de un flujo de trabajo de importación de datos.

A continuación, debe asegurarse de que nunca vende a terceros la información personal de los perfiles que han optado por la exclusión.

1. En la interfaz de la Campaña, edite un perfil para cambiar el estado de exclusión.

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. When the value of the field is **[!UICONTROL True]**, the information is displayed on the profile&#39;s details.

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. Puede configurar la lista perfiles para que muestre la columna de salida. Para obtener información sobre cómo configurar listas, consulte [esta sección](../../start/using/customizing-lists.md).

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. Puede hacer clic en la columna para ordenar los destinatarios según la información de exclusión.

   ![](assets/privacy-ccpa-profile-sorting.png)