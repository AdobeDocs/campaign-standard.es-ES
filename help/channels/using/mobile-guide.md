---
title: Guía de Campaign Standard Mobile
description: Obtenga más información sobre las directrices generales para los envíos móviles en Adobe Campaign Standard, como cómo configurar las aplicaciones móviles o crear notificaciones push y mensajes en la aplicación.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
source-git-commit: e583ba4e93b16389be9d06c4b7fa8eebf4ee3cfc
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 23%

---

# Introducción a los canales móviles {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Obtenga información sobre cómo configurar la aplicación móvil para notificaciones push </br><a href="#configuration-push">Haga clic aquí</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Aprenda a configurar su aplicación móvil para mensajes en la aplicación </br><a href="#configuring-mobile-app">Haga clic aquí</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Obtenga más información sobre cómo crear notificaciones push </br><a href="#create-push">Haga clic aquí</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Aprenda a crear mensajes en la aplicación</br><a href="#create-inapp">Haga clic aquí</a></p></td></tr>
</table>

## Acerca de la entrega móvil {#about-mobile}

Adobe Campaign le permite crear y enviar mensajes personalizados en varios canales y medir su eficacia mediante informes dedicados.

Con Adobe Campaign Standard, puede enviar envíos móviles a través de tres canales diferentes:

* SMS, presentado en la sección Acerca de los mensajes SMS .
* Las notificaciones push se presentan en la sección Acerca de las notificaciones push .
* Los mensajes en la aplicación se presentan en la sección Acerca de los mensajes en la aplicación .

## Configurar la aplicación móvil para notificaciones push {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuración de una aplicación móvil mediante los SDK para Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign aprovechando los SDK para Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Explicación de la estructura de carga útil de las notificaciones push del Campaign Standard</strong></p>
    </div>
    <p>Obtenga más información sobre la estructura de la carga útil recibida en las aplicaciones móviles cuando una notificación push se envía correctamente a una aplicación desde Adobe Campaign Standard.</br><a href="../../administration/using/push-payload.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implementación del seguimiento de notificaciones locales</strong></p>
    </div>
    <p>Obtenga información aquí sobre cómo asegurarse de que el seguimiento de notificaciones locales se haya implementado correctamente. </br><a href="../../administration/using/local-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementación del seguimiento push</strong></p>
    </div>
    <p>Obtenga información sobre cómo garantizar que el seguimiento de notificaciones push se haya implementado correctamente en iOS y Android.</br><a href="../../administration/using/push-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Configuración de una aplicación móvil para mensajes en la aplicación {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuración de una aplicación móvil mediante los SDK para Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign aprovechando los SDK para Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Casos de uso móvil admitidos con los SDK para Adobe Experience Platform</strong></p>
    </div>
    <p>Obtenga más información sobre los casos de uso móvil admitidos en Adobe Campaign Standard mediante los SDK para Adobe Experience Platform.</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Configuración de reglas de Adobe Experience Platform Launch para admitir casos de uso de Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Haga clic aquí </strong></a> para empezar a crear elementos de datos y reglas en Adobe Experience Platform Launch para enviar datos PII y otros datos de aplicaciones móviles a Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementación del seguimiento de notificaciones locales</strong></p>
    </div>
    <p>Obtenga información aquí sobre cómo asegurarse de que el seguimiento de notificaciones locales se haya implementado correctamente. </br><a href="../../administration/using/local-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Creación de una notificación push {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparación y envío de una notificación push</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Aprenda </strong></a> a preparar la notificación push y a enviarla a la audiencia de destino.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de una notificación push</strong></p>
    </div>
    <p>Para ajustar la entrega, Adobe Campaign le permite acceder a un conjunto de opciones mientras diseña una notificación push.</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Creación de una notificación push multilingüe</strong></p>
    </div>
    <p>Personalice el contenido de las notificaciones push enviando mensajes en función de los idiomas y regiones preferidos de los usuarios.</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Mostrar una imagen desde una notificación push de Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Aprenda </strong></a> a mostrar una imagen desde una notificación push de Adobe Campaign en un dispositivo iOS.</p>
    <br>
  </td>
</tr>
</table>

## Crear un mensaje en la aplicación {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparación y envío de un mensaje en la aplicación</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Aprenda </strong></a> a preparar los mensajes en la aplicación y a enviarlos a la audiencia de destino.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de los mensajes en la aplicación</strong></p>
    </div>
    <p>Para ajustar mejor su envío, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña una aplicación.</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Personalización de un tipo de mensaje de notificación local</strong></p>
    </div>
    <p>Las notificaciones locales solo se pueden activar mediante una aplicación en un momento determinado y en función de un evento. </br><a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Informe en la aplicación</strong></p>
    </div>
    <p>El informe en la aplicación proporciona detalles relacionados con los envíos en la aplicación.</br><a href="../../reporting/using/in-app-report.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Creación de mensajes SMS {#create-sms}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Creación de un mensaje SMS</strong></p>
    </div>
    <p>Crear un envío SMS es muy similar a crear un correo electrónico normal. </br>Los pasos  <a href="../../channels/using/creating-an-sms-message.md"><strong>detallados a </strong></a> continuación describen la configuración específica de este canal.</br></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de un mensaje SMS
</strong></p>
    </div>
    <p>Para ajustar mejor su envío, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña un mensaje SMS.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>Haga clic aquí para obtener más información.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong></p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Administración de SMS entrantes</strong></p>
    </div>
    <p>Cuando un perfil responde a un mensaje SMS enviado mediante Campaign, puede configurar mensajes que se le envían automáticamente, así como la acción que se va a realizar. Personalización de un tipo de mensaje de notificación local</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Haga clic aquí para obtener más información.</br><a href="../../channels/using/managing-incoming-sms.md"><strong></p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Informe SMS</strong></p>
    </div>
    <p>El informe SMS proporciona detalles sobre los envíos SMS, como los entregados y las tasas de devoluciones.</br><a href="../../reporting/using/sms-report.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Solución de problemas del dispositivo móvil {#mobile-troubleshooting}

Las siguientes páginas le ayudarán a resolver los problemas más comunes que se producen al utilizar la entrega móvil en Adobe Campaign Classic.

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preguntas frecuentes sobre notificaciones push</strong></p>
    </div>
    <p><a href="../../channels/using/about-push-notifications.md#push-faq"><strong>Haga clic aquí para obtener más información.</p>
  </td>
  <td>
    <div>
    <p><strong>Preguntas frecuentes sobre la sincronización de Adobe Launch</strong></p>
    </div>
    <p><a href="../../channels/using/in-app-faq.md"><strong>Haga clic aquí para obtener más información.</p>
  </td>
  <td>
    <div>
    <p><strong>Preguntas frecuentes en la aplicación</strong></p>
    </div>
    <p><a href="../../administration/using/syncwithlaunch-faq.md"><strong>Haga clic aquí para obtener más información.</p>
  </td>
</tr>
</table>


