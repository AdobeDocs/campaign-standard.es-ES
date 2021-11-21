---
title: Uso de plantillas de envío
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"Las plantillas de envíos ofrecen una mayor eficiencia al proporcionar escenarios listos para usar para los tipos de actividades más comunes."'
feature: Deliverability
role: User
level: Intermediate
exl-id: ca134a7f-9035-4885-b4cb-1170b6ec10cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 59%

---

# Uso de plantillas {#use-templates}

Las plantillas de envíos ofrecen una mayor eficiencia al proporcionar escenarios listos para usar para los tipos de actividades más comunes. Con las plantillas, los especialistas en marketing pueden implementar nuevas campañas con una personalización mínima en un período de tiempo más corto.

Obtenga más información sobre las plantillas de envíos en [esta sección](../../start/using/marketing-activity-templates.md).

## Introducción a las plantillas de entregas {#gs-templates}

Una [plantilla de envíos](../../start/using/marketing-activity-templates.md#creating-a-new-template) le permite definir una vez un conjunto de propiedades técnicas y funcionales que se adaptan a sus necesidades y pueden reutilizarse en futuros envíos. A continuación, puede ahorrar tiempo y estandarizar envíos cuando sea necesario.

Cuando se gestionan varias marcas en Adobe Campaign, Adobe recomienda tener un subdominio por marca. Por ejemplo, un banco puede tener varios subdominios correspondientes a cada una de sus agencias regionales. Si un banco posee el dominio bluebank.com, sus subdominios pueden ser @ny.bluebank.com, @ma.bluebank.com, @ca.bluebank.com, etc. Tener una plantilla de envíos para cada subdominio le permite utilizar los parámetros preconfigurados adecuados para cada una de sus marcas, lo que evita errores y le ahorra tiempo.

**Sugerencia**: Para evitar errores de configuración en Campaign, se recomienda duplicar una plantilla nativa y modificar sus propiedades en lugar de crear una nueva plantilla.

## Configuración de direcciones

* La dirección del remitente es obligatoria para permitir que se envíe un mensaje de correo electrónico.

* Algunos ISP (proveedores de servicios de Internet) comprueban la validez de la dirección del remitente antes de aceptar mensajes.

* Una dirección mal formada puede resultar en que el servidor receptor la rechace. Debe asegurarse de que se proporciona una dirección correcta.

* La dirección debe identificar explícitamente al remitente. El dominio debe ser propiedad del remitente y estar registrado en él.

* Adobe recomienda crear cuentas de correo electrónico que se correspondan con las direcciones especificadas para envíos y respuestas. Consulte con el administrador del sistema de mensajería.

En el **[!UICONTROL Advanced parameters]** de las propiedades de una plantilla de correo electrónico, la variable **[!UICONTROL From (email address)]** corresponde a la dirección del remitente.

![](assets/template-parameters.png)

El dominio de dirección debe ser el mismo que el subdominio configurado.

La variable **[!UICONTROL Reply to]** los campos corresponden a la dirección de correo electrónico y al nombre utilizado para las respuestas.

**Sugerencia** - Adobe recomienda utilizar una dirección real existente, como el servicio de atención al cliente de su marca. En este caso, si un destinatario envía una respuesta, el servicio de atención al cliente podrá atenderla.

Para cambiar el nombre del remitente que aparece en el encabezado de los mensajes enviados, vaya a **[!UICONTROL Properties]**  en la página de inicio del Diseñador de correo electrónico (accesible a través del icono de inicio) y haga clic en la **[!UICONTROL Default sender name]** bloque.

![](assets/template-content.png)

Para aumentar la tasa de apertura de los envíos, Adobe recomienda utilizar un nombre fácilmente identificable por los destinatarios, como el nombre de la marca.

**Sugerencia** - Para mejorar aún más la experiencia del destinatario, puede añadir el nombre de una persona, por ejemplo &quot;Emma de Megastore&quot;.

Para obtener más información sobre la personalización del nombre del remitente, consulte [Remitente del correo electrónico](../../designing/using/subject-line.md#email-sender).

## Personalización del nombre del remitente del SMS

En el **Parámetros avanzados** de las propiedades de una plantilla SMS, la variable **De** permite personalizar el nombre del remitente del mensaje SMS con una cadena de caracteres. Este es el nombre que aparecerá como el nombre del remitente del mensaje SMS en el teléfono móvil del destinatario.

Si este campo está vacío, será el número de origen proporcionado en la cuenta externa que se utilizará. Si no se proporciona ningún número de origen, será el código corto que se utilizará. Para obtener más información al respecto, consulte [Configuración de SMS](../../administration/using/configuring-sms-channel.md).

**Sugerencia** - Compruebe la legislación de su país con respecto a la modificación de la dirección del remitente. También debe consultar a su proveedor de servicio de SMS para ver si ofrece esta funcionalidad.

## Configuración de un grupo de control

Una vez entregado el envío, puede comparar el comportamiento de los destinatarios excluidos con el de los destinatarios que sí recibieron el envío. Puede medir la eficacia de sus campañas. Obtenga más información sobre los grupos de control [en esta sección](../../sending/using/control-group.md).

## Uso de tipologías para aplicar filtros o reglas de control

Una tipología contiene reglas de comprobación que se aplican durante la fase de análisis antes de enviar un mensaje.

En el **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** de las propiedades de la plantilla, cambie la tipología predeterminada según sus necesidades.

Por ejemplo, para controlar mejor el tráfico saliente, puede definir qué direcciones IP se pueden utilizar definiendo una afinidad por subdominio y creando una tipología por afinidad. Las afinidades se definen en el archivo de configuración de la instancia. Póngase en contacto con el administrador de Adobe Campaign.

Para obtener más información sobre tipologías, consulte [esta sección](../../sending/using/managing-typologies.md).

## Vinculación de una marca a una plantilla

Los parámetros de los correos electrónicos enviados relacionados con la identidad de una marca (como el logotipo de la marca o la dirección del remitente) se administran de forma centralizada en Adobe Campaign. Puede crear una o varias marcas y vincularlas a plantillas de envío.

Para obtener más información sobre el uso y la configuración de marcas en Adobe Campaign, consulte Marcas.

Para mostrar o cambiar la marca asignada a una plantilla de envío, seleccione el botón Editar propiedades de la plantilla y vaya a los detalles de la marca.

![](assets/template-brand.png)

Para obtener más información sobre cómo vincular una marca a una plantilla, consulte [Asignación de una marca a un correo electrónico](../../administration/using/branding.md#assigning-a-brand-to-an-email).

Obtenga información sobre cómo crear y configurar una marca [en esta sección](../../administration/using/branding.md#creating-a-brand).
