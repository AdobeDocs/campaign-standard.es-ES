---
title: Prueba de los activadores
description: null
page-status-flag: nunca activado
uuid: b3a6667d-e843-4ad6-817e-d91542b5f2e2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y activadores
discoiquuid: f67e69f2-09fb-4f33-b2c3-c67a060743e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Prueba de los activadores{#testing-your-triggers}

Las siguientes sugerencias para la resolución de problemas le ayudarán a resolver los problemas más comunes que puede encontrar al utilizar activadores con Adobe Campaign:

**¿Está activada la funcionalidad?**

Para comprobar si la integración Desencadenadores - Campaña está activada, haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda, y seleccione **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. Deberías ver el **[!UICONTROL Experience Cloud Triggers]** elemento.

Si lo ve, continúe con el siguiente paso.

Si no es así, póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe. Consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un activador**

Siga los pasos descritos en [Creación de un activador asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para crear un activador.

Si se crea el activador, continúe con el paso siguiente. De lo contrario, significa que la conexión del punto final del activador ha fallado. Compruebe si Triggers está aprovisionado en Experience Cloud (servicios de activación). Si no es así, póngase en contacto con el ejecutivo o el socio de servicios profesionales de su cuenta de Adobe. Se requiere la siguiente información:

* Nombre de empresa de Marketing Cloud
* ID DE ORIGEN DE IMS
* Empresa de inicio de sesión de Analytics (puede ser igual que el nombre de la empresa de Marketing Cloud)

**Intente publicar el activador**

Siga los pasos descritos en [Creación de un activador asignado en Campaña](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) para publicar el activador.

Si la publicación se ha realizado correctamente, continúe con el paso siguiente. Si no es así, póngase en contacto con Adobe para reiniciar la instancia e inténtelo de nuevo.

**Generar el activador desde el sitio web**

Siga los pasos descritos en [Edición de la plantilla](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) de mensaje transaccional para editar y publicar la plantilla transaccional. A continuación, pruebe la generación del activador desde el sitio web.

Si Analytics recibe el activador, continúe con el paso siguiente. En caso contrario, compruebe los siguientes elementos:

* Activador habilitado para Analytics
* El sitio web utilizado MCID y Analytics está habilitado en la DTM
* Se utiliza el grupo de informes correcto de Analytics al crear activadores

**¿La campaña recibe el activador?**

En caso contrario, compruebe si el activador se recibe de la canalización.

Si no es así, póngase en contacto con Adobe para comprobar la configuración de los puntos finales de la canalización.

Si es así, siga estas líneas de guía:

* Compruebe el tipo de ID de reconciliación en el origen de datos de campaña.
* El origen de datos CustomerId se crea mediante Atributos del cliente.
* Compruebe el ID de la fuente de datos.
* Pida a Adobe que reinicie la instancia de Campaign después de la configuración del origen de datos.
* Compruebe los problemas de análisis de activadores en el informe de activadores.

**¿El activador está en estado pendiente?**

Si no es así, continúe con el paso siguiente. Si es así, siga estas líneas de guía:

* Compruebe que la plantilla de transacción está publicada.
* Si el umbral propensityScore está habilitado para Campaign, compruebe la puntuación de tendencia del activador en la canalización.
* Compruebe que el perfil no esté bloqueado.
* Compruebe la aplicación de las reglas de tipología.
* Compruebe los registros del mensaje transaccional.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para activar campos de personalización de enriquecimiento marcados como no válidos, valide la plantilla transaccional de las colecciones eventCusResource asociadas.
* Validar el formato del mensaje

