---
title: Marcas
description: Descubra todas las herramientas disponibles para administrar las identidades de marca.
page-status-flag: nunca activado
uuid: d66ac5a2-2ae1-4870-b48e-7f276744ffdd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: application-settings
discoiquuid: cbb1dcec-3bc6-4013-87fa-27d0e5d32bf8
context-tags: marca,descripción general;marca,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Marcas{#branding}

## Acerca de la identidad de marca {#about-brand-identity}

Cada empresa tiene directrices técnicas y visuales de marca. Con Adobe Campaign, puede definir un conjunto de especificaciones para presentar una marca coherente a sus clientes, desde logotipos hasta aspectos técnicos, como remitente de correo electrónico, dirección URL o dominios.

Los administradores técnicos pueden definir una o varias marcas para introducir de forma centralizada los parámetros que afectan a la identidad de una marca. Esto incluye el logotipo de la marca, el dominio de la dirección URL de acceso de las páginas de aterrizaje o la configuración del seguimiento de mensajes. Con Adobe Campaign, puede crear estas marcas y vincularlas a mensajes o páginas de aterrizaje. Esta configuración se administra en plantillas.

## Configuración y uso de marcas {#configuring-and-using-brands}

El principio principal de configuración y uso de marcas es:

1. Cree y configure la marca: esta operación requiere permisos específicos y la realiza el administrador técnico de Adobe Campaign.
1. Cree una o varias plantillas de página de envío y de aterrizaje para esta marca. Consulte la sección [Creación de una plantilla](../../start/using/about-templates.md) .
1. Cree mensajes y páginas de aterrizaje según esta plantilla. Consulte las secciones [Creación de un correo electrónico](../../channels/using/creating-an-email.md) y [Creación de una página](../../channels/using/designing-a-landing-page.md) de aterrizaje.

>[!CAUTION]
>
>Los usuarios finales no pueden crear ni modificar marcas: estas operaciones deben ser realizadas por el administrador técnico de Adobe Campaign. Para cualquier solicitud, póngase en contacto con el servicio de atención al cliente de Adobe. No se puede utilizar la marca múltiple en el contexto de la mensajería transaccional. Para obtener más información sobre esto, consulte Mensajes [transaccionales y marca](../../channels/using/about-transactional-messaging.md#permissions-and-branding).

Las marcas se encuentran en el **[!UICONTROL Administration > Instance settings > Brand configuration]** menú.

De forma predeterminada, una marca recién creada solo es visible para los usuarios asignados con los derechos correspondientes por el administrador.

Una **marca** se define con las siguientes características:

* Una **identidad** que define y personaliza su marca. Esta sección contiene los campos siguientes:

   ![](assets/branding_01.png)

   * **Etiqueta** visible en la interfaz
   * **Marca**
   * **Dirección URL** del sitio web y etiqueta **del** sitio web de la marca
   * **Logotipo de marca**

* **[!UICONTROL Header parameters of sent emails]** que personaliza lo que verán los destinatarios de las campañas. Esta sección contiene los campos siguientes:

   ![](assets/branding_04_header.png)

   * **Remitente (dirección de correo electrónico)** con la dirección de correo electrónico de la marca.
   * **Remitente (nombre)** con el nombre de la marca.
   * **Responder a (dirección de correo electrónico)** con la dirección de correo electrónico a la que el cliente puede responder.
   * **Responda a (nombre)** con el nombre de la marca.
   * **Error (dirección de correo electrónico)** con la dirección de correo electrónico que se utilizará en caso de error.
   >[!CAUTION]
   >
   >Después de actualizar los parámetros de encabezado de los correos electrónicos, si el nombre y la dirección de correo electrónico del remitente no han cambiado en el correo electrónico creado a partir de la plantilla, compruebe la configuración avanzada de la plantilla.

* **Los servidores expuestos en Internet** definen los servidores utilizados para el seguimiento pero también para el acceso a la página de aterrizaje. Esta sección contiene los campos siguientes:

   ![](assets/configure_branding_04.png)

   * **Dirección URL externa del servidor** de aplicaciones utilizado para alojar y acceder a las distintas páginas de aterrizaje que cree.
   * **Dirección URL externa del servidor** de seguimiento utilizada como dirección URL rastreada durante los envíos.
   * **Dirección URL externa del servidor** de páginas reflejadas que se utiliza como página de reflejo predeterminada en los envíos.

* **[!UICONTROL Tracking URL configuration (Web Analytics)]**, que define la configuración del seguimiento de direcciones URL de su marca.

   Aquí se definen los parámetros adicionales que permiten realizar el seguimiento de los vínculos en sistemas externos como herramientas de análisis web como Adobe Analytics o Google Analytics.

   ![](assets/branding_05.png)

## Asignación de una marca a un correo electrónico {#assigning-a-brand-to-an-email}

### Vinculación de una marca a una plantilla {#linking-a-brand-to-a-template}

Para utilizar los parámetros definidos para una marca, debe estar vinculado a una plantilla de entrega o a una plantilla de página de aterrizaje. Para ello, debe crear o editar una plantilla.

>[!NOTE]
>
>Para obtener más información sobre la creación de una plantilla, consulte la sección [Creación de una plantilla](../../start/using/about-templates.md) .

Una vez creada la plantilla, puede vincularla a una marca. Para ello:

1. Haga clic en el **[!UICONTROL Edit properties]** botón para acceder a las propiedades de la plantilla.

   ![](assets/branding_04.png)

1. Utilice la lista desplegable para seleccionar la marca que desea vincular a la plantilla.

   >[!NOTE]
   >
   >De forma predeterminada, **[!UICONTROL Default brand (branding)]** se selecciona la opción.

   ![](assets/branding_05.png)

   Para ver cómo está configurada la marca seleccionada, haga clic en el icono **[!UICONTROL Navigate to the detail of the element selected]** .

   ![](assets/branding_06.png)

1. Confirme la selección y guarde la plantilla.

La plantilla está vinculada a la marca. En el editor de correo electrónico, los elementos como la dirección de **correo electrónico del remitente** predeterminado, el nombre **del remitente** predeterminado o el **logotipo** utilizarán los datos de marca configurados.

### Caso de uso de marca {#branding-use-case}

En este ejemplo, vamos a crear una nueva marca relacionada con el turismo y utilizarla en un mensaje de correo electrónico.

#### Configurar una nueva marca {#configure-a-new-brand}

>[!CAUTION]
>
>La configuración de marca solo la administra Adobe, ya que requiere permisos específicos y configuración técnica.

1. El administrador de Adobe Campaign crea la marca en **[!UICONTROL Administration > Instance settings > Brand configuration]**. Agrega el elemento **Vacaciones en los trópicos** del menú avanzado y configura el **[!UICONTROL ID]** y el **[!UICONTROL Header parameters of sent emails]** de la marca.

   ![](assets/branding_07.png)

1. A continuación, el administrador configura la dirección URL de los **servidores expuestos en Internet** para que se puedan utilizar las páginas de aterrizaje y, a continuación, las direcciones URL de seguimiento.

   En este ejemplo, la herramienta **Web Analytics** utilizada es **Google Analytics**. El administrador configura la URL de seguimiento de la siguiente manera:

   ![](assets/branding_12.png)

La marca se crea y configura correctamente. Ahora puede ser utilizado por los equipos de mercadotecnia.

#### Implementar una nueva marca {#implement-a-new-brand}

Como administrador de envíos, usted se encarga de crear las plantillas de entrega para utilizar la nueva marca. Para lograrlo, siga los pasos a continuación:

1. En el menú avanzado **[!UICONTROL Resources > Templates > Delivery templates]**, duplique una plantilla integrada para configurar una nueva plantilla de entrega.

   ![](assets/branding_08.png)

1. Para vincular esta plantilla a las **Vacaciones de la marca Tropics** , edite las propiedades de la plantilla y seleccione la marca en la lista desplegable.

   ![](assets/branding_09.png)

1. Configure esta plantilla de correo electrónico para que refleje la identidad de la marca.
1. Una vez completada la plantilla, puede guardarla.

   ![](assets/branding_10.png)

   La plantilla de envío ahora se puede utilizar para crear correos electrónicos que se enviarán a una audiencia.

#### Usar la nueva marca en una entrega {#use-the-new-brand-in-a-delivery}

Para crear un correo electrónico vinculado a una marca, siga los pasos a continuación:

1. Haga clic en el **[!UICONTROL Create]** botón en el **[!UICONTROL Marketing activities]** menú.

   ![](assets/branding_14.png)

1. Seleccione la **[!UICONTROL Email]** actividad y, a continuación, elija la plantilla vinculada a la nueva marca.

   ![](assets/branding_15.png)

1. Su correo electrónico ya está configurado. Puede comprobar la información antes de probarla con los perfiles de prueba y luego enviarla a su audiencia.

   ![](assets/branding_16.png)

