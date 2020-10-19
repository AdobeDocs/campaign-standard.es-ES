---
title: Uso de plantillas de envíos
seo-title: Uso de plantillas de envíos
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 100f7eef03d10a66832920708ad415f8f0d3883c
workflow-type: tm+mt
source-wordcount: '802'
ht-degree: 58%

---


# Uso de plantillas {#use-templates}

Las plantillas de envíos ofrecen una mayor eficiencia al proporcionar escenarios listos para usar para los tipos de actividades más comunes. Con las plantillas, los especialistas en marketing pueden implementar nuevas campañas con una personalización mínima en un período de tiempo más corto.

Obtenga más información sobre las plantillas de envíos en [esta sección](../../start/using/marketing-activity-templates.md).

## Introducción a las plantillas de envíos {#gs-templates}

Una [plantilla de envíos](../../start/using/marketing-activity-templates.md#creating-a-new-template) le permite definir una vez un conjunto de propiedades técnicas y funcionales que se adaptan a sus necesidades y pueden reutilizarse en futuros envíos. A continuación, puede ahorrar tiempo y estandarizar envíos cuando sea necesario.

Cuando se gestionan varias marcas en Adobe Campaign, Adobe recomienda tener un subdominio por marca. Por ejemplo, un banco puede tener varios subdominios correspondientes a cada una de sus agencias regionales. Si un banco posee el dominio bluebank.com, sus subdominios pueden ser @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Tener una plantilla de envíos para cada subdominio le permite utilizar los parámetros preconfigurados adecuados para cada una de sus marcas, lo que evita errores y le ahorra tiempo.

**Sugerencia**:  Para evitar errores de configuración en la Campaña, le recomendamos que duplicado una plantilla nativa y modifique sus propiedades en lugar de crear una nueva plantilla.

## Configuración de direcciones

* La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico.

* Algunos ISP (proveedores de servicios de Internet) comprueban la validez de la dirección del remitente antes de aceptar mensajes.

* Una dirección mal formada puede resultar en que el servidor receptor la rechace. Debe asegurarse de que se proporciona una dirección correcta.

* La dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado en él.

* Adobe recomienda crear cuentas de correo electrónico que se correspondan con las direcciones especificadas para envíos y respuestas. Consulte con el administrador del sistema de mensajería.

En la **[!UICONTROL Advanced parameters]** sección de las propiedades de una plantilla de correo electrónico, el **[!UICONTROL From (email address)]** campo corresponde a la dirección del remitente.

![](assets/template-parameters.png)

El dominio de dirección debe ser el mismo que el subdominio configurado.

Los **[!UICONTROL Reply to]** campos corresponden a la dirección de correo electrónico y el nombre utilizados para las respuestas.

**Sugerencia** : Adobe recomienda utilizar una dirección real existente como el servicio de atención al cliente de su marca. En este caso, si un destinatario envía una respuesta, el servicio de atención al cliente podrá atenderla.

Para cambiar el nombre del remitente que aparecerá en el encabezado de los mensajes enviados, vaya a la **[!UICONTROL Properties]** ficha de la página de inicio del Diseñador de correo electrónico (a la que se puede acceder a través del icono de inicio) y haga clic en el **[!UICONTROL Default sender name]** bloque.

![](assets/template-content.png)

Para aumentar la tasa de apertura de los envíos, Adobe recomienda utilizar un nombre que sea fácilmente identificable por los destinatarios, como el nombre de su marca.

**Sugerencia** : Para mejorar aún más la experiencia del destinatario, puede agregar el nombre de una persona, por ejemplo &quot;Emma de Megastore&quot;.

Para obtener más información sobre la personalización del nombre del remitente, consulte [Envío del remitente](../../designing/using/subject-line.md#email-sender)por correo electrónico.

## Personalización del nombre del remitente SMS

En la sección Parámetros **** avanzados de las propiedades de una plantilla SMS, la opción **Desde** permite personalizar el nombre del remitente del mensaje SMS mediante una cadena de caracteres. Este es el nombre que aparecerá como el nombre del remitente del mensaje SMS en el teléfono móvil del destinatario.

Si este campo está vacío, será el número de origen proporcionado en la cuenta externa que se utilizará. Si no se proporciona ningún número de origen, será el código corto que se utilizará. Para obtener más información al respecto, consulte [Configuración de SMS](../../administration/using/configuring-sms-channel.md).

**Sugerencia** : Compruebe la legislación de su país sobre la modificación de la dirección del remitente. También debe consultar a su proveedor de servicio de SMS para ver si ofrece esta funcionalidad.

## Configuración de un grupo de control

Una vez entregado el envío, puede comparar el comportamiento de los destinatarios excluidos con el de los destinatarios que sí recibieron el envío. Puede medir la eficacia de sus campañas. Obtenga más información sobre los grupos de control [en esta sección](../../sending/using/control-group.md).

## Uso de tipologías para aplicar filtros o reglas de control

Una tipología contiene reglas de comprobación que se aplican durante la fase de análisis antes de enviar un mensaje.

In the **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** section of the template&#39;s properties, change the default typology according to your needs.

Por ejemplo, para controlar mejor el tráfico saliente, puede definir qué direcciones IP se pueden utilizar definiendo una afinidad por subdominio y creando una tipología por afinidad. Las afinidades se definen en el archivo de configuración de la instancia. Póngase en contacto con el administrador de Adobe Campaign.

Para obtener más información sobre tipologías, consulte [esta sección](../../sending/using/managing-typologies.md).

## Vinculación de una marca a una plantilla

Los parámetros de los correos electrónicos enviados relacionados con la identidad de una marca (como el logotipo de la marca o la dirección del remitente) se administran de forma centralizada en Adobe Campaign. Puede crear una o varias marcas y vincularlas a Plantillas de envíos.

Para obtener más información sobre el uso y la configuración de marcas en Adobe Campaign, consulte Marcas.

Para mostrar o cambiar la marca asignada a una Plantilla de envíos, seleccione el botón Editar propiedades de la plantilla y desplácese hasta los detalles de la marca.

![](assets/template-brand.png)

Para obtener más información sobre cómo vincular una marca a una plantilla, consulte [Asignación de una marca a un correo electrónico](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Aprenda a crear y configurar una marca [en esta sección](../../administration/using/branding.md#creating-a-brand).
