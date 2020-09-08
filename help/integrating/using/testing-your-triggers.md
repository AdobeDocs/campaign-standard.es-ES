---
title: Prueba de los activadores
description: null
page-status-flag: never-activated
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 2%

---


# Prueba de los activadores{#testing-your-triggers}

Las siguientes sugerencias para la solución de problemas le ayudarán a resolver los problemas más comunes que puede encontrar al utilizar Triggers con Adobe Campaign:

**¿Está activada la funcionalidad?**

Para comprobar si la integración Desencadenadores - Campaña está activada, haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]**. Deberías ver el **[!UICONTROL Experience Cloud Triggers]** elemento.

Si lo ve, continúe con el siguiente paso.

Si no es así, póngase en contacto con el ejecutivo de su cuenta de Adobe o con un socio de servicios profesionales. Consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un activador**

Siga los pasos descritos en [Creación de un activador asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para crear un activador.

Si se crea el activador, continúe con el paso siguiente. Si no es así, significa que la conexión del punto final del activador ha fallado. Compruebe si Triggers está aprovisionado en Experience Cloud (servicios de Activación). Si no es así, póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe. Se requiere la siguiente información:

* Nombre de Compañía de Marketing Cloud
* ID de la organización IMS
* Compañía de inicio de sesión de Analytics (puede ser la misma que el nombre de Compañía de Marketing Cloud)

**Intente publicar el activador**

Siga los pasos descritos en [Creación de un activador asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar el activador.

Si la publicación se ha realizado correctamente, continúe con el paso siguiente. Si no es así, póngase en contacto con Adobe para reiniciar la instancia y volver a intentarlo.

**Generar el activador desde el sitio web**

Siga los pasos descritos en [Edición de la Plantilla de mensaje transaccional](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) para editar y publicar la plantilla transaccional. A continuación, pruebe la generación del activador desde el sitio web.

Si Analytics recibe el activador, continúe con el paso siguiente. Si no es así, compruebe los siguientes elementos:

* Activador habilitado para Analytics
* El sitio web utilizado MCID y Analytics está habilitado en la DTM
* Se utiliza el grupo de informes correcto de Analytics al crear activadores

**¿Recibe la Campaña el activador?**

En caso contrario, compruebe si el activador se recibe de la canalización.

Si no es así, póngase en contacto con Adobe para comprobar la configuración de los puntos finales de la tubería.

Si es así, siga estas líneas de guía:

* Compruebe el tipo de ID de reconciliación en el origen de datos de la Campaña.
* El origen de datos CustomerId se crea mediante Atributos del cliente.
* Compruebe el ID de la fuente de datos.
* Pida a Adobe que reinicie la instancia de Campaña después de la configuración del origen de datos.
* Compruebe los problemas de análisis de activadores en el informe de activadores.

**¿El activador está en estado pendiente?**

Si no es así, continúe con el paso siguiente. Si es así, siga estas líneas de guía:

* Compruebe que la plantilla de transacción está publicada.
* Compruebe que el perfil no está incluida en la lista de bloqueados.
* Compruebe la aplicación de reglas de tipología.
* Compruebe los registros del mensaje transaccional.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para activar campos de personalización de enriquecimiento marcados como no válidos, valide la plantilla transaccional de las colecciones eventCusResource asociadas.
* Validar el formato del mensaje

