---
title: Cuentas externas
description: Configure cuentas externas para configurar conexiones con sistemas externos como servidores SFTP.
page-status-flag: never-activated
uuid: 5d2e2e3d-5d1f-4466-97e5-842c50390146
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: d5c6a3d4-f767-46c1-a8c0-3b9dc52dcea8
internal: n
snippet: y
context-tags: extAccount,main;extAccount,overview
translation-type: tm+mt
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Cuentas externas{#external-accounts}

Una cuenta externa es una configuración que permite
            configurar y probar el acceso a un servidor que sea externo a Adobe Campaign.

Estas 
            cuentas externas se pueden utilizar en flujos de trabajo de Campaign para acceder y administrar datos.

Puede configurar los siguientes tipos de cuentas
            externas:

* SFTP. Para obtener más información, consulte [esta sección](#sftp-external-account).
* Amazon Storage Service (S3). Para obtener más información, consulte [esta sección](#amazon-s3-external-account).
* Adobe Experience Manager. Para obtener más información, consulte [esta sección](#adobe-experience-manager-external-account).
* Adobe Analytics. Para obtener más información, consulte [esta sección](../../integrating/using/configure-campaign-analytics-integration.md).
* Google reCAPTCHA. Para obtener más información, consulte [esta sección](#google-recaptcha-external-account).

>[!NOTE]
>
>Adobe utiliza otros tipos de cuentas externas durante el proceso de aprovisionamiento del producto. A partir de la versión 17.9 de Campaign Standard, las cuentas externas de FTP se pueden definir pero ya no se pueden utilizar en las nuevas actividades de flujo de trabajo. Si ya tiene una conexión configurada, aún está habilitada.

Los administradores pueden configurar las cuentas externas en el **[!UICONTROL Administration > Application settings > External accounts]** menú.

## Creación de una cuenta externa {#creating-an-external-account}

Adobe Campaign viene con un conjunto de cuentas externas 
                   predefinidas. Para configurar conexiones con sistemas externos como servidores FTP 
                 utilizados para transferencias de archivos, puede crear cuentas externas propias.

Los procesos técnicos utilizan las cuentas externas 
                 como flujos de trabajo técnicos o flujos de trabajo de campaña. Al configurar una transferencia de archivos 
                 en un flujo de trabajo o un intercambio de datos con cualquier otra aplicación (Adobe Target, Experience
                 Manager, etc.), debe seleccionar una cuenta externa.

1. Haga clic en el botón **.[!UICONTROL Create]**
1. Introduzca una etiqueta. La etiqueta y el ID se utilizarán al seleccionar cuentas externas en flujos de trabajo.
1. Seleccione el tipo de cuenta que desee crear.
1. Configure el acceso a la cuenta especificando las credenciales, la dirección del servidor, el número de puerto y o las claves cuando corresponda.

   La información necesaria suele ser proporcionada por 
                       el proveedor del servidor al que está conectándose.

1. Guarde su cuenta.

La cuenta externa se crea y se agrega a la lista de cuentas. Ahora está disponible para las transferencias de datos y archivos o las configuraciones
                de enrutamiento en las actividades de flujo de trabajo y propiedades de entrega.

## Cuenta externa SFTP {#sftp-external-account}

Los distintos tipos de cuentas externas requieren que se especifique información diferente.

Para una cuenta externa de SFTP, proporcione los siguientes detalles:

* Dirección del servidor. Por ejemplo, **ftp.domain.com**.
* Número de puerto. For example, **22**.
* Credenciales del servidor SFTP: nombre de cuenta y contraseña utilizados para conectarse al servidor.

### Recomendaciones de servidor SFTP alojado por Adobe {#adobe-hosted-sftp-server-recommendations}

Al administrar archivos y datos para fines de ETL, estos archivos se almacenan en un servidor SFTP alojado proporcionado por Adobe. Este SFTP está diseñado para ser un espacio de almacenamiento temporal en el que se puede controlar la retención y eliminación de archivos.

Cuando no se utiliza o monitorea correctamente, este espacio puede llenar rápidamente el espacio físico disponible en el servidor y causar problemas graves. Puede provocar la pérdida o corrupción de datos en la plataforma.

Para evitar estos problemas, Adobe recomienda seguir las prácticas recomendadas a continuación:

* Mantenga los datos mínimos posibles.
* Utilice la autenticación basada en claves para evitar la caducidad de la contraseña. Los formatos admitidos son **OpenSSH** y **SSH2** únicamente. Deberá proporcionar la clave pública al equipo de asistencia de Adobe para que se cargue en el servidor de campañas.
* Mantenga los datos sólo durante el tiempo que sea necesario. 15 días es el límite máximo de tiempo.
* Utilice flujos de trabajo para eliminar correctamente los datos (administrar la retención de flujos de trabajo que consuman datos).
* Utilice lotes en sus cargas por SFTP y sus flujos de trabajo.
* Gestionar errores/excepciones.
* Inicie sesión ocasionalmente en el SFTP para comprobar directamente lo que sucede allí.
* Recuerde que la gestión de discos SFTP es responsabilidad principalmente suya.

Además, tenga en cuenta que las IP públicas desde las que intenta iniciar la conexión SFTP deben incluirse en la lista de direcciones permitidas en la instancia de Campaign. La lista blanca de direcciones IP se puede solicitar a través de un ticket [de](https://support.neolane.net)soporte, junto con la clave pública que se utilizará para la autenticación.

Los servidores SFTP se pueden administrar desde el Panel de control. For more information, refer to the [Control Panel documentation](https://helpx.adobe.com/campaign/kb/control-panel-sftp.html).

>[!NOTE]
>
>El Panel de control solo está disponible para los usuarios administradores de clientes alojados en AWS.
Compruebe si la instancia está alojada en AWS [aquí](https://helpx.adobe.com/campaign/kb/control-panel-faq.html#IMSOrgID).

## Cuenta externa de Amazon S3 {#amazon-s3-external-account}

El campo del servidor de Amazon S3 debe rellenarse de la siguiente manera:

```
<S3 bucket name>.s3.amazonaws.com/<s3 object path>
```

Para almacenar el archivo en modo codificado S3, marque la **[!UICONTROL Keep files in S3 encrypted]** casilla.

![](assets/external_accounts_2.png)

La información necesaria suele ser proporcionada por 
                       el proveedor del servidor al que está conectándose.

Especifique el **[!UICONTROL AWS Region]** punto final asociado. Puede consultar las regiones compatibles y las versiones de firma en la documentación [oficial de](https://docs.aws.amazon.com/general/latest/gr/rande.html#s3_region)Amazon S3.

>[!NOTE]
>
>Debe **[!UICONTROL Receiver server]** introducirse sin la región de AWS; más adelante se agregará automáticamente a la dirección URL.

### Recomendaciones de cuentas de Amazon S3 {#amazon-s3-account-recommendations}

Para ayudarle a configurar su cuenta de Amazon S3, le recomendamos que siga estas recomendaciones:

* Cree una política de cubos estricta para restringir el acceso a los cubos S3. La directiva de bucket se puede configurar al crear un bucket. For more information, refer to the [Amazon S3 documentation](https://docs.aws.amazon.com/AmazonS3/latest/dev//example-bucket-policies.html).
* Durante la creación de una cuenta externa, active la casilla de verificación para que el cifrado almacene datos confidenciales en el bucket S3. Para ello, active la **[!UICONTROL Keep files in S3 encrypted]** casilla.
* Conceder permisos de bloque para especificar quién puede acceder al objeto en un bloque. Para obtener más información sobre el permiso de bucket, consulte la documentación [de](https://docs.aws.amazon.com/AmazonS3/latest/dev//access-control-overview.html)Amazon S3.

## Cuenta externa de Adobe Experience Manager {#adobe-experience-manager-external-account}

Las cuentas externas de Adobe Experience Manager se utilizan al integrar Campaign con Experience Manager.

El proceso y los requisitos relacionados con esta integración están disponibles en [este documento](../../integrating/using/about-campaign-integrations.md).

Al configurar esta nueva cuenta externa, 
                debe proporcionar los siguientes detalles:

* Servidor: introduzca la dirección URL del servidor de Adobe Experience Manager. Por ejemplo, **http://aem.domain.com:4502**.
* Credenciales de cuenta de AEM: utilice la cuenta que accederá a la instancia de Adobe Experience Manager. Debe formar parte de la cuenta del grupo remoto de campañas en Experience Manager.

## Cuenta externa de Google reCAPTCHA {#google-recaptcha-external-account}

>[!NOTE]
>
>La configuración de Google reCAPTCHA requiere una cuenta de Google.

El mecanismo reCAPTCHA de Google le permite proteger su página de aterrizaje del spam y los abusos causados por los bots. Esto no es intrusivo para los clientes, ya que no requiere ninguna interacción por parte de ellos y se basa en las interacciones con el sitio. Para registrar su sitio, consulte esta [página](https://www.google.com/recaptcha/admin/create). Debe elegir el tipo de reCAPTCHA V3.

Para agregar Google reCAPTCHA V3 a su página de aterrizaje, primero debe configurarla en su cuenta externa. Para obtener más información sobre cómo agregarla a la página de aterrizaje, consulte esta [sección](../../channels/using/configuring-landing-page.md#setting-google-recaptcha).

Para una cuenta externa de Google reCAPTCHA V3, proporcione los siguientes detalles:

* A **[!UICONTROL Label]** y **[!UICONTROL ID]** de su cuenta externa
* **[!UICONTROL Type]**:: Google reCAPTCHA
* Su **[!UICONTROL Site key]** y **[!UICONTROL Site secret]**
* A **[!UICONTROL Threshold]** entre 0 y 1

   El valor 0,0 **[!UICONTROL Threshold]** significa que es probable que sea un bot y 1,0 una buena interacción. De forma predeterminada, puede utilizar un umbral de 0,5.

![](assets/external_accounts_3.png)
