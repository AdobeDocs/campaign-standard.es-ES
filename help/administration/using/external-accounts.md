---
title: Cuentas externas
seo-title: Cuentas externas
description: Cuentas externas
seo-description: Configure cuentas externas para configurar conexiones con sistemas externos como servidores SFTP.
page-status-flag: no activado nunca
uuid: 5 d 2 e 2 e 3 d -5 d 1 f -4466-97 e 5-842 c 50390146
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: app-settings
discoiquuid: d 5 c 6 a 3 d 4-f 767-46 c 1-a 8 c 0-3 b 9 dc 52 dcea 8
internal: n
snippet: y
context-tags: Extaccount, main; Extaccount, información general
translation-type: tm+mt
source-git-commit: 0fcedd464ae2074e7eda793bbf20cc53ce04f324

---


# External accounts{#external-accounts}

Una cuenta externa es una configuración que permite configurar y probar el acceso a un servidor externo a Adobe Campaign.

Estas cuentas externas se pueden utilizar en flujos de trabajo de campaña para acceder y administrar datos.

Puede configurar los siguientes tipos de cuentas externas:

* SFTP. For more on this, refer to [this section](../../administration/using/external-accounts.md#sftp-external-account).
* Amazon Storage Service (S 3). For more on this, refer to [this section](../../administration/using/external-accounts.md#amazon-s3-external-account).
* Adobe Experience Manager. For more on this, refer to [this section](../../administration/using/external-accounts.md#adobe-experience-manager-external-account).
* Adobe Analytics. For more on this, refer to [this section](../../integrating/using/configure-campaign-analytics-integration.md).
* Google recaptcha. For more on this, refer to [this section](../../administration/using/external-accounts.md#google-recaptcha-external-account).

>[!NOTE]
>
>Adobe utiliza otros tipos de cuentas externas durante el proceso de aprovisionamiento de productos. Desde la versión 17.9 de Campaign Standard, las cuentas externas FTP pueden definirse pero ya no se pueden utilizar en nuevas actividades de flujo de trabajo. Si ya ha configurado una conexión, aún está habilitada.

External accounts can be configured by administrators under the **[!UICONTROL Administration > Application settings > External accounts]** menu.

## Creating an external account {#creating-an-external-account}

Adobe Campaign incluye un conjunto de cuentas externas predefinidas. Para configurar conexiones con sistemas externos como servidores FTP utilizados para transferencias de archivos, puede crear sus propias cuentas externas.

Los procesos técnicos utilizan cuentas externas como flujos de trabajo técnicos o flujos de trabajo de campañas. Al configurar una transferencia de archivos en un flujo de trabajo o intercambio de datos con cualquier otra aplicación (Adobe Target, Experience Manager, etc.), debe seleccionar una cuenta externa.

1. Click the **[!UICONTROL Create]** button.
1. Introduzca una etiqueta. La etiqueta y el ID se utilizarán al seleccionar cuentas externas en flujos de trabajo.
1. Seleccione el tipo de cuenta que desee crear.
1. Configure el acceso a la cuenta especificando credenciales, dirección del servidor, número de puerto y claves cuando sea relevante.

   La información necesaria normalmente la proporciona el proveedor del servidor al que está conectando.

1. Guarde su cuenta.

La cuenta externa se crea y agrega a la lista de cuentas. Ahora está disponible para sus transferencias de datos/archivos o para enrutar configuraciones en actividades de flujo de trabajo y propiedades de entrega.

## SFTP external account {#sftp-external-account}

Diferentes tipos de cuentas externas requieren que se especifique información diferente.

Para obtener una cuenta externa SFTP, proporcione los siguientes detalles:

* Dirección del servidor. For example, **ftp.domain.com**.
* Número de puerto. For example, **22**.
* Credenciales del servidor SFTP: nombre de cuenta y contraseña utilizados para conectarse al servidor.

### Adobe hosted SFTP server recommendations {#adobe-hosted-sftp-server-recommendations}

Al administrar archivos y datos para ETL, estos archivos se almacenan en un servidor SFTP alojado proporcionado por Adobe. Este SFTP está diseñado para ser un espacio de almacenamiento temporario en el que puede controlar la retención y eliminación de archivos.

Cuando no se utiliza ni se supervisa correctamente, este espacio puede rellenar rápidamente el espacio físico disponible en el servidor y causar graves problemas. Puede provocar pérdida de datos o daños en su plataforma.

Para evitar estos problemas, Adobe recomienda seguir las optimizaciones siguientes:

* Mantenga los datos mínimos posibles.
* Utilice la autenticación basada en claves para evitar la caducidad de la contraseña. Supported formats are **OpenSSH** and **SSH2** only. Tendrá que proporcionar la clave pública al equipo de asistencia de Adobe para que se cargue en el servidor de campaña.
* Conserve los datos solo durante el tiempo necesario. 15 días es el límite de tiempo máximo.
* Utilice flujos de trabajo para eliminar correctamente los datos (administre la retención de los flujos de trabajo que consumen los datos).
* Utilice lotes en cargas SFTP, así como en flujos de trabajo.
* Gestión de errores/excepciones.
* En ocasiones, inicie sesión en SFTP para comprobar directamente lo que está ahí.
* Recuerde que la gestión de discos SFTP es principalmente responsabilidad.

Además, tenga en cuenta que las IP públicas desde las que está intentando iniciar la conexión SFTP deben incluirse en la lista de direcciones permitidas en la instancia de campaña. Whitelisting of IP addresses can be requested via a [support ticket](https://support.neolane.net), along with providing the public key to use for authentication.

Los servidores SFTP se pueden administrar desde el Panel de control. For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>Panel de control solo está disponible para usuarios administradores de clientes alojados en AWS.
Check if your instance is hosted on AWS [here](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Amazon S3 external account {#amazon-s3-external-account}

El campo del servidor Amazon S 3 debe rellenarse de la siguiente manera:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

To store your file in S3 encrypted mode, check the **[!UICONTROL Keep files in S3 encrypted]** box.

![](assets/external_accounts_2.png)

La información necesaria normalmente la proporciona el proveedor del servidor al que está conectando.

Specify the **[!UICONTROL AWS Region]** associated to your endpoint. You can check the supported regions and signature versions in the official [Amazon S3 documentation](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region) .

### Amazon S3 account recommendations {#amazon-s3-account-recommendations}

Para ayudarle a configurar la cuenta de Amazon S 3, le recomendamos que siga estas recomendaciones:

* Cree normas estrictas de bucket para restringir el acceso a los bloques S 3. La política de bucket se puede configurar al crear un bloque. For more information, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* While creating an external account, enable the encryption to store sensitive data in the S3 bucket by checking the **[!UICONTROL Keep files in S3 encrypted]** box.
* Conceda permisos de bloque para especificar quién puede acceder al objeto en un bloque. For more information on bucket permission, refer to the [Amazon S3 documentation](http://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)

## Adobe Experience Manager external account {#adobe-experience-manager-external-account}

Las cuentas externas de Adobe Experience Manager se utilizan al integrar Campaign con Experience Manager.

Process and requirements related to this integration are available in [this document](../../integrating/using/about-campaign-integrations.md).

A medida que configure esta nueva cuenta externa, debe proporcionar los siguientes detalles:

* Servidor: introduzca la URL del servidor de Adobe Experience Manager. For example, **http://aem.domain.com:4502**.
* Credenciales de cuenta de AEM: utilice la cuenta que accederá a la instancia de Adobe Experience Manager. Debe ser una parte de cuenta del grupo remoto de campañas en Experience Manager.

## Google reCAPTCHA external account {#google-recaptcha-external-account}

>[!NOTE]
>
>La configuración de Google recaptcha requiere una cuenta de Google.

El mecanismo de recaptcha de Google permite proteger la página de aterrizaje de correo no deseado y de abuso causado por bots. Esto no resulta intrusivo para sus clientes, ya que no requiere ninguna interacción de ellos y se basa en interacciones con su sitio. To register your site, refer to this [page](https://www.google.com/recaptcha/admin/create). Debe elegir el tipo de recaptcha V 3.

Para agregar Google recaptcha V 3 a la página de aterrizaje, primero debe configurarlo en su cuenta externa. For more information on how to add it to your landing page, refer to this [section](../../channels/using/designing-a-landing-page.md#setting-google-recaptcha).

Para una cuenta externa de Google recaptcha V 3, proporcione los siguientes detalles:

* A **[!UICONTROL Label]** and **[!UICONTROL ID]** of your external account
* **[!UICONTROL Type]**: Google recaptcha
* Your **[!UICONTROL Site key]** and **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** between 0 and 1

   The 0.0 **[!UICONTROL Threshold]** value means that it is likely a bot and 1.0 likely a good interaction. De forma predeterminada, puede utilizar un umbral de 0,5.

![](assets/external_accounts_3.png)

