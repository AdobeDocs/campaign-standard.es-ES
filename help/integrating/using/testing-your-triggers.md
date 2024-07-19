---
title: Prueba de los activadores
description: Obtenga información sobre sugerencias de solución de problemas para ayudarle a solucionar los problemas más comunes que puede encontrar al usar Déclencheur con Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: 602878233e919d01f3972167cb6d3a1acc4cfc02
workflow-type: tm+mt
source-wordcount: '460'
ht-degree: 1%

---

# Prueba de los activadores{#testing-your-triggers}

Las siguientes sugerencias para la resolución de problemas le ayudan a solucionar los problemas más comunes que puede encontrar al utilizar Déclencheur con Adobe Campaign:

**¿Está activada la funcionalidad?**

Para comprobar si la integración Déclencheur - Campaign está activada, haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Debería ver el elemento **[!UICONTROL Experience Cloud Triggers]**.

Si lo ve, continúe con el siguiente paso.

Si no es así, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. Consulte [Activar la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un déclencheur**

Siga los pasos que se describen en [Creación de un déclencheur asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para crear un déclencheur.

Si se crea el déclencheur, continúe con el paso siguiente. Si no es así, significa que la conexión de punto final de déclencheur ha fallado. Compruebe si Déclencheur está aprovisionado en Experience Cloud (servicios de activación). Si no es así, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. Se requiere la siguiente información:

* Nombre de empresa de Marketing Cloud
* ID de la organización
* Empresa de inicio de sesión de Analytics (puede ser la misma que el nombre de empresa de Marketing Cloud)

**Intente publicar el déclencheur**

Siga los pasos que se describen en [Creación de un déclencheur asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar el déclencheur.

Si la publicación se ha realizado correctamente, continúe con el paso siguiente. Si no es así, póngase en contacto con el Adobe de para reiniciar la instancia e inténtelo de nuevo.

**Generar el déclencheur desde el sitio web**

Siga los pasos descritos en [Edición de la plantilla de mensaje transaccional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar y publicar la plantilla transaccional. A continuación, pruebe la generación del déclencheur desde el sitio web.

Si Analytics recibe el déclencheur, continúe con el paso siguiente. Si no es así, compruebe lo siguiente:

* El déclencheur está habilitado para Analytics
* El sitio web utilizado por MCID y Analytics está habilitado en DTM
* Se utiliza el grupo de informes correcto de Analytics al crear déclencheur

**¿El déclencheur se ha recibido en Campaign?**

Si no es así, compruebe si el déclencheur se recibe de la canalización.

Si no es así, póngase en contacto con el Adobe de para comprobar la configuración de los puntos finales de la canalización.

Si es así, siga estas directrices:

* Compruebe el tipo de ID de reconciliación en la fuente de datos de Campaign.
* CustomerId Datasource se crea mediante Atributos del cliente.
* Compruebe el ID de origen de datos.
* Pida al Adobe que reinicie la instancia de Campaign después de la configuración de Datasource.
* Consulte los problemas de análisis de déclencheur en el informe de déclencheur.

**¿Está el déclencheur en estado pendiente?**

Si no es así, continúe con el paso siguiente. Si es así, siga estas directrices:

* Compruebe que la plantilla transaccional esté publicada.
* Compruebe que el perfil no esté en la lista de bloqueados de la.
* Compruebe la aplicación de las reglas de tipología.
* Compruebe los registros del mensaje transaccional.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para los campos personalizados de enriquecimiento de déclencheur marcados como no válidos, valide la plantilla transaccional de las colecciones eventCusResource asociadas.
* Validación del formato del mensaje
