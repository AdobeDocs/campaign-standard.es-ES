---
title: Flujos de trabajo técnicos
description: Flujos de trabajo técnicos son flujos de trabajo listos para usar diseñados para gestionar procesos técnicos en segundo plano en Adobe Campaign, lo que garantiza el correcto funcionamiento de la plataforma.
page-status-flag: never-activated
uuid: 6e763dc1-e1d3-4d94-bc0b-ef5b1703d8e5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: application-settings
discoiquuid: e9f147bd-6a5b-4b82-b9bb-311e38e22c62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b4cbc56973a57cde8af6cefa9ff89c7d29ab7b79

---


# Flujos de trabajo técnicos{#technical-workflows}

Los Flujos de trabajo técnicos se entregan de forma predeterminada con Adobe Campaign. Flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse de forma regular en el servidor.

Permiten realizar operaciones de mantenimiento en la base de datos, aprovechar la información de seguimiento de los envíos y actualizar los trabajos provisionales de los envíos.

Los administradores funcionales pueden acceder a los flujos de trabajo técnicos en el **[!UICONTROL Administration > Application settings > Workflows]** menú.

>[!NOTE]
>
>Como administrador funcional, puede reiniciar o pausar flujos de trabajo técnicos y modificar sus propiedades y estructura.

![](assets/technical_workflows.png)

## Lista de flujos de trabajo técnicos {#list-of-technical-workflows}

Los Flujos de trabajo técnicos se utilizan para gestionar procesos técnicos y de fondo autoactivados en Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prueba</span> A/B <br /> </td> 
   <td> <span class="uicontrol">abTesting</span><br /> </td> 
   <td> Este flujo de trabajo analiza los registros de seguimiento de cada variante. Al final del período de prueba A/B, calcula automáticamente la variante ganadora. De forma predeterminada, se inicia todos los días.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturación</span> <br /> </td> 
   <td> <span class="uicontrol">facturación</span> <br /> </td> 
   <td> Este flujo de trabajo envía el informe de actividad del sistema al usuario de "facturación" por correo electrónico. De forma predeterminada, se inicia automáticamente todos los días a la 1 de la mañana.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Este flujo de trabajo es el flujo de trabajo de mantenimiento de la base de datos: ejecuta diferentes estadísticas y procesos, y elimina datos obsoletos de la base de datos según la configuración que se haya definido. De forma predeterminada, se inicia automáticamente todos los días a las 4 de la mañana.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsión</span><br /> </td> 
   <td> <span class="uicontrol">forecasting</span> <br /> </td> 
   <td> Este flujo de trabajo ejecuta la análisis de los envíos almacenados en la previsión provisional (creación de los registros provisionales). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar una audiencia</span> compartida <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Este flujo de trabajo sincroniza los datos de audiencia de Adobe Experience Cloud importados en Adobe Campaign. De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uso compartido</span> instantáneo de informes <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span><br /> </td> 
   <td> Este flujo de trabajo se inicia en cuanto se programa el envío de un informe. Convierte el informe en un archivo pdf y luego lo envía por correo electrónico a los destinatarios objetivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Conciliación de KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiCompatibility</span><br /> </td> 
   <td> Este flujo de trabajo obtiene los KPI del servicio de Sistema de informes una vez al día y los compara con los datos de Adobe Analytics. Luego empuja la diferencia si es necesario. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Administración de las exclusiones</span> de NMAC <br /> </td> 
   <td> <span class="uicontrol">mobileAppOptOutMgt</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza las suscripciones a las notificaciones en dispositivos móviles. De forma predeterminada, se inicia cada 6 horas entre la 1 de la mañana y la medianoche.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archiving</span> local del centro de mensajes <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span><br /> </td> 
   <td> Este flujo de trabajo archiva eventos en tiempo real en una tabla histórica. De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reporting aggregates</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza los agregados utilizados en los informes. De forma predeterminada, se inicia automáticamente a las 2 de la mañana.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartir KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span><br /> </td> 
   <td> Este flujo de trabajo envía datos KPI cada 15 minutos desde Adobe Campaign Standard a Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sincronizar con Launch</span><br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span><br /> </td> 
   <td> Este flujo de trabajo sincroniza las propiedades móviles de Adobe Launch importadas en Adobe Campaign Standard. Se inicia cada 15 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Actualizar ejecución</span> de envío <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span><br /> </td> 
   <td> Este flujo de trabajo actualiza el seguimiento del envío. De forma predeterminada, se inicia cada 10 minutos.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar indicadores</span> de envío <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span><br /> </td> 
   <td> Este flujo de trabajo actualiza los KPI del envío (Indicador de rendimiento clave). De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar estado del evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Este flujo de trabajo le permite atribuir un estado a un evento. Están disponibles los siguientes estados de evento:<br /> <strong>Pendiente</strong>: El evento está en una cola. Aún no se le ha asignado ninguna plantilla de mensaje.<br /> envío <span class="uicontrol"></span> pendiente: El evento está en la cola, se le ha asignado una plantilla de mensaje y el envío la está procesando.<br /> <strong>Enviado</strong>: Este estado se copia de los registros de envío. Significa que el envío fue enviado.<br /> <strong>Ignorado por el envío</strong>: Este estado se copia de los registros de envío. Significa que la entrega se ha omitido.<br /> Error <strong>de Envío</strong>: Este estado se copia de los registros de envío. Significa que la entrega ha fallado.<br /> No se tiene en cuenta <span class="uicontrol">el</span> Evento: El evento no se pudo vincular a una plantilla de mensaje. El evento no se va a procesar.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Este flujo de trabajo le permite crear la lista de reglas de cualificación de reglas de devolución, así como la lista de dominios y MX en la plataforma. Este flujo de trabajo solo funciona si el HTTPS está abierto. De forma predeterminada, se inicia automáticamente a las 2 de la mañana.<br /> </td> 
  </tr> 
 </tbody> 
</table>

