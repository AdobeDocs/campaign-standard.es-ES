---
title: Flujos de trabajo técnicos
description: Descubra más información sobre los Flujos de trabajo técnicos
audience: administration
feature: Instance Settings
role: Admin
level: Experienced
exl-id: da3a3af5-207a-4289-bd07-00a8c5d1cf57
source-git-commit: 2e81a05b1b647991250d13d7d37f5da275a8db44
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 76%

---

# Flujos de trabajo técnicos{#technical-workflows}

Los flujos de trabajo técnicos se entregan ya preparados con Adobe Campaign. Los flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse de forma regular en el servidor.

Permiten realizar operaciones de mantenimiento en la base de datos, aprovechar la información de seguimiento de los envíos y actualizar los trabajos provisionales de los envíos.

Los administradores funcionales pueden acceder a los flujos de trabajo técnicos desde el menú **[!UICONTROL Administration > Application settings > Workflows]**.

>[!NOTE]
>
>Como administrador funcional, puede reiniciar o pausar flujos de trabajo técnicos y modificar sus propiedades y estructura.

![](assets/technical_workflows.png)

## Lista de flujos de trabajo técnicos {#list-of-technical-workflows}

Los flujos de trabajo técnicos se utilizan para gestionar procesos técnicos y de fondo autoactivados en Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Prueba A/B</span> <br /> </td> 
   <td> <span class="uicontrol">abTesting</span> <br /> </td> 
   <td> Este flujo de trabajo analiza los registros de seguimiento de cada variante. Al final del periodo de prueba A/B, calcula automáticamente la variante ganadora. De forma predeterminada, se inicia todos los días.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturación</span> <br /> </td> 
   <td> <span class="uicontrol">facturación</span> <br /> </td> 
   <td> Este flujo de trabajo envía el informe de actividad del sistema al usuario de “facturación” por correo electrónico. De forma predeterminada, se inicia automáticamente todos los días a las 01:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Copia de encabezados de plantillas de envío</span> <br /> </td> 
   <td> <span class="uicontrol">smtpHeaderupdate</span> <br /> </td> 
   <td> Este flujo de trabajo copia los encabezados SMTP establecidos para las plantillas de envíos de correo electrónico en los envíos secundarios correspondientes que no sean plantillas. Este flujo de trabajo solo recoge las entregas de marketing por correo electrónico. Los encabezados SMTP no se copian en envíos transaccionales y envíos de prueba. <br> Este flujo de trabajo no se ejecuta periódicamente. El usuario debe iniciarlo en función de cada uso. <!--So it'not really a technical workflow like all workflows on this page, because it's not run automatically - TBC--> <br> Si hay un gran volumen de envíos en la instancia, puede actualizar la opción NmsCleanup_DeliveryPurgeDelay en <strong>Configuración de aplicación</strong>. Si realiza un cambio en los encabezados SMTP de cualquier plantilla, debe volver a ejecutar el flujo de trabajo después del cambio para que los encabezados corregidos se copien en los envíos que no sean de plantilla.<a href="data-retention.md#deliveries">Más información</a>
   <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Database cleanup</span> <br /> </td> 
   <td> <span class="uicontrol">cleanup</span> <br /> </td> 
   <td> Este flujo de trabajo es el flujo de trabajo de mantenimiento de la base de datos: ejecuta diferentes estadísticas y procesos y elimina datos obsoletos de la base de datos según la configuración que se haya definido. De forma predeterminada, se inicia automáticamente todos los días a las 04:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsión</span> <br /> </td> 
   <td> <span class="uicontrol">previsión</span> <br /> </td> 
   <td> Este flujo de trabajo ejecuta el análisis de los envíos almacenados en la previsión provisional (creación de los registros provisionales). De forma predeterminada, se inicia cada día a las 01:00. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importación de una audiencia compartida</span> <br /> </td> 
   <td> <span class="uicontrol">importSharedAudience</span> <br /> </td> 
   <td> Este flujo de trabajo sincroniza los datos de audiencia de Adobe Experience Cloud importados en Adobe Campaign. De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uso compartido instantáneo de informes</span> <br /> </td> 
   <td> <span class="uicontrol">reportSendingNow</span> <br /> </td> 
   <td> Este flujo de trabajo se inicia en cuanto se programa el envío de un informe. Convierte el informe en un archivo pdf y luego lo envía por correo electrónico a los destinatarios objetivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliación de KPI con Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiReconciliation</span> <br /> </td> 
   <td> Este flujo de trabajo recupera los KPI del servicio de creación de informes una vez al día y los reconcilia con los datos de Adobe Analytics. Luego inserta la diferencia si es necesario. De forma predeterminada, se inicia cada día a las 04:20.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archivado local del centro de mensajes</span> <br /> </td> 
   <td> <span class="uicontrol">mcSynch_local</span> <br /> </td> 
   <td> Este flujo de trabajo archiva eventos en tiempo real en una tabla histórica. De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reporting aggregates</span> <br /> </td> 
   <td> <span class="uicontrol">reportingAggregates</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza los agregados que se utilizan en los informes. De forma predeterminada, se inicia automáticamente a las 02:00.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uso compartido de KPI con Adobe Analytics</span> <br /> </td> 
   <td> <span class="uicontrol">kpiSharing</span> <br /> </td> 
   <td> Este flujo de trabajo envía datos KPI cada 15 minutos desde Adobe Campaign Standard a Adobe Analytics.<br /> </td> 
  </tr> 
    </tr> 
   <tr> 
   <td> <span class="uicontrol">Sincronización con Launch</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Este flujo de trabajo sincroniza las propiedades móviles de etiquetas importadas en Adobe Campaign Standard. Se inicia cada 15 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Recuperación de registros de seguimiento</span> <br /> </td> 
   <td> <span class="uicontrol">SyncWithLaunch</span> <br /> </td> 
   <td> Este flujo de trabajo sincroniza las propiedades móviles de etiquetas importadas en Adobe Campaign Standard. Se inicia cada 15 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Recuperar registros de seguimiento</span> <br /> </td> 
   <td> <span class="uicontrol">trackingLogRecovery</span> <br /> </td> 
   <td> Este flujo de trabajo restaura los registros de seguimiento perdidos. Tenga en cuenta que este flujo de trabajo técnico se utiliza en contextos específicos y se restringe únicamente al uso interno del Adobe. <br> De forma predeterminada, se inicia cada 10 minutos.<br /> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Actualización de la ejecución de entrega</span> <br/> </td> 
   <td> <span class="uicontrol">updateDeliveryExecInfo</span> <br/> </td> 
   <td> Este flujo de trabajo copia los broadlogs y los registros de seguimiento en la base de datos local. De forma predeterminada, se inicia cada 10 minutos.<br/> </td> 
  </tr>
  <tr> 
   <td> <span class="uicontrol">Actualización de los indicadores de entrega</span> <br /> </td> 
   <td> <span class="uicontrol">updateDeliveryIndicators</span> <br /> </td> 
   <td> Este flujo de trabajo actualiza los KPI de la entrega (indicador clave de rendimiento). De forma predeterminada, se inicia cada hora.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar estado del evento</span> <br /> </td> 
   <td> <span class="uicontrol">updateEventsStatus</span> <br /> </td> 
   <td> Este flujo de trabajo le permite atribuir un estado a un evento. Están disponibles los siguientes estados de evento:<br /> <strong>Pendiente</strong>: el evento está en una cola. Aún no se le ha asignado ninguna plantilla de mensaje.<br /> <span class="uicontrol">Entrega pendiente</span>: el evento está en cola, se le ha asignado una plantilla de mensaje y la entrega lo está procesando.<br /> <strong>Enviado</strong>: este estado se copia desde los registros de envío. Significa que la entrega se ha enviado.<br /> <strong>Ignorado por la entrega</strong>: este estado se copia desde los registros de envío. Significa que la entrega se ha omitido.<br /> <strong>Error de entrega</strong>: este estado se copia desde los registros de envío. Significa que la entrega ha fallado.<br /> <span class="uicontrol">No se tiene en cuenta el evento</span>: el evento no se ha podido relacionar con una plantilla de mensaje. El evento no se va a procesar.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Update for deliverability</span> <br /> </td> 
   <td> <span class="uicontrol">deliverabilityUpdate</span> <br /> </td> 
   <td> Este flujo de trabajo le permite crear la lista de reglas de calificación de regla devuelta, así como la lista de dominios y los MX de la plataforma. Este flujo de trabajo solo funciona si HTTPS está abierto. De forma predeterminada, se inicia automáticamente a las 02:00.<br /> </td> 
  </tr> 
 </tbody> 
</table>
