---
title: Guía de Campaign Standard Mobile
description: Obtenga más información sobre las directrices generales para envíos móviles en Adobe Campaign Standard, como cómo configurar las aplicaciones móviles o crear notificaciones push y mensajes en la aplicación.
audience: channels
content-type: reference
topic-tags: mobile-guide
feature: Overview
role: User
level: Beginner
exl-id: d4e1b935-b21f-4a24-99ba-f455db0f7cfc
source-git-commit: afb988281f00dc17b484872259d44f51864d55f1
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 22%

---

# Introducción a los canales móviles {#mobile-guide}

<table style="table-layout:fixed">
<tr>
<td><img src="assets/do-not-localize/config_push.png" width="60px"><p>Obtenga información sobre cómo configurar la aplicación móvil para notificaciones push </br><a href="#configuration-push">Haga clic aquí</a></p></td>
<td><img src="assets/do-not-localize/config_inapp.png" width="60px"><p>Obtenga información sobre cómo configurar la aplicación móvil para mensajes en la aplicación </br><a href="#configuring-mobile-app">Haga clic aquí</a></p></td>
</tr>
<tr>
<td><img src="assets/do-not-localize/push2.png" width="60px"><p>Más información sobre cómo crear notificaciones push </br><a href="#create-push">Haga clic aquí</a></p></td>
<td><img src="assets/do-not-localize/inapp.png" width="60px"><p>Obtenga información sobre cómo crear mensajes en la aplicación</br><a href="#create-inapp">Haga clic aquí</a></p></td></tr>
</table>

## Acerca de la entrega móvil {#about-mobile}

Adobe Campaign le permite crear y enviar mensajes personalizados en varios canales y medir su eficacia mediante informes dedicados.

Con Adobe Campaign Standard, puede realizar envíos móviles a través de tres canales diferentes:

* SMS, presentados en la sección Acerca de los mensajes SMS.
* Notificaciones push, que se muestran en la sección Acerca de las notificaciones push.
* Mensajes en la aplicación, presentados en la sección Acerca de los mensajes en la aplicación.

## Configuración de la aplicación móvil para notificaciones push {#configuration-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuración de una aplicación móvil mediante los SDK de Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign mediante el uso de los SDK de Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Explicación de la estructura de carga de notificaciones push de Campaign Standard</strong></p>
    </div>
    <p>Obtenga más información acerca de la estructura de la carga útil recibida en aplicaciones móviles cuando una notificación push se envía correctamente a una aplicación desde Adobe Campaign Standard.</br><a href="../../administration/using/push-payload.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Implementación del seguimiento de notificaciones locales</strong></p>
    </div>
    <p>Obtenga información aquí sobre cómo asegurarse de que el seguimiento de notificaciones locales se ha implementado correctamente. </br><a href="../../administration/using/local-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementación del seguimiento push</strong></p>
    </div>
    <p>Aprenda a garantizar que el seguimiento de notificaciones push se haya implementado correctamente en iOS y Android.</br><a href="../../administration/using/push-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Configuración de una aplicación móvil para mensajes en la aplicación {#configuring-mobile-app}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Configuración de una aplicación móvil mediante los SDK de Adobe Experience Platform</strong></p>
    </div>
    <p>Para enviar mensajes en la aplicación y notificaciones push, las aplicaciones móviles deben configurarse en Adobe Campaign mediante el uso de los SDK de Adobe Experience Platform.</br><a href="../../administration/using/configuring-a-mobile-application.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Casos de uso móvil admitidos con los SDK de Adobe Experience Platform</strong></p>
    </div>
    <p>Obtenga más información acerca de los casos de uso móvil admitidos en Adobe Campaign Standard mediante el uso de los SDK para Adobe Experience Platform.</br><a href="../../administration/using/supported-mobile-use-cases.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Configuración de reglas de etiquetas para admitir casos de uso de Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/configuring-rules-launch.md"><strong>Haga clic aquí</strong></a> para empezar a crear elementos de datos y reglas en la interfaz de usuario de recopilación de datos para enviar PII y otros datos de aplicaciones móviles a Adobe Campaign Standard.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Implementación del seguimiento de notificaciones locales</strong></p>
    </div>
    <p>Obtenga información aquí sobre cómo asegurarse de que el seguimiento de notificaciones locales se ha implementado correctamente. </br><a href="../../administration/using/local-tracking.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Crear una notificación push {#create-push}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparación y envío de una notificación push</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-a-push-notification.md"><strong>Obtenga información aquí</strong></a> Obtenga información sobre cómo preparar la notificación push y, a continuación, cómo enviarla a la audiencia de destino.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de una notificación push</strong></p>
    </div>
    <p>Para ajustar mejor la entrega, Adobe Campaign le permite acceder a un conjunto de opciones mientras diseña una notificación push.</br><a href="../../channels/using/customizing-a-push-notification.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Creación de una notificación push multilingüe</strong></p>
    </div>
    <p>Personalice el contenido de las notificaciones push enviando mensajes en función de los idiomas y las regiones preferidos por los usuarios.</br><a href="../../channels/using/creating-a-multilingual-push-notification.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Mostrar una imagen desde una notificación push de Adobe Campaign Standard</strong></p>
    </div>
    <p><a href="../../administration/using/image-push-notification.md"><strong>Obtenga información aquí</strong></a> Obtenga información sobre cómo mostrar una imagen desde una notificación push de Adobe Campaign en un dispositivo iOS.</p>
    <br>
  </td>
</tr>
</table>

## Creación de un mensaje en la aplicación {#create-inapp}

<table style="table-layout:fixed">
<tr>
  <td>
    <div>
    <p><strong>Preparación y envío de un mensaje en la aplicación</strong></p>
    </div>
    <p><a href="../../channels/using/preparing-and-sending-an-in-app-message.md"><strong>Obtenga información aquí</strong></a> Obtenga información sobre cómo preparar los mensajes en la aplicación y, a continuación, cómo enviarlos a la audiencia de destino.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de los mensajes en la aplicación</strong></p>
    </div>
    <p>Para ajustar mejor la entrega, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña una aplicación.</br><a href="../../channels/using/customizing-an-in-app-message.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
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
    <p>Crear un envío SMS es muy similar a crear un correo electrónico normal. </br>Los pasos <a href="../../channels/using/creating-an-sms-message.md"><strong>detalladamente aquí</strong></a> describa la configuración específica de este canal.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Personalización de un mensaje SMS
</strong></p>
    </div>
    <p>Para ajustar mejor la entrega, Adobe Campaign le permite acceder a un conjunto de opciones avanzadas mientras diseña un mensaje SMS.</br><a href="../../channels/using/sms-and-push-content-editor-interface.md"><strong>Haga clic aquí para obtener más información.</p>
    <br>
  </td>
</tr>
<tr>
  <td>
    <div>
    <p><strong>Administración de SMS entrantes</strong></p>
    </div>
    <p>Cuando un perfil responde a un mensaje SMS enviado a través de Campaign, puede configurar mensajes que se envían automáticamente, así como la acción que se va a realizar.Personalización de un tipo de mensaje de notificación local</br><a href="../../channels/using/managing-incoming-sms.md"><strong>Haga clic aquí para obtener más información.</p>
    <br>
  </td>
  <td>
    <div>
    <p><strong>Informe SMS</strong></p>
    </div>
    <p>El informe SMS proporciona detalles sobre los envíos SMS, como las tasas de entrega y devolución.</br><a href="../../reporting/using/sms-report.md"><strong>Haga clic aquí</strong></a> para obtener más información.</p>
    <br>
  </td>
</tr>
</table>

## Solución de problemas móvil {#mobile-troubleshooting}

Las siguientes páginas le ayudarán a resolver los problemas más comunes que se producen al utilizar la entrega móvil en Adobe Campaign Standard.

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
