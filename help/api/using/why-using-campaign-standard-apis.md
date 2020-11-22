---
solution: Campaign Standard
product: campaign
title: Razones para utilizar las API de Campaign Standard?
description: Obtenga más información sobre las API de Campaign Standard y por qué utilizarlas.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '491'
ht-degree: 3%

---


# Razones para utilizar las API de Campaign Standard {#why-using-campaign-standard-apis}

Adobe Campaign Standard proporciona API que permiten que los sistemas existentes se integren con la plataforma ACS para resolver problemas reales en tiempo real.

Los sitios web públicos, como la página de suscripción o de exclusión, deben conectarse a los sistemas back-end para almacenar información de perfil. Los sistemas back-end como Adobe Campaign tienen la flexibilidad y la capacidad de ingerir datos de perfil en y realizar operaciones personalizadas en él.

Estos son algunos ejemplos:

* Registro en línea de clientes potenciales.
* Administración de preferencias de comunicación de marketing y perfil de clientes existente.
* Activación de comunicación transaccional basada en eventos: confirmación de pedido, itinerario de reservación, restablecimiento de contraseña, etc.
* Incluso la comunicación por correo electrónico del abandono del carro de compras.

Las páginas de aterrizaje de registro permiten a los clientes o clientes potenciales registrar su nombre y dirección de correo electrónico. Una vez que el Campaign Standard captura la información y las preferencias del perfil, puede enviar mensajes personalizados en función de los intereses de la persona.

Están construidas con los elementos siguientes:

1. Formulario de registro con oyentes de API de campaña.

   ![texto alt](assets/apis_uc1.png)

1. Acciones personalizadas que se deben realizar en función de las casillas de verificación. Un cliente que selecciona &quot;Ofertas especiales de correo electrónico&quot; recibirá un correo personalizado diferente con un cupón de regalo en comparación con el proceso normal de registro.

   ![texto alt](assets/apis_uc2.png)

1. Un perfil puede cambiar sus detalles después de hacer clic en el vínculo &quot;Actualizar detalles&quot; del correo electrónico. Esto lleva al perfil a la página &quot;Actualizar los detalles de Perfil y preferencia&quot;. Para realizar la operación, los detalles del perfil (Pkey) se pasan al servidor de Campaña y el perfil se recupera y se representa. Una vez que el perfil hace clic en el botón &quot;Actualizar&quot;, la información se actualiza en el sistema (mediante un comando del PATCH).

   ![texto alt](assets/apis_uc3.png)

Existe una colección de solicitudes para ayudarle a familiarizarse con las solicitudes de API de Campaign Standard. Esta colección en formato JSON proporciona solicitudes de API prediseñadas que representan casos de uso comunes.

Los pasos a continuación describen un caso de uso paso a paso para importar y utilizar la colección para crear un perfil en la base de datos de Campaign Standard.

>[!NOTE]
>
>Nuestro ejemplo usa Postman. Sin embargo, no dude en usar su cliente REST favorito.

1. Descargue la colección JSON haciendo clic [aquí](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Abra Postman y seleccione el menú **Archivo** / **Importar** .

1. Arrastre y suelte el archivo descargado en la ventana. Se muestran las solicitudes de API prediseñadas, listas para utilizarse.

   ![texto alt](assets/postman_collection.png)

1. Seleccione la **Creación de una solicitud de perfil** y, a continuación, actualice la solicitud de POST y la ficha **Encabezados** con su propia información (&lt;ORGANIZACIÓN>, &lt;API_KEY>, &lt;ACCESS_TOKEN>). Para obtener más información, consulte [esta sección](../../api/using/setting-up-api-access.md).

   ![texto alt](assets/postman_uc1.png)

1. Rellene la ficha **Cuerpo** con la información que desee agregar al nuevo perfil y, a continuación, haga clic en el botón **Enviar** para ejecutar la solicitud.

   ![texto alt](assets/postman_uc2.png)

1. Una vez creado el objeto, se asocia una clave principal (PKey). Es visible en la respuesta de la solicitud, así como en otros atributos.

   ![texto alt](assets/postman_uc3.png)

1. Abra la instancia de Campaign Standard y, a continuación, compruebe que se ha creado el perfil, con toda la información de la carga útil.

   ![texto alt](assets/postman_uc4.png)
