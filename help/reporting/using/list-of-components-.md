---
title: 'Lista de componentes '
description: Encuentre aquí la lista de todos los componentes disponibles en los informes dinámicos, así como sus definiciones.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 8980bf05-60a8-4360-a354-445e1faeb5b2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 3%

---

# Lista de componentes {#list-of-components}

Para obtener más información sobre la compatibilidad entre dimensiones y métricas, consulte esta [tabla](/help/reporting/using/assets/dynamic_report_compatibility.pdf). Si dos componentes no son compatibles, la celda mostrará el valor **Ninguna**.

[![imagen](assets/dynamic_report_compatibility.png)](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf?lang=en)

## Dimension {#dimensions}

La tabla siguiente proporciona la lista de dimensiones utilizadas en los informes y sus definiciones.

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
   <td> País/región<br /> </td> 
   <td> País registrado en el perfil del destinatario.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Etiqueta e ID de la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dispositivo<br /> </td> 
   <td> Dispositivo desde el que se abrió, visualizó o hizo clic en la notificación de correo electrónico/SMS/push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Motivo del error<br /> </td> 
   <td> Tipos de errores que causaban devoluciones para cada entrega, por ejemplo, usuario desconocido, dominio no válido o buzón lleno.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sexo<br /> </td> 
   <td> Sexo del destinatario, como hombre o mujer. Si el campo gender está vacío en el perfil del destinatario, el valor es none.<br /> </td> 
  </tr> 
  <tr> 
   <td> Acciones de mensajes en la aplicación<br /> </td> 
   <td> Acciones sobre el mensaje en la aplicación enviado, por ejemplo, acciones sobre el botón 1 o 2 o despidos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tipo de mensaje<br /> </td> 
   <td> Canal utilizado para el envío, como correo electrónico, SMS, notificaciones push o en la aplicación.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nombre de la aplicación móvil<br /> </td> 
   <td> Nombre de la aplicación móvil<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma<br /> </td> 
   <td> Plataforma del dispositivo desde el que se abrió, visualizó o hizo clic en el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Perfil<br /> </td> 
   <td> Reagrupa los campos de perfil predeterminados y personalizados creados durante la extensión de recursos de perfil. Para obtener más información, consulte <a href="../../developing/using/key-steps-to-add-a-resource.md">página</a> o <a href="../../reporting/using/creating-a-custom-profile-dimension.md">ejemplo</a>.<br /> Tenga en cuenta que los datos de esta dimensión se recuperan en cuanto se publica el recurso personalizado vinculado al campo de perfil.<br /> </td> 
  </tr> 
  <tr> 
   <td> Plataforma push<br /> </td> 
   <td> Plataforma del dispositivo desde el que se abrió la notificación push, como iOS o Android.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dominio de destinatario<br /> </td> 
   <td> Dominio utilizado para abrir el correo electrónico.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega recurrente<br /> </td> 
   <td> Etiqueta e ID de la entrega recurrente.<br /> </td> 
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
   <td> Dirección URL en la que el usuario hizo clic desde el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Categoría de URL de seguimiento<br /> </td> 
   <td> Categoría asignada a la dirección URL de seguimiento.<br /> </td> 
  </tr> 
  <tr> 
   <td> Etiqueta de URL de seguimiento<br /> </td> 
   <td> Etiqueta dada a la dirección URL, como página espejo, póngase en contacto con nosotros o abra.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega transaccional<br /> </td> 
   <td> Etiqueta e ID de la entrega transaccional.<br /> </td> 
  </tr> 
  <tr> 
   <td> Variant<br /> </td> 
   <td> Variant del correo electrónico en caso de prueba A/B.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Métricas {#metrics}

Las tablas siguientes proporcionan la lista de métricas utilizadas en los informes y sus definiciones en función del tipo de envío.

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
   <td> En lista de bloqueados<br /> </td> 
   <td> Número de destinatarios que han declarado un correo electrónico como correo no deseado o no deseado.<br /> </td> 
  </tr> 
  <tr> 
   <td> lista de bloqueados tasa de <br /> </td> 
   <td> Porcentaje de envíos marcados en lista de bloqueados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Errores<br /> </td> 
   <td> Total de errores acumulados durante la entrega y el procesamiento automático de devoluciones en relación con la cantidad total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Tasa de error<br /> </td> 
   <td> Porcentaje de correos electrónicos devueltos en comparación con el correo electrónico enviado.<br /> </td> 
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
   <td> Número de mensajes enviados correctamente, en relación con el número total de mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> Porcentaje de mensajes enviados correctamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo grave<br /> </td> 
   <td> Número total de errores permanentes, como una dirección de correo electrónico incorrecta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de salida hacia otro sitio<br /> </td> 
   <td> Porcentaje de envíos que fallaron debido a errores permanentes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Página espejo<br /> </td> 
   <td> Número de destinatarios que hicieron clic en el vínculo de la página espejo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de página espejo<br /> </td> 
   <td> Porcentaje de clics en el vínculo de página espejo comparado con el total de mensajes de entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics en ofertas<br /> </td> 
   <td> Número de veces que se hizo clic en una oferta en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de clics de ofertas<br /> </td> 
   <td> Porcentaje de clics en una oferta.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> Número de veces que se abrió un mensaje en una entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> Porcentaje de mensajes abiertos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de envíos para la entrega.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cuarentena<br /> </td> 
   <td> Número de mensajes que se devolvieron y que dieron como resultado la cuarentena de la dirección.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de cuarentena<br /> </td> 
   <td> Porcentaje de cuarentena comparado con los mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazado<br /> </td> 
   <td> Número de mensajes clasificados como correo no deseado por los servidores SMTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa rechazada<br /> </td> 
   <td> Porcentaje de mensajes marcados como rechazados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Rechazo suave<br /> </td> 
   <td> Número total de errores temporales, como una bandeja de entrada completa.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de devoluciones suave<br /> </td> 
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
   <td> Número de bajas únicas en comparación con los mensajes enviados.<br /> </td> 
  </tr> 
  <tr> 
   <td> Cancelación de suscripción<br /> </td> 
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
   <td> Total de errores acumulados durante la entrega en relación con el número total de mensajes enviados, por ejemplo errores de MCPNS o del proveedor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Devoluciones + Tasa de error<br /> </td> 
   <td> Porcentaje de notificaciones push que rebotaron en comparación con las notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Haga clic en<br /> </td> 
   <td> Número de veces que el usuario ha enviado una notificación push al dispositivo y ha hecho clic en ella. El usuario quería ver la notificación, que luego se moverá al seguimiento de Push Open, o la descartará.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de pulsaciones<br /> </td> 
   <td> Porcentaje de usuarios que interactuaron con la notificación push.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entrega<br /> </td> 
   <td> Número de notificaciones push enviadas correctamente, en relación con el número total de notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de entrega<br /> </td> 
   <td> Porcentaje de notificaciones push enviadas correctamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> Número de veces que se ha enviado una notificación push al dispositivo y se ha dejado intacta en el centro de notificaciones. En la mayoría de los casos, el número de impresiones debe ser similar al número entregado. Esto garantiza que el dispositivo obtuvo el mensaje y retransmitió esa información al servidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de notificaciones push enviadas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Apertura<br /> </td> 
   <td> Número total de notificaciones push enviadas al dispositivo y en las que los usuarios han hecho clic para abrir la aplicación. Esto es similar al clic push , excepto que no se activará un push Open si se descarta la notificación.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de apertura<br /> </td> 
   <td> Porcentaje de notificaciones push abiertas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos<br /> </td> 
   <td> Número de veces que un usuario único interactúa con la notificación push, por ejemplo, haciendo clic en la notificación o el botón.<br /> </td> 
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
   <td> Número total de mensajes en la aplicación que el proveedor de servicios entrega al dispositivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones<br /> </td> 
   <td> Total de mensajes en la aplicación vistos por los destinatarios en función de si se cumplió el criterio de déclencheur.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics en la aplicación <br /> </td> 
   <td> Número total de destinatarios que hicieron clic en el Botón 1 o en el Botón 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de clics en la aplicación<br /> </td> 
   <td> Porcentaje de usuarios que hicieron clic en Botón 1 o Botón 2 comparados con los usuarios que vieron el mensaje.<br /> </td> 
  </tr> 
  <tr> 
   <td> Despido en la aplicación<br /> </td> 
   <td> Número total de mensajes que los destinatarios descartaron haciendo clic en el botón cerrar o descartando automáticamente.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tasa de despido en la aplicación<br /> </td> 
   <td> Porcentaje de mensajes en la aplicación que los destinatarios descartaron.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesado/enviado<br /> </td> 
   <td> Número total de mensajes en la aplicación enviados desde Adobe Campaign como parte del proceso de envío enviado.<br /> </td> 
  </tr> 
  <tr> 
   <td> Impresiones únicas<br /> </td> 
   <td> Número de impresiones por un destinatario único.<br /> </td> 
  </tr> 
  <tr> 
   <td> Clics únicos en la aplicación<br /> </td> 
   <td> Número de veces que los destinatarios hicieron clic en el Botón 1 o en el Botón 2.<br /> </td> 
  </tr> 
  <tr> 
   <td> Eliminaciones únicas en la aplicación<br /> </td> 
   <td> Número de veces que los destinatarios descartaron un mensaje en la aplicación.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Segmentos {#segments}

La siguiente tabla le ofrece la lista de segmentos utilizados en los informes y sus definiciones.

<table> 
 <thead> 
  <tr> 
   <th> Segmento<br /> </th> 
   <th> Definición<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Edad: Boomers 1<br /> </td> 
   <td> Destinatarios nacidos entre 1946 y 1954.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Boomers 2<br /> </td> 
   <td> Destinatarios nacidos entre 1955 y 1965.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 18 a 25<br /> </td> 
   <td> Destinatarios de 18 a 25 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 26 a 30<br /> </td> 
   <td> Destinatarios de 26 a 30 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 31 a 40<br /> </td> 
   <td> Destinatarios de 31 a 40 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: De 41 a 50<br /> </td> 
   <td> Destinatarios de 41 a 50 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación X<br /> </td> 
   <td> Destinatarios nacidos entre 1966 y 1976.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación Y (milenios)<br /> </td> 
   <td> Destinatarios nacidos entre 1977 y 1994.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Generación Z<br /> </td> 
   <td> Destinatarios nacidos desde 1995 hasta hoy.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Buenos a 50<br /> </td> 
   <td> Destinatarios cuya edad es buena a 50 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 25<br /> </td> 
   <td> Destinatarios cuya edad es menor de 25 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 30<br /> </td> 
   <td> Destinatarios cuya edad es menor de 30 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 40<br /> </td> 
   <td> Destinatarios cuya edad es menor de 40 años.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edad: Menos de 50<br /> </td> 
   <td> Destinatarios cuya edad es menor de 50 años.<br /> </td> 
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
