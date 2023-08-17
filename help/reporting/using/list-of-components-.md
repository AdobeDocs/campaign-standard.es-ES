---
title: Lista de componentes
description: Aquí encontrará la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 5%

---

# Lista de componentes {#list-of-components}

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte esta sección [tabla](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Si dos componentes no son compatibles, la celda mostrará el valor **Ninguno**.

[![imagen](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

## Dimensiones {#dimensions}

La siguiente tabla le proporciona la lista de dimensiones utilizadas en los informes y sus definiciones.

<table> 
 <thead> 
  <tr> 
   <th> Dimensión<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Explorador<br /> </td> 
   <td> Explorador desde el que se abrió o se hizo clic en el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaña<br /> </td> 
   <td> Etiqueta e ID de la campaña.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ciudad<br /> </td> 
   <td> Ciudad registrada en el perfil del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> País o región<br /> </td> 
   <td> País registrado en el perfil del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Etiqueta e ID de envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo desde el que se abrió, vio o hizo clic la notificación push/SMS/de correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo del error<br /> </td> 
   <td> Tipos de errores que ocasionaban devoluciones para cada entrega; por ejemplo, usuario desconocido, dominio no válido o buzón lleno.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Sexo del destinatario, como hombre o mujer. Si el campo de sexo está vacío en el perfil del destinatario, el valor es ninguno.<br /> </td> 
  </tr> 
  <tr> 
   <td> Acciones de mensajes en la aplicación<br /> </td> 
   <td> Acciones sobre el mensaje en la aplicación entregado, p. ej. acciones sobre el botón 1 o 2 o despidos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensaje<br /> </td> 
   <td> Canal utilizado para el envío, como correo electrónico, SMS, notificación push o en la aplicación.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nombre de aplicación móvil<br /> </td> 
   <td> Nombre de la aplicación móvil<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma<br /> </td> 
   <td> Plataforma del dispositivo desde el que se abrió, visualizó o hizo clic en el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br /> </td> 
   <td> Reagrupa los campos de perfil predeterminados y personalizados creados durante la extensión de recursos de perfil; para obtener más información, consulte <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> o esto <a href="../../reporting/using/creating-a-custom-profile-dimension.md">ejemplo</a>.<br /> Tenga en cuenta que los datos de esta dimensión se recuperan en cuanto se publica el recurso personalizado vinculado al campo de perfil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma push<br /> </td> 
   <td> Plataforma del dispositivo desde el que se abrió la notificación push como, por ejemplo, iOS o Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio del destinatario<br /> </td> 
   <td> Dominio utilizado para abrir el correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega recurrente<br /> </td> 
   <td> Etiqueta e ID del envío recurrente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio del remitente<br /> </td> 
   <td> Dominio utilizado para enviar el correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> IP del remitente<br /> </td> 
   <td> IP utilizada para enviar el correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Estado<br /> </td> 
   <td> Estado registrado en el perfil del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> URL de seguimiento<br /> </td> 
   <td> URL en la que el usuario hizo clic desde el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoría de URL de seguimiento<br /> </td> 
   <td> Categoría asignada a la URL de seguimiento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de URL de seguimiento<br /> </td> 
   <td> Etiqueta proporcionada a la dirección URL, como una página espejo, póngase en contacto con nosotros o abra.<br /> </td> 
  </tr> 
  <tr> 
   <td> Envío transaccional<br /> </td> 
   <td> Etiqueta e ID del envío transaccional.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variante<br /> </td> 
   <td> Variante del correo electrónico en el caso de las pruebas A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

Las siguientes tablas proporcionan la lista de métricas utilizadas en los informes y sus definiciones según el tipo de envío.

### Métricas de correo electrónico y SMS {#email-and-sms-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> En la lista de bloqueados<br /> </td> 
   <td> Número de destinatarios que han declarado un correo electrónico como no deseado o no deseado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de Lista de bloqueados de la<br /> </td> 
   <td> Porcentaje de envíos marcados en el momento de la lista de bloqueados de la.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> Total de errores acumulados durante el envío y el procesamiento automático de devoluciones en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error<br /> </td> 
   <td> Porcentaje de correos electrónicos devueltos en comparación con los enviados por correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic en<br /> </td> 
   <td> Número de veces que se hizo clic en un contenido en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> Porcentaje de clics en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de mensajes enviados correctamente en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> Porcentaje de mensajes enviados correctamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo duro<br /> </td> 
   <td> Número total de errores permanentes, como una dirección de correo electrónico incorrecta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de salida hacia otro sitio dura<br /> </td> 
   <td> Porcentaje de envíos que fallaron debido a errores permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Página espejo<br /> </td> 
   <td> Número de destinatarios que hicieron clic en el vínculo de la página espejo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Velocidad de página espejo<br /> </td> 
   <td> Porcentaje de clics en el vínculo de la página espejo comparados con el total de mensajes de envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics de oferta<br /> </td> 
   <td> Número de veces que se hizo clic en una oferta en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones de oferta<br /> </td> 
   <td> Porcentaje de clics en una oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> Número de veces que se ha abierto un mensaje en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> Porcentaje de mensajes abiertos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de envíos para el envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cuarentena<br /> </td> 
   <td> Número de mensajes que rebotaron y que dieron lugar a la cuarentena de la dirección.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de cuarentena<br /> </td> 
   <td> Porcentaje de cuarentenas comparadas con mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> Número de mensajes clasificados como correo no deseado por los servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de rechazados<br /> </td> 
   <td> Porcentaje de mensajes marcados como rechazados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo suave<br /> </td> 
   <td> Número total de errores temporales, como una bandeja de entrada llena.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones suaves<br /> </td> 
   <td> Porcentaje de envíos que fallaron debido a un motivo temporal.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> Número de destinatarios que hicieron clic en un contenido de una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> Número de destinatarios que abrieron la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Baja única<br /> </td> 
   <td> Número de destinatarios que hicieron clic en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de cancelación de suscripción<br /> </td> 
   <td> Número de bajas únicas comparadas con los mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cancelado<br /> </td> 
   <td> Número de clics en el vínculo de baja de suscripción.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas de notificaciones push {#push-notification-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> Total de errores acumulados durante el envío en relación con el número total de mensajes enviados, por ejemplo, errores de MCPNS o del proveedor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devolución + Tasa de error<br /> </td> 
   <td> Porcentaje de notificaciones push que rebotaron en comparación con las notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic en<br /> </td> 
   <td> Número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario deseaba ver la notificación, que luego se moverá al seguimiento de Apertura push, o descartarla.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> Porcentaje de usuarios que interactuaron con la notificación push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de notificaciones push enviadas correctamente en relación con el número total de notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> Porcentaje de notificaciones push enviadas correctamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> Número de veces que se ha enviado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número enviado. Esto garantiza que el dispositivo reciba el mensaje y retransmita esa información al servidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> Número total de notificaciones push enviadas al dispositivo y en las que los usuarios hicieron clic al abrir la aplicación. Esto es similar al clic push, excepto que una apertura push no se activa si se descarta la notificación.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> Porcentaje de notificaciones push abiertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> Número de veces que un usuario único interactúa con la notificación push; por ejemplo, hace clic en la notificación o el botón.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> Número de impresiones por destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Aperturas únicas<br /> </td> 
   <td> Número de destinatarios que abrieron la entrega.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Métricas en la aplicación {#in-app-metrics}

<table> 
 <thead> 
  <tr> 
   <th> Métrica<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número total de mensajes en la aplicación enviados al dispositivo por el proveedor de servicios.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> Total de mensajes en la aplicación vistos por los destinatarios según si se cumplió el criterio de déclencheur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics en la aplicación <br /> </td> 
   <td> Número total de destinatarios que hicieron clic en el botón 1 o el botón 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones en la aplicación<br /> </td> 
   <td> Porcentaje de usuarios que hicieron clic en el botón 1 o el botón 2 comparados con los usuarios que vieron el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despido en la aplicación<br /> </td> 
   <td> Número total de mensajes que los destinatarios descartaron al hacer clic en el botón Cerrar o descartar automáticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de despido en la aplicación<br /> </td> 
   <td> Porcentaje de mensajes en la aplicación que los destinatarios descartaron.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de mensajes en la aplicación enviados desde Adobe Campaign como parte del proceso de envío.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> Número de impresiones de un destinatario único.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos en la aplicación<br /> </td> 
   <td> Número de veces que los destinatarios hicieron clic en el botón 1 o el botón 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Descartes únicos en la aplicación<br /> </td> 
   <td> Cantidad de veces que los destinatarios descartaron un mensaje en la aplicación.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

La siguiente tabla le proporciona la lista de segmentos utilizados en los informes y sus definiciones.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Edad: 1<br /> </td> 
   <td> Destinatarios nacidos entre 1946 y 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Boomers 2<br /> </td> 
   <td> Destinatarios nacidos entre 1955 y 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 18 a 25 años<br /> </td> 
   <td> Destinatarios de 18 a 25 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 26 a 30 años<br /> </td> 
   <td> Destinatarios de 26 a 30 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 31 a 40 años<br /> </td> 
   <td> Destinatarios de 31 a 40 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 41 a 50 años<br /> </td> 
   <td> Destinatarios de 41 a 50 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación X<br /> </td> 
   <td> Destinatarios nacidos entre 1966 y 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación Y (Millennials)<br /> </td> 
   <td> Destinatarios nacidos entre 1977 y 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación Z<br /> </td> 
   <td> Destinatarios nacidos desde 1995 hasta la actualidad.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Mayor de 50 años<br /> </td> 
   <td> Destinatarios cuya edad es mayor de 50 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 25 años<br /> </td> 
   <td> Destinatarios cuya edad es menor de 25 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 30 años<br /> </td> 
   <td> Destinatarios cuya edad es menor de 30 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 40 años<br /> </td> 
   <td> Destinatarios cuya edad es menor de 40 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 50 años<br /> </td> 
   <td> Destinatarios cuya edad es inferior a 50 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación silenciosa<br /> </td> 
   <td> Destinatarios nacidos en 1945 o antes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Todas las visitas<br /> </td> 
   <td> Cada destinatario<br /> </td> 
  </tr>
 </tbody> 
</table>
