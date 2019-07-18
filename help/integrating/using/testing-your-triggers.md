---
title: Prueba de los activadores
seo-title: Prueba de los activadores
description: Prueba de los activadores
seo-description: null
page-status-flag: no activado nunca
uuid: b 3 a 6667 d-e 843-4 ad 6-817 e-d 91542 b 5 f 2 e 2
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y activadores
discoiquuid: f 67 e 69 f 2-09 fb -4 f 33-b 2 c 3-c 67 a 060743 e 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Testing your triggers{#testing-your-triggers}

Las siguientes sugerencias para solucionar problemas le ayudarán a resolver los problemas más comunes que puede encontrar al utilizar Activadores con Adobe Campaign:

**¿Se activa la funcionalidad?**

To check if the Triggers - Campaign integration is activated, click the Adobe Campaign logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]**. You should see the **[!UICONTROL Experience Cloud Triggers]** item.

Si lo ve, vaya al paso siguiente.

Si no es así, póngase en contacto con su ejecutivo de cuentas de Adobe o con su socio de servicios profesionales. See [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality).

**Intente crear un activador**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to create a trigger.

Si se crea el activador, vaya al paso siguiente. Si no es así, significa que la conexión de punto final de desencadenador falló. Compruebe si Activadores está aprovisionado en Experience Cloud (servicios de activación). Si no lo hace, póngase en contacto con su administrador de cuentas de Adobe o con su socio de servicios profesionales. Se requiere la siguiente información:

* Nombre de empresa de Marketing Cloud
* ID de organización IMS
* Empresa de inicio de sesión de Analytics (puede ser igual que el nombre de empresa de Marketing Cloud)

**Intente publicar el activador**

Follow the steps described in [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) to publish the trigger.

Si la publicación se realiza correctamente, pase al paso siguiente. Si no, póngase en contacto con Adobe para reiniciar la instancia e inténtelo de nuevo.

**Generar el activador desde el sitio web**

Follow the steps described in [Editing the transactional message template](../../integrating/using/using-triggers-in-campaign.md#editing-the-transactional-message-template) to edit and publish the transactional template. A continuación, pruebe la generación del activador desde el sitio web.

Si Analytics recibe el activador, continúe con el paso siguiente. De lo contrario, compruebe los siguientes elementos:

* Activador habilitado para Analytics
* El sitio web utilizado MCID y Analytics está habilitado en la DTM
* El grupo de informes correcto de Analytics se usa al crear activadores

**¿El activador recibido por campaña?**

Si no es así, compruebe si el activador se recibe desde el canal.

Si no es así, póngase en contacto con Adobe para comprobar la configuración de los puntos finales del canal.

Si es así, siga estas líneas de guía:

* Compruebe el tipo de ID de reconciliación en la fuente de datos de campaña.
* La fuente de datos customerid se crea mediante Atributos del cliente.
* Compruebe el ID de fuente de datos.
* Pida a Adobe que reinicie la instancia de campaña después de la configuración de fuente de datos.
* Compruebe los problemas de análisis activador en el informe desencadenador.

**¿El activador está en estado pendiente?**

Si no es así, pase al paso siguiente. Si es así, siga estas líneas de guía:

* Compruebe que la plantilla transaccional esté publicada.
* Si el umbral propensityscore está habilitado para Campaign, compruebe la puntuación de propensión del activador desde la cartera.
* Compruebe que el perfil no está bloqueado.
* Compruebe la aplicación de las reglas de tipología.
* Compruebe los registros del mensaje de transacción.

**¿Es válido el mensaje?**

Si el mensaje no es válido, compruebe los siguientes elementos:

* Para activar los campos de personalización de enriquecimiento marcados como no válidos, valide la plantilla transaccional desde las colecciones eventcusresource asociadas.
* Validación del formato de mensaje

