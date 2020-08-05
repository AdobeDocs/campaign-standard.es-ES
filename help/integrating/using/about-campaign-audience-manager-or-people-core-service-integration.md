---
title: Acerca de la integración de Campaign con Audience Manager o el servicio principal People
description: Con la integración de servicios principales Audience Manager/Personas, puede compartir audiencias o segmentos dentro de las distintas soluciones de Adobe Experience Cloud.
page-status-flag: never-activated
uuid: 39e3c78e-cccd-4823-afe9-abc7f8aef034
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: bf718329-f181-46f7-80a2-b525a8dee46d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e790f550f6eb84954f199caeda88a8fd90dfd85
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 8%

---


# Acerca de la integración de Campaign con Audience Manager o el servicio principal People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Según los datos intercambiados, la importación de audiencias en Adobe Campaign puede estar sujeta a restricciones legales.

Adobe Campaign le permite intercambiar y compartir audiencias/segmentos con las distintas aplicaciones de Adobe Experience Cloud. La integración de **Adobe Campaign** con el servicio **principal** Personas (también conocido como servicio **principal de** Perfiles y Audiencias) o Adobe Audience Manager le permite:

* Importe audiencias/segmentos de diferentes soluciones de Adobe Experience Cloud en Adobe Campaign. Las Audiencias se pueden importar desde el **[!UICONTROL Audiences]** menú en Adobe Campaign.
* Exportar audiencias como audiencias o segmentos compartidos. Estas audiencias pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. Las Audiencias se pueden exportar después de segmentar actividades en un flujo de trabajo mediante la **[!UICONTROL Save audience]** actividad.

La integración admite dos tipos de Adobe Experience Cloud ID:

* **ID**de Visitante: este tipo de ID le permite reconciliar visitantes de Adobe Experience Cloud con perfiles de Adobe Campaign. Tan pronto como se habilita una conexión mediante IMS de Adobe, se activa el servicio de ID de Visitante de Marketing Cloud, que sustituye a la cookie permanente utilizada por Adobe Campaign. Esto le permite identificar un visitante y luego vincularlo a un perfil.
   <br>Un ID de visitante se vincula a un perfil en cuanto el perfil hace clic en un mensaje de correo electrónico enviado por Adobe Campaign:
   * Si el perfil ya tiene un ID de visitante, los datos del navegador del perfil permiten que Adobe Campaign se recupere y vincule automáticamente el perfil al ID de visitante.
   * Si no se encuentra ningún ID de visitante, se crea un nuevo ID. Este ID de visitante se almacena en los registros de seguimiento de perfil.

   El ID será reconocido por las demás aplicaciones de Adobe Marketing Cloud con el mismo CNAME.

* **ID**declarado: este tipo de ID permite reconciliar cualquier tipo de datos con elementos de la base de datos de Adobe Campaign. Se representa en Adobe Campaign como una clave de conciliación predefinida. Al intercambiar datos, los identificadores de la base de datos de Adobe Campaign tienen hash. A continuación, estos ID con hash se comparan con los ID con hash de la audiencia de Adobe Marketing Cloud implicada en la importación o exportación.
   <br>Esta integración admite ID declarados normales, ID declarados con hash e ID declarados cifrados.

   >[!CAUTION]
   >
   >El ID declarado solo funcionará con Adobe Audience Manager. El ID declarado no funcionará sin él.

   El cifrado le permite compartir datos cifrados en fuentes de datos (por ejemplo, PII) mediante el uso del ID declarado especificando el algoritmo de codificación.

   Por ejemplo, con la capacidad de descifrar direcciones de correo electrónico cifradas o números SMS, también puede enviar mensajes activados a sus usuarios aunque su perfil no exista en la base de datos de Adobe Campaign.

El diagrama siguiente detalla cómo funciona esta integración. Aquí, AAM significa Adobe Audience Manager et ACS para Adobe Campaign Standard.

![](assets/aam_diagram.png)