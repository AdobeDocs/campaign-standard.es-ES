---
title: Prueba de los activadores
description: Conozca las sugerencias para la solución de problemas que le ayudarán a solucionar los problemas más comunes que puede encontrar al usar Déclencheur con Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 66628f2a-6ed3-4b12-b2ed-9b9eec440dc3
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 1%

---

# Prueba de los activadores{#testing-your-triggers}

Las siguientes sugerencias para la solución de problemas le ayudan a resolver los problemas más comunes que puede encontrar al usar Déclencheur con Adobe Campaign:

**¿Está activada la funcionalidad?**

Para comprobar si la integración de Déclencheur - Campaign está activada, haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Debería ver el elemento **[!UICONTROL Experience Cloud Triggers]**.

Si lo ve, continúe con el siguiente paso.

Si no es así, póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe. Consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un déclencheur**

Siga los pasos descritos en [Creación de un déclencheur asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para crear un déclencheur.

Si se crea el déclencheur, continúe con el siguiente paso. Si no es así, significa que la conexión del punto final del déclencheur ha fallado. Compruebe si Déclencheur está aprovisionado en Experience Cloud (servicios de activación). Si no es así, póngase en contacto con el ejecutivo de su cuenta de Adobe o con el socio de servicios profesionales. Se requiere la siguiente información:

* Nombre de la empresa del Marketing Cloud
* ID de la organización IMS
* Empresa de inicio de sesión de Analytics (puede ser el mismo que el nombre de la empresa de Marketing Cloud)

**Intente publicar el déclencheur**

Siga los pasos descritos en [Creación de un déclencheur asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar el déclencheur.

Si la publicación se ha realizado correctamente, continúe con el siguiente paso. Si no es así, póngase en contacto con Adobe para reiniciar la instancia e inténtelo de nuevo.

**Generar el déclencheur desde el sitio web**

Siga los pasos descritos en [Edición de la plantilla de mensaje transaccional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar y publicar la plantilla transaccional. A continuación, pruebe la generación del déclencheur desde el sitio web.

Si Analytics recibe el déclencheur, continúe con el siguiente paso. Si no es así, compruebe los siguientes elementos:

* Déclencheur habilitado para Analytics
* El sitio web utilizado MCID y Analytics está habilitado en la DTM
* Se utiliza el grupo de informes correcto de Analytics al crear déclencheur

**¿Campaign recibe el déclencheur?**

Si no es así, compruebe si el déclencheur se recibe de la canalización.

Si no es así, póngase en contacto con Adobe para comprobar la configuración de los puntos finales de la canalización.

Si es así, siga estas directrices:

* Compruebe el tipo de ID de reconciliación en la fuente de datos de Campaign.
* La fuente de datos de CustomerId se crea mediante Atributos del cliente.
* Compruebe el ID de la fuente de datos.
* Solicite a Adobe que reinicie la instancia de Campaign después de la configuración de la Fuente de datos.
* Compruebe los problemas de análisis de déclencheur en el informe de déclencheur.

**¿El déclencheur está en estado pendiente?**

Si no es así, continúe con el siguiente paso. Si es así, siga estas directrices:

* Compruebe que la plantilla transaccional esté publicada.
* Compruebe que el perfil no esté en lista de bloqueados.
* Compruebe la aplicación de las reglas de tipología.
* Compruebe los registros del mensaje transaccional.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para los campos personalizados de enriquecimiento de déclencheur marcados como no válidos, valide la plantilla transaccional de las colecciones eventCusResource asociadas.
* Validar el formato del mensaje
