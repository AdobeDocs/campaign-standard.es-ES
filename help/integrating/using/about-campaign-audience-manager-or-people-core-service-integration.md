---
title: Acerca de Campaign-Audience Manager o la integración de servicio principal Personas
seo-title: Acerca de Campaign-Audience Manager o la integración de servicio principal Personas
description: Acerca de Campaign-Audience Manager o la integración de servicio principal Personas
seo-description: Con la integración del servicio principal Audience Manager/Personas, puede compartir audiencias o segmentos dentro de las distintas soluciones de Adobe Experience Cloud.
page-status-flag: nunca activado
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: servicio de trabajo con campaña y audiencia-administrador-o-personas-núcleo
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f54c92b92524e2966aa8c1c8497c8a7dff1bcf9

---


# Acerca de Campaign-Audience Manager o la integración de servicio principal Personas{#about-campaign-audience-manager-or-people-core-service-integration}

Adobe Campaign permite intercambiar y compartir audiencias/segmentos con las distintas aplicaciones de Adobe Experience Cloud. La integración de **Adobe Campaign** con el servicio **principal** Personas (también conocido como servicio **principal** Profiles &amp; Audiences) o Adobe Audience Manager le permite:

* Importe audiencias/segmentos de distintas soluciones de Adobe Experience Cloud en Adobe Campaign. Las audiencias se pueden importar desde el **[!UICONTROL Audiences]** menú en Adobe Campaign.
* Exportar audiencias como audiencias o segmentos compartidos. Estas audiencias pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud
          que utiliza. Las audiencias se pueden exportar después de segmentar actividades en un flujo de trabajo, mediante la **[!UICONTROL Save audience]** actividad.

La integración admite dos tipos de Adobe Experience Cloud ID:

* **ID** del visitante: este tipo de ID le permite reconciliar a los visitantes de Adobe Experience Cloud con los perfiles de Adobe Campaign.
* **ID** declarado: este tipo de ID permite reconciliar cualquier tipo de datos con perfiles en la base de datos de Adobe Campaign. Esta integración admite ID declarados normales, ID declarados con hash e ID declarados cifrados. Para **[!UICONTROL Declared ID]** su validez, consulte esta [página](../../integrating/using/provisioning-and-configuring-integration-with-audience-manager-or-people-core-service.md).

   El cifrado le permite compartir datos cifrados en fuentes de datos (por ejemplo, PII) mediante el uso del ID declarado especificando el algoritmo de codificación.

   Por ejemplo, con la capacidad de descifrar direcciones de correo electrónico cifradas o números SMS, también puede enviar mensajes activados a sus usuarios aunque su perfil no exista en la base de datos de Adobe Campaign.

>[!CAUTION]
>
>Según los datos intercambiados, la importación de audiencias en Adobe Campaign puede estar sujeta a restricciones legales

