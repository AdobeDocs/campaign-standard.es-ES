---
title: Flujos de trabajo técnicos
seo-title: Flujos de trabajo técnicos
description: Flujos de trabajo técnicos
seo-description: Los flujos de trabajo técnicos son flujos de trabajo integrados diseñados para gestionar procesos técnicos en segundo plano en Adobe Campaign, lo que asegura el correcto comportamiento de la plataforma.
page-status-flag: no activado nunca
uuid: 6 e 763 dc 1-e 1 d 3-4 d 94-bc 0 b-ef 5 b 1703 d 8 e 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: app-settings
discoiquuid: e 9 f 147 bd -6 a 5 b -4 b 82-b 9 bb -311 e 38 e 22 c 62
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2541b6dadd005c74d6bb737a0e3692e63a5b85db

---


# Technical workflows{#technical-workflows}

Los flujos de trabajo técnicos se entregan directamente con Adobe Campaign. Los flujos de trabajo técnicos son operaciones o trabajos programados para ejecutarse con regularidad en el servidor.

Permiten llevar a cabo operaciones de mantenimiento en la base de datos, aprovechar la información de seguimiento en los envíos y actualizar los trabajos provisionales en los envíos.

Functional administrators can access technical workflows under the **[!UICONTROL Administration > Application settings > Workflows]** menu.

>[!NOTE]
>
>Como administrador funcional, puede reiniciar o pausar flujos de trabajo técnicos y modificar sus propiedades y estructura.

![](assets/technical_workflows.png)

## List of technical workflows {#list-of-technical-workflows}

Los flujos de trabajo técnicos se utilizan para gestionar los procesos técnicos y de fondo autoactivados en Adobe Campaign.

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Etiqueta</strong><br /> </td> 
   <td> <strong>ID</strong><br /> </td> 
   <td> <strong>Descripción</strong><br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Pruebas A/B</span><br /> </td> 
   <td> <span class="uicontrol">Abtesting</span><br /> </td> 
   <td> Este flujo de trabajo analiza los registros de seguimiento de cada variante. Al finalizar el período de prueba A/B, calcula automáticamente la variante ganadora. By default, it is started every day.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Facturación</span><br /> </td> 
   <td> <span class="uicontrol">facturación</span><br /> </td> 
   <td> Este flujo de trabajo envía el informe de actividad del sistema al usuario de facturación por correo electrónico. By default, it is automatically started every day at 1am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Limpieza de base de datos</span><br /> </td> 
   <td> <span class="uicontrol">limpiar</span><br /> </td> 
   <td> Este flujo de trabajo es el flujo de trabajo de mantenimiento de la base de datos: ejecuta diferentes estadísticas y procesos, y elimina los datos obsoletos de la base de datos según la configuración definida. By default, it is automatically started every day 4am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Previsión</span><br /> </td> 
   <td> <span class="uicontrol">previsión</span><br /> </td> 
   <td> Este flujo de trabajo ejecuta el análisis de los envíos almacenados en la previsión provisional (creación de registros provisionales). By default, it is started every day at 1am. <br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Importar una audiencia compartida</span><br /> </td> 
   <td> <span class="uicontrol">Importsharedaudience</span><br /> </td> 
   <td> Este flujo de trabajo sincroniza los datos de audiencia de Adobe Experience Cloud importados en Adobe Campaign. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Uso compartido de informes instantáneos</span><br /> </td> 
   <td> <span class="uicontrol">Reportsendingnow</span><br /> </td> 
   <td> Este flujo de trabajo se inicia tan pronto como se programe un informe. It converts your report into a pdf file then sends it in an email to the targeted recipients.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Reconciliación de KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpireconciliación</span><br /> </td> 
   <td> Este flujo de trabajo recoge los KPI del servicio de informes una vez al día y los compara con los datos de Adobe Analytics. A continuación, inserta la diferencia si es necesario. By default, it is started every day at 4.20am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Administración de exclusiones NMAC</span><br /> </td> 
   <td> <span class="uicontrol">Mobileappoptoutmgt</span><br /> </td> 
   <td> Este flujo de trabajo actualiza las suscripciones a las notificaciones en dispositivos móviles. By default, it is started every 6 hours between 1am and midnight.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Archivo local del Centro de mensajes</span><br /> </td> 
   <td> <span class="uicontrol">Mcsynch_ local</span><br /> </td> 
   <td> Este flujo de trabajo archiva eventos en tiempo real en una tabla histórica. By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Informes agregados</span><br /> </td> 
   <td> <span class="uicontrol">Informes agregados</span><br /> </td> 
   <td> Este flujo de trabajo actualiza los agregados utilizados en los informes. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Compartir KPI con Adobe Analytics</span><br /> </td> 
   <td> <span class="uicontrol">Kpisharing</span><br /> </td> 
   <td> This workflow pushes KPI data every 15 minutes from Adobe Campaign Standard to Adobe Analytics.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualización de la ejecución de entrega</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryexecinfo</span><br /> </td> 
   <td> Este flujo de trabajo actualiza el seguimiento de la entrega. By default, it is started every 10 minutes.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar los indicadores de entrega</span><br /> </td> 
   <td> <span class="uicontrol">Updatedeliveryindicator</span><br /> </td> 
   <td> Este flujo de trabajo actualiza los KPI de la entrega (indicador de rendimiento clave). By default, it is started every hour.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualizar estado del evento</span><br /> </td> 
   <td> <span class="uicontrol">Updateeventsstatus</span><br /> </td> 
   <td> Este flujo de trabajo le permite atribuir un estado a un evento. The following event statuses are available:<br /> <strong>Pending</strong>: The event is in a queue. Todavía no se ha asignado ninguna plantilla de mensaje.<br /><span class="uicontrol">Entrega</span> pendiente: El evento se encuentra en la cola, se le asigna una plantilla de mensaje y se procesa mediante la entrega.<br /><strong>Enviado</strong>: Este estado se copia desde los registros de entrega. Significa que la entrega se envió.<br /><strong>Omitido por la entrega</strong>: Este estado se copia desde los registros de entrega. Significa que la entrega se ha omitido.<br /><strong>Falló la entrega</strong>: Este estado se copia desde los registros de entrega. Significa que la entrega ha fallado.<br /><span class="uicontrol">Evento no tenido en cuenta</span> : El evento no se pudo vincular a una plantilla de mensaje. The event will not be processed.<br /> </td> 
  </tr> 
  <tr> 
   <td> <span class="uicontrol">Actualización para la entrega</span><br /> </td> 
   <td> <span class="uicontrol">Deliverabilityupdate</span><br /> </td> 
   <td> Este flujo de trabajo permite crear la lista de reglas de calificación de reglas de devoluciones, así como la lista de dominios y MX en la plataforma. Este flujo de trabajo solo funciona si HTTPS está abierto. By default, it is automatically started at 2am.<br /> </td> 
  </tr> 
 </tbody> 
</table>

