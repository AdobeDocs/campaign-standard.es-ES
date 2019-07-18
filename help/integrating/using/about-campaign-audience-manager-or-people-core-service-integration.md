---
title: Acerca de la integración de los servicios principales de Campaign-Audience Manager o Personas
seo-title: Acerca de la integración de los servicios principales de Campaign-Audience Manager o Personas
description: Acerca de la integración de los servicios principales de Campaign-Audience Manager o Personas
seo-description: Con la integración del servicio principal de Audience Manager/Personas, puede compartir audiencias o segmentos dentro de las distintas soluciones de Adobe Experience Cloud.
page-status-flag: no activado nunca
uuid: 39 e 3 c 78 e-cccd -4823-afe 9-abc 7 f 8 aef 034
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf 718329-f 181-46 f 7-80 a 2-b 525 a 8 dee 46 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# About Campaign-Audience Manager or People core service integration{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign le permite intercambiar y compartir audiencias o segmentos con las distintas aplicaciones de Adobe Experience Cloud. Integrating **Adobe Campaign** with **People core service** (also known as **Profiles &amp; Audiences core service**) or Adobe Audience Manager allows you to:

* Importar audiencias/segmentos de distintas soluciones de Adobe Experience Cloud en Adobe Campaign. Audiences can be imported from the **[!UICONTROL Audiences]** menu in Adobe Campaign.
* Exportar audiencias como audiencias o segmentos compartidos. Estas audiencias se pueden utilizar en las distintas soluciones de Adobe Experience Cloud que utilice. Audiences can be exported after targeting activities in a workflow, using the **[!UICONTROL Save audience]** activity.

La integración admite dos tipos de ID de Adobe Experience Cloud:

* **ID de visitante**: este tipo de ID permite reconciliar visitantes de Adobe Experience Cloud con perfiles de Adobe Campaign.
* **ID declarado**: este tipo de ID permite reconciliar cualquier tipo de datos con perfiles en la base de datos de Adobe Campaign. Esta integración admite ID declarados regulares, ID declarados con hash y ID declarados cifrados.

   La codificación permite compartir datos cifrados en fuentes de datos (por ejemplo, PII) utilizando el ID declarado especificando el algoritmo de codificación.

   Por ejemplo, con la capacidad de descifrar direcciones de correo electrónico cifradas o números SMS, también puede enviar mensajes activados a los usuarios aunque su perfil no exista en la base de datos de Adobe Campaign.

>[!CAUTION]
>
>Según los datos intercambiados, la importación de audiencias en Adobe Campaign puede estar sujeta a restricciones legales

