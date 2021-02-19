---
solution: Campaign Standard
product: campaign
title: Prueba de los activadores
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 2%

---


# Prueba de los activadores{#testing-your-triggers}

Las siguientes sugerencias de solución de problemas le ayudarán a resolver los problemas más comunes que puede encontrar al usar Déclencheur con Adobe Campaign:

**¿Está activada la funcionalidad?**

Para comprobar si la integración de Déclencheur - Campaña está activada, haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda, luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Debería ver el elemento **[!UICONTROL Experience Cloud Triggers]**.

Si lo ve, continúe con el siguiente paso.

Si no es así, póngase en contacto con el ejecutivo de su cuenta de Adobe o con un socio de servicios profesionales. Consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un déclencheur**

Siga los pasos descritos en [Creación de un déclencheur asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para crear un déclencheur.

Si se crea el déclencheur, continúe con el paso siguiente. Si no es así, significa que la conexión del punto final del déclencheur ha fallado. Compruebe si los Déclencheur están aprovisionados en Experience Cloud (servicios de Activación). Si no es así, póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe. Se requiere la siguiente información:

* Nombre de Compañía de Marketing Cloud
* ID de la organización IMS
* Compañía de inicio de sesión de Analytics (puede ser la misma que el nombre de Compañía de Marketing Cloud)

**Intente publicar el déclencheur**

Siga los pasos descritos en [Creación de un déclencheur asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar el déclencheur.

Si la publicación se ha realizado correctamente, continúe con el paso siguiente. Si no es así, póngase en contacto con Adobe para reiniciar la instancia y volver a intentarlo.

**Generar el déclencheur desde el sitio web**

Siga los pasos descritos en [Edición de la Plantilla de mensaje transaccional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar y publicar la plantilla transaccional. A continuación, pruebe la generación del déclencheur desde el sitio web.

Si Analytics recibe el déclencheur, continúe con el paso siguiente. Si no es así, compruebe los siguientes elementos:

* Déclencheur habilitado para Analytics
* El sitio web utilizado MCID y Analytics está habilitado en la DTM
* Se utiliza el grupo de informes correcto de Analytics al crear déclencheur

**¿Recibe la Campaña el déclencheur?**

En caso contrario, compruebe si el déclencheur se recibe de la canalización.

Si no es así, póngase en contacto con Adobe para comprobar la configuración de los puntos finales de la tubería.

En caso afirmativo, siga estas directrices:

* Compruebe el tipo de ID de reconciliación en el origen de datos de la Campaña.
* El origen de datos CustomerId se crea mediante Atributos del cliente.
* Compruebe el ID de la fuente de datos.
* Pida a Adobe que reinicie la instancia de Campaña después de la configuración del origen de datos.
* Compruebe los problemas de análisis de déclencheur en el informe déclencheur.

**¿Está el déclencheur en estado pendiente?**

Si no es así, continúe con el paso siguiente. En caso afirmativo, siga estas directrices:

* Compruebe que la plantilla de transacción está publicada.
* Compruebe que el perfil no está en lista de bloqueados.
* Compruebe la aplicación de reglas de tipología.
* Compruebe los registros del mensaje transaccional.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para campos de personalización de enriquecimiento de déclencheur marcados como no válidos, valide la plantilla transaccional de las colecciones eventCusResource asociadas.
* Validar el formato del mensaje

