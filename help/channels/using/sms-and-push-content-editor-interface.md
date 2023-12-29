---
title: Interfaz de editor de contenido push y SMS
description: Aprenda a utilizar las diferentes secciones del editor para modificar el contenido de mensajes SMS y push.
audience: designing
content-type: reference
topic-tags: editing-sms-and-push-content
context-tags: delivery,smsContent,back
feature: SMS
role: User
level: Intermediate
exl-id: d430d0e7-1201-49c6-aad3-a2c03d02290c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 96%

---

# Interfaz de editor de contenido push y SMS{#sms-and-push-content-editor-interface}

El editor de contenido push y SMS está organizado en dos secciones diferentes que le permiten ver y editar el mensaje.

1. La **barra de acciones** contiene las opciones generales de la página. Puede insertar campos de personalización o bloques de contenido, añadir texto condicional y previsualizar su contenido SMS desde aquí. Consulte [Barra de acciones del editor de contenido push y SMS](#sms-and-push-content-editor-action-bar).
1. La **zona de edición** de la pantalla le permite introducir directamente el mensaje de texto y seleccionar dónde desea insertar la personalización. Consulte [los modos de edición de contenido push y SMS](#sms-and-push-content-edition-modes).

## Barra de acciones del editor de contenido push y SMS {#sms-and-push-content-editor-action-bar}

La barra de acciones contiene diferentes botones que le permiten interactuar con el contenido que se está creando.

<table> 
 <thead> 
  <tr> 
   <th> Icono<br /> </th> 
   <th> Nombre del botón<br /> </th> 
   <th> Canal<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <img height="21px" src="assets/viewon_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Previsualización</span> <br /> </td> 
   <td> Solo SMS<br /> </td> 
   <td> Permite ver cómo se representa el correo electrónico para un destinatario. Consulte <a href="../../sending/using/previewing-messages.md">Vista previa de mensajes</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/undo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Deshacer</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Cancela la última acción realizada.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/redo_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Rehacer</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Rehace la última acción que se ha cancelado.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_field_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserción de un campo de personalización</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Permite añadir un campo de la base de datos al contenido. Consulte <a href="../../designing/using/personalization.md#inserting-a-personalization-field" target="_blank">Inserción de un campo de personalización</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/personalization_block_darkgrey-24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Inserción de un bloque de contenido</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Permite añadir un bloque de personalización al contenido. Consulte <a href="../../designing/using/personalization.md#adding-a-content-block" target="_blank">Adición de un bloque de contenido</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontent_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Habilitación de texto dinámico</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Permite insertar texto dinámico en el contenido. Consulte <a href="../../channels/using/defining-dynamic-text.md" target="_blank">Definición de texto dinámico</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> <img height="21px" src="assets/dynamiccontentdisable_24px.png" /> <br /> </td> 
   <td> <span class="uicontrol">Deshabilitación de texto dinámico</span> <br /> </td> 
   <td> SMS y push<br /> </td> 
   <td> Permite eliminar texto dinámico.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Modos de edición de contenido push y SMS {#sms-and-push-content-edition-modes}

El editor de contenido push y SMS ofrece las siguientes funcionalidades:

* Escriba texto.
* Añada un campo personalizado. Para obtener más información al respecto, consulte [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).
* Añada un bloque de contenido. Para obtener más información al respecto, consulte [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block).
* Añada texto dinámico. Para obtener más información al respecto, consulte [Definición de texto dinámico](../../channels/using/defining-dynamic-text.md).
* Personalice el nombre del remitente del SMS (solo SMS). Para obtener más información al respecto, consulte [Configuración de SMS](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
