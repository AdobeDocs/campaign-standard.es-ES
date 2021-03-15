---
solution: Campaign Standard
product: campaign
title: Acerca de la integración de Campaign con Audience Manager o el servicio principal People
description: Con la integración Audience Manager/servicio principal People, puede compartir audiencias o segmentos dentro de las distintas soluciones de Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 10%

---


# Acerca de la integración de Campaign con Audience Manager o el servicio principal People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Según los datos intercambiados, la importación de audiencias en Adobe Campaign puede estar sujeta a restricciones legales.

Adobe Campaign le permite intercambiar y compartir audiencias y segmentos con las distintas aplicaciones de Adobe Experience Cloud. La integración de **Adobe Campaign** con **el servicio principal Personas** (también conocido como **Servicio principal de Perfiles y audiencias**) o Adobe Audience Manager le permite:

* Importar audiencias y segmentos de distintas soluciones de Adobe Experience Cloud en Adobe Campaign. Las audiencias se pueden importar desde el menú **[!UICONTROL Audiences]** en Adobe Campaign.
* Exportar audiencias como audiencias o segmentos compartidos. Estas audiencias pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. Las audiencias se pueden exportar después de actividades de segmentación en un flujo de trabajo mediante la actividad **[!UICONTROL Save audience]**.

La integración admite dos tipos de Adobe Experience Cloud ID:

* **ID** de visitante: este tipo de ID le permite reconciliar visitantes de Adobe Experience Cloud con perfiles de Adobe Campaign. Tan pronto como se activa una conexión mediante IMS de Adobe, se activa el servicio ID de visitante de Marketing Cloud, que sustituye la cookie permanente utilizada por Adobe Campaign. Esto le permite identificar a un visitante y luego vincularlo a un perfil.
   <br>Un ID de visitante está vinculado a un perfil en cuanto este hace clic en un correo electrónico enviado por Adobe Campaign:
   * Si el perfil ya tiene un ID de visitante, los datos del explorador del perfil permiten a Adobe Campaign recuperarse y vincular automáticamente el perfil al ID de visitante.
   * Si no se encuentra ningún ID de visitante, se crea un nuevo ID. Este ID de visitante se almacena en los registros de seguimiento de perfil.

   Las otras aplicaciones de Adobe Marketing Cloud reconocen entonces la ID con el mismo CNAME.

* **ID** declarado: este tipo de ID le permite reconciliar cualquier tipo de datos con elementos de la base de datos de Adobe Campaign. Se representa en Adobe Campaign como una clave de conciliación predefinida. Al intercambiar datos, los identificadores de la base de datos de Adobe Campaign se colocan en hash. A continuación, estos ID con hash se comparan con los ID con hash de la audiencia de Adobe Marketing Cloud implicada en la importación o exportación.
   <br>Esta integración admite ID declarados normales, ID declarados con hash e ID declarados cifrados.

   >[!CAUTION]
   >
   >El ID declarado solo funcionará con Adobe Audience Manager. El ID declarado no funcionará sin él.

   La codificación le permite compartir datos cifrados en fuentes de datos (por ejemplo, PII) mediante el ID declarado especificando el algoritmo de codificación.

   Por ejemplo, con la capacidad de descifrar direcciones de correo electrónico o números SMS cifrados, también puede enviar mensajes activados a los usuarios aunque su perfil no exista en la base de datos de Adobe Campaign.

El diagrama siguiente detalla cómo funciona esta integración. En este caso, AAM significa Adobe Audience Manager y ACS para Adobe Campaign Standard.

![](assets/aam_diagram.png)