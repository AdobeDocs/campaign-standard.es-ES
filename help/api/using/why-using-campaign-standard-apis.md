---
title: ¿Por qué utilizar las API de Campaign Standard?
description: Obtenga más información sobre las API de Campaign Standard y por qué utilizarlas.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 47b5cf6aee969c7a199ec934b5be6bf80bee590e

---


# Por qué utilizar las API de Campaign Standard {#why-using-campaign-standard-apis}

Adobe Campaign Standard ofrece API que permiten que los sistemas existentes se integren con la plataforma ACS para resolver problemas reales en tiempo real.

Los sitios web públicos, como la página de suscripción o de exclusión, deben conectarse a los sistemas back-end para almacenar información de perfil. Los sistemas back-end como Adobe Campaign tienen la flexibilidad y la capacidad de ingestar datos de perfil en y realizar operaciones personalizadas en ellos.

Estos son algunos ejemplos:

* Posibles inscripciones en línea.
* Gestión de preferencias de comunicación de marketing y perfil del cliente existente.
* Activación de comunicaciones transaccionales basadas en eventos: confirmación de pedidos, itinerario de reservación, restablecimiento de contraseña, etc.
* Incluso la comunicación por correo electrónico del abandono del carro de compras.

Las páginas de aterrizaje de registro permiten a los clientes o posibles clientes registrar su nombre y dirección de correo electrónico. Una vez que Campaign Standard captura la información de perfil y las preferencias, puede enviar mensajes personalizados en función de los intereses de la persona.

Están construidas con los elementos siguientes:

1. Formulario de registro con oyentes de API de campaña.

   ![texto alt](assets/apis_uc1.png)

1. Acciones personalizadas que se deben realizar en función de las casillas de verificación. Un cliente que selecciona "Ofertas especiales por correo electrónico" recibirá un correo personalizado diferente con un cupón de regalo en comparación con el proceso normal de registro.

   ![texto alt](assets/apis_uc2.png)

1. Un perfil puede cambiar sus detalles después de hacer clic en el vínculo "Actualizar detalles" del correo electrónico. Esto lleva el perfil a la página "Actualizar su perfil y detalles de preferencias". Para realizar la operación, los detalles del perfil (Pkey) se pasan al servidor de Campaign y el perfil se recupera y se representa. Una vez que el perfil hace clic en el botón "Actualizar", la información se actualiza en el sistema (mediante un comando PATCH).

   ![texto alt](assets/apis_uc3.png)

Hay disponible una colección de solicitudes para familiarizarse con las solicitudes de API de Campaign Standard. Esta colección en formato JSON proporciona solicitudes de API prediseñadas que representan casos de uso comunes.

Los pasos a continuación describen un caso de uso paso a paso para importar y utilizar la colección para crear un perfil en la base de datos de Campaign Standard.

>[!NOTE]
>
>Nuestro ejemplo usa Postman. Sin embargo, no dude en usar su cliente REST favorito.

1. Descargue la colección JSON haciendo clic [aquí](https://helpx.adobe.com/content/dam/help/en/campaign/kb/working-with-acs-api/_jcr_content/main-pars/download_section/download-1/KB_postman_collection.json.zip).

1. Abra Postman y seleccione el menú **Archivo** / **Importar** .

1. Arrastre y suelte el archivo descargado en la ventana. Se muestran las solicitudes de API prediseñadas, listas para utilizarse.

   ![texto alt](assets/postman_collection.png)

1. Seleccione la opción **Crear una solicitud de perfil** y, a continuación, actualice la solicitud POST y la ficha **Encabezados** con su propia información (&lt;ORGANIZACIÓN&gt;, &lt;API_KEY&gt;, &lt;ACCESS_TOKEN&gt;). Para obtener más información, consulte [esta sección](../../api/using/setting-up-api-access.md).

   ![texto alt](assets/postman_uc1.png)

1. Rellene la ficha **Cuerpo** con la información que desee agregar al nuevo perfil y, a continuación, haga clic en el botón **Enviar** para ejecutar la solicitud.

   ![texto alt](assets/postman_uc2.png)

1. Una vez creado el objeto, se asocia una clave principal (PKey). Es visible en la respuesta de la solicitud, así como en otros atributos.

   ![texto alt](assets/postman_uc3.png)

1. Abra la instancia de Campaign Standard y, a continuación, compruebe que se ha creado el perfil con toda la información de la carga útil.

   ![texto alt](assets/postman_uc4.png)
