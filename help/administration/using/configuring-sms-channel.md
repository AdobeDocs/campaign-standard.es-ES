---
title: Configuración del canal SMS
seo-title: Configuración del canal SMS
description: Configuración del canal SMS
seo-description: '" Consulte los pasos de configuración SMS: enrutamiento, codificación, formatos y propiedades avanzadas. "'
page-status-flag: no activado nunca
uuid: 5 f 13 dbd 5-9522-4199-8 d 9 a -44 c 397 cb 2458
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: configurar canales
discoiquuid: 356 d 4 d 4 f -3 d 5 a -468 c-bff 8-96767 cd 8 fff 6
context-tags: Extaccountmobile, overview; Extaccount, main; entrega, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 866567d63dd2798eb56d42d4e163e5484c9b4d68

---


# Configuring SMS channel{#configuring-sms-channel}

To send SMS messages, one or several external accounts must be configured by an administrator under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL SMS]** &gt; **[!UICONTROL SMS accounts]** menu.

The steps for creating and modifying an external account are detailed in the [External accounts](../../administration/using/external-accounts.md) section. Encontrará los parámetros específicos de cuentas externas para enviar mensajes SMS.

## Defining an SMS Routing {#defining-an-sms-routing}

The external account **[!UICONTROL SMS routing via SMPP]** is provided by default, but it can be useful to add other accounts.

Si desea utilizar el protocolo SMPP, también puede crear una nueva cuenta externa. For more information on SMS protocol and settings, refer to this [technical note](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html).

1. Create a new external account from **[!UICONTROL Administration > Application settings > External accounts]**.
1. Define the account type as **[!UICONTROL Routing]**, the channel as **[!UICONTROL Mobile (SMS)]** and the delivery mode as **[!UICONTROL Bulk delivery]**.

   Once these routing parameters have been defined, the SMS connector ( **[!UICONTROL Generic SMPP]** ) is selected automatically. Este conector permite que Adobe Campaign envíe mensajes SMS directamente a los perfiles de destino mediante la conexión a un centro de servicio de mensajes corto (SMS-C) a través del protocolo SMPP.

   ![](assets/sms_routing.png)

1. Defina los parámetros de conexión.

   Para introducir los parámetros de conexión específicos para enviar mensajes SMS, comuníquese con el proveedor de servicios SMS que le explicará cómo completar los distintos campos de cuenta externa.

   ![](assets/sms_connection.png)

   The **[!UICONTROL Enable TLS over SMPP]** option allows you to encrypt SMPP traffic.

   **[!UICONTROL Enable verbose SMPP traces in the log file]** permite desplazar todo el tráfico SMPP en archivos de registro. Esta opción debe habilitarse para solucionar problemas del conector y compararla con el tráfico que vio el proveedor.

1. Contact Adobe who will give you the value to enter into the **[!UICONTROL SMS-C implementation name]** field, depending on the provider chosen.
1. Defina la configuración de canal SMPP. You can learn more in the [SMS encoding and formats](../../administration/using/configuring-sms-channel.md#sms-encoding-and-formats) section.

   Enable the **[!UICONTROL Store incoming MO in the database]** if you want all incoming SMS to be stored in the inSMS table. For more information on how to retrieve your incoming SMS, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

   The **[!UICONTROL Enable Real-time KPI updates during SR processing]** option allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. These KPIs can be found in the **[!UICONTROL Deployment]** window and are directly recalculated from the SR (Status Report) received from the provider.

   ![](assets/sms_connection_1.png)

1. Define the **[!UICONTROL Throughput and timeouts]** parameters.

   Puede especificar el rendimiento máximo de los mensajes salientes ("MT", Terminated Terminated) en MT por segundo. Si introduce "0" en el campo correspondiente, el rendimiento será ilimitado.

   Los valores de todos los campos correspondientes a las duraciones deben completarse en segundos.

1. Defina los parámetros específicos SMS-C en caso de que necesite definir una asignación de codificación específica. For more information, refer to the [SMSC specifics](../../administration/using/configuring-sms-channel.md#smsc-specifics) section.

   Enable the **[!UICONTROL Send full phone number (send characters other than digits)]** option if you don't want to respect the SMPP protocol and transfer the **[!UICONTROL +]** prefix to the server of the SMS provider (SMS-C).

   However, given that certain providers require the use of the **[!UICONTROL +]** prefix, it is advised that you check with your provider and they will suggest that you enable this option if necessary.

1. Si es necesario, defina las respuestas automáticas para desencadenar acciones basadas en el contenido de una respuesta. For more on this, refer to [this section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).
1. Guarde la configuración de la cuenta externa de enrutamiento SMS.

Ahora puede utilizar su nuevo enrutamiento para enviar mensajes SMS con Adobe Campaign.

## SMS encoding and formats {#sms-encoding-and-formats}

### SMS encoding, length and transliteration {#sms-encoding--length-and-transliteration}

De forma predeterminada, el número de caracteres de un SMS cumple los estándares GSM (Global System for Mobile Communications).

Los mensajes SMS con codificación GSM se limitan a 160 caracteres o a 153 caracteres por SMS para mensajes enviados en varias partes.

>[!NOTE]
>
>Ciertos caracteres se cuentan como dos (llaves, corchetes, símbolo del euro, etc.). The list of available GSM characters is presented in the [Table of characters - GSM Standard](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard) section.

Si lo desea, puede autorizar la transliteración de caracteres marcando el cuadro correspondiente.

![](assets/sms_transliteration.png)

La transliteración consiste en sustituir un carácter de SMS por otro cuando el estándar GSM no tiene en cuenta ese carácter.

* If transliteration is **authorized**, each character that is not taken into account is replaced by a GSM character when the message is sent. Por ejemplo, la letra "ë" se sustituye por "e". Por lo tanto, el mensaje se modifica ligeramente, pero el límite de caracteres seguirá siendo el mismo.
* When transliteration is **not authorized**, each message that contains characters that are not taken into account is sent in binary format (Unicode): all of the characters are therefore sent as they are. Sin embargo, los mensajes SMS que utilizan Unicode están limitados a 70 caracteres (o 67 caracteres por SMS para mensajes enviados en varias partes). Si se supera el número máximo de caracteres, se enviarán varios mensajes, lo que puede crear costes adicionales.

>[!CAUTION]
>
>Al insertar campos de personalización en el contenido del mensaje SMS, se pueden introducir caracteres que la codificación GSM no tenga en cuenta. A content example is offered in the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

De forma predeterminada, la transliteración de caracteres está deshabilitada. Si desea que todos los caracteres de los mensajes SMS se mantengan tal y como están, para no alterar los nombres propios, recomendamos que no active esta opción.

Sin embargo, si los mensajes SMS contienen muchos caracteres que generan mensajes Unicode, puede elegir habilitar esta opción para limitar los costes de envío de mensajes.

### Table of characters - GSM Standard {#table-of-characters---gsm-standard}

Esta sección presenta los caracteres tomados en cuenta por el estándar GSM. Todos los caracteres insertados en el cuerpo del mensaje, aparte de los que se mencionan a continuación, convierten el mensaje completo en formato binario (Unicode) y, por lo tanto, lo limitan a 70 caracteres. For more on this, refer to the [SMS encoding, length and transliteration](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) section.

**Caracteres básicos**

<table> 
 <tbody> 
  <tr> 
   <td> @<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> SP<br /> </td> 
   <td> 0<br /> </td> 
   <td> ¡<br /> </td> 
   <td> P<br /> </td> 
   <td> ¿<br /> </td> 
   <td> P<br /> </td> 
  </tr> 
  <tr> 
   <td> £<br /> </td> 
   <td> _<br /> </td> 
   <td> !<br /> </td> 
   <td> 1<br /> </td> 
   <td> A<br /> </td> 
   <td> Q<br /> </td> 
   <td> a<br /> </td> 
   <td> q<br /> </td> 
  </tr> 
  <tr> 
   <td> $<br /> </td> 
   <td> <img height="21px" src="assets/phi.png" /> <br /> </td> 
   <td> "<br /> </td> 
   <td> 2<br /> </td> 
   <td> B<br /> </td> 
   <td> R<br /> </td> 
   <td> b<br /> </td> 
   <td> r<br /> </td> 
  </tr> 
  <tr> 
   <td> ¥<br /> </td> 
   <td> <img height="21px" src="assets/gamma.png" /> <br /> </td> 
   <td> #<br /> </td> 
   <td> 3<br /> </td> 
   <td> C<br /> </td> 
   <td> S<br /> </td> 
   <td> c<br /> </td> 
   <td> s<br /> </td> 
  </tr> 
  <tr> 
   <td> è<br /> </td> 
   <td> <img height="21px" src="assets/delta.png" /> <br /> </td> 
   <td> ¤<br /> </td> 
   <td> 4<br /> </td> 
   <td> D<br /> </td> 
   <td> T<br /> </td> 
   <td> d<br /> </td> 
   <td> t<br /> </td> 
  </tr> 
  <tr> 
   <td> é<br /> </td> 
   <td> <img height="21px" src="assets/omega.png" /> <br /> </td> 
   <td> %<br /> </td> 
   <td> 5<br /> </td> 
   <td> E<br /> </td> 
   <td> U<br /> </td> 
   <td> e<br /> </td> 
   <td> u<br /> </td> 
  </tr> 
  <tr> 
   <td> ù<br /> </td> 
   <td> <img height="21px" src="assets/pi.png" /> <br /> </td> 
   <td> &amp;<br /> </td> 
   <td> 6<br /> </td> 
   <td> F<br /> </td> 
   <td> V<br /> </td> 
   <td> f<br /> </td> 
   <td> v<br /> </td> 
  </tr> 
  <tr> 
   <td> ì<br /> </td> 
   <td> <img height="21px" src="assets/psi.png" /> <br /> </td> 
   <td> '<br /> </td> 
   <td> 7<br /> </td> 
   <td> G<br /> </td> 
   <td> W<br /> </td> 
   <td> g<br /> </td> 
   <td> w<br /> </td> 
  </tr> 
  <tr> 
   <td> ò<br /> </td> 
   <td> <img height="21px" src="assets/sigma.png" /> <br /> </td> 
   <td> (<br /> </td> 
   <td> 8<br /> </td> 
   <td> H<br /> </td> 
   <td> X<br /> </td> 
   <td> h<br /> </td> 
   <td> x<br /> </td> 
  </tr> 
  <tr> 
   <td> Ç<br /> </td> 
   <td> <img height="21px" src="assets/theta.png" /> <br /> </td> 
   <td> )<br /> </td> 
   <td> 9 </td> 
   <td> I<br /> </td> 
   <td> Y<br /> </td> 
   <td> i<br /> </td> 
   <td> y<br /> </td> 
  </tr> 
  <tr> 
   <td> LF<br /> </td> 
   <td> <img height="21px" src="assets/xi.png" /> <br /> </td> 
   <td> *<br /> </td> 
   <td> :<br /> </td> 
   <td> J<br /> </td> 
   <td> Z<br /> </td> 
   <td> j<br /> </td> 
   <td> z<br /> </td> 
  </tr> 
  <tr> 
   <td> Ø<br /> </td> 
   <td> ESC<br /> </td> 
   <td> +<br /> </td> 
   <td> ;<br /> </td> 
   <td> K<br /> </td> 
   <td> Ä<br /> </td> 
   <td> k<br /> </td> 
   <td> ä<br /> </td> 
  </tr> 
  <tr> 
   <td> ø<br /> </td> 
   <td> Æ<br /> </td> 
   <td> ,<br /> </td> 
   <td> &lt;<br /> </td> 
   <td> L<br /> </td> 
   <td> Ö<br /> </td> 
   <td> l<br /> </td> 
   <td> ö<br /> </td> 
  </tr> 
  <tr> 
   <td> CR<br /> </td> 
   <td> æ<br /> </td> 
   <td> -<br /> </td> 
   <td> = </td> 
   <td> M<br /> </td> 
   <td> Ñ<br /> </td> 
   <td> m<br /> </td> 
   <td> ñ<br /> </td> 
  </tr> 
  <tr> 
   <td> Å<br /> </td> 
   <td> ß<br /> </td> 
   <td> .<br /> </td> 
   <td> &gt;<br /> </td> 
   <td> N<br /> </td> 
   <td> Ü<br /> </td> 
   <td> n<br /> </td> 
   <td> ü<br /> </td> 
  </tr> 
  <tr> 
   <td> å<br /> </td> 
   <td> É<br /> </td> 
   <td> /<br /> </td> 
   <td> ?<br /> </td> 
   <td> O<br /> </td> 
   <td> §<br /> </td> 
   <td> o<br /> </td> 
   <td> à<br /> </td> 
  </tr> 
 </tbody> 
</table>

SP: Espacio

ESC: Escape

LF: Salto de línea

CR: Retorno de carro

**Caracteres avanzados (contabilizados dos veces)**

^ { } [ ~ ] | €

### SMSC specifics {#smsc-specifics}

>[!NOTE]
>
>Estas opciones permiten adaptar el conector para trabajar con SMSC no estándar (es decir, no seguir exactamente la especificación SMPP 3.4) o requisitos de codificación específicos, y únicamente deben configurarlos los usuarios avanzados.

Al enviar un mensaje SMS, Adobe Campaign puede utilizar una o varias codificaciones de texto. Cada codificación tiene su propio conjunto de caracteres específico y determina el número de caracteres que se ajustan a un mensaje SMS.

The **[!UICONTROL DATA_CODING]** field allows Adobe Campaign to communicate to the SMS-C which encoding is used.

>[!NOTE]
>
>The mapping between the **data_coding** value and the encoding actually used is standardized. Nevertheless, certain SMS-C have their own specific mapping: in this case, your **Adobe Campaign** administrator needs to declare this mapping. Consulte a su proveedor para obtener más información.

The **[!UICONTROL Define a specific mapping of encodings]** functionality allows you to declare **data_codings** and to force the encoding if necessary: to do this, specify a single encoding in the table.

**Configuración**

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is not checked, the connector takes on a generic behavior:

   * It will try to use GSM encoding to which it assigns the value **data_coding = 0**.
   * If GSM encoding fails, it will use **UCS2** encoding to which it assigns the value **data_coding = 8**.
   ![](assets/sms_data_coding.png)

* When the **[!UICONTROL Define a specific mapping of encodings]** functionality is checked, you can define the encodings that you would like to use as well as the linked **[!UICONTROL data_coding]** field values. Adobe Campaign intentará utilizar la primera codificación de la lista, luego lo siguiente, si la primera codificación resulta imposible.

   The order of declaration is important: it is recommended that you put the list in ascending order **of cost** in order to favor the encodings allowing you to fit as many characters as possible in each SMS message.

   Declare únicamente las codificaciones que desee utilizar. Si algunas de las codificaciones proporcionadas por SMS-C no deben coincidir con su finalidad de uso, no las declare en la lista.

   ![](assets/sms_data_coding1.png)

### Automatic reply sent to the MO {#automatic-reply-sent-to-the-mo}

Cuando un perfil responde a un mensaje SMS que se envió mediante Campaign, puede configurar los mensajes que se devuelven automáticamente a él, así como la acción que se realizará.

For more information, refer to [this section](../../channels/using/managing-incoming-sms.md).

## Configuring SMS properties {#configuring-sms-properties}

Esta sección detalla la lista de parámetros exclusivos de SMS en la pantalla de propiedades de una entrega SMS o una plantilla SMS.

The specific parameters for sending SMS messages are regrouped in the **[!UICONTROL Send]** and in the **[!UICONTROL Advanced parameters]** sections.

![](assets/sms_options.png)

* The **[!UICONTROL From]** option allows you to personalize the name of the SMS message sender using a string of characters. Este es el nombre que aparecerá como nombre remitente del mensaje SMS en el teléfono móvil del destinatario.

   Si este campo está vacío, será el número de fuente proporcionado en la cuenta externa que se utilizará. Si no se proporciona ningún número de fuente, será el código corto que se utilizará. The external account specific to SMS delivery is presented in the [External SMS account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.

   ![](assets/sms_smpp.png)

   >[!CAUTION]
   >
   >Verifique la legislación de su país con respecto a la modificación de la dirección del remitente. También debe consultar a su proveedor de servicios SMS si ofrece esta funcionalidad.

* The **[!UICONTROL Maximum number of SMS per message]** option allows you to define the number of SMS messages to use to send a message. Si se supera este número, no se enviará el mensaje.

   >[!CAUTION]
   >
   >Si ha insertado campos de personalización o texto condicional en el contenido del mensaje SMS, la longitud del mensaje y, como resultado, la cantidad de mensajes SMS que se enviarán, pueden variar de un destinatario a otro. For more on this, refer to the [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md) section.

* **[!UICONTROL Transmission mode]** El campo permite determinar el método de entrega para mensajes SMS:

   * **[!UICONTROL Saved on SIM card]**: el mensaje se almacena en la tarjeta SIM del destinatario.
   * **[!UICONTROL Saved on mobile]**: el mensaje se almacena en la memoria interna del teléfono.
   * **[!UICONTROL Flash]**: El mensaje se muestra en el teléfono móvil del destinatario como notificación y luego desaparece sin que se guarde.

