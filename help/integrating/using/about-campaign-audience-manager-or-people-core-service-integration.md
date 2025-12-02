---
title: Acerca de la integración de Campaign-Audience Manager o el servicio principal People
description: Con la integración de Audience Manager y el servicio principal Personas, puede compartir audiencias o segmentos dentro de las distintas soluciones de Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e8b96c66-82f7-4adb-88b2-b7e0f7c4a96f
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 20%

---

# Acerca de la integración de Campaign-Audience Manager o el servicio principal People{#about-campaign-audience-manager-or-people-core-service-integration}

>[!CAUTION]
>
>Según los datos intercambiados, la importación de audiencias en Adobe Campaign puede estar sujeta a restricciones legales.

Adobe Campaign le permite intercambiar y compartir audiencias y segmentos con las distintas aplicaciones de Adobe Experience Cloud. La integración de **Adobe Campaign** con **servicio principal Personas** (también conocido como **servicio principal Perfiles y audiencias**) o Adobe Audience Manager le permite:

* Importar audiencias y segmentos de diferentes soluciones de Adobe Experience Cloud en Adobe Campaign. Las audiencias se pueden importar desde el menú **[!UICONTROL Audiences]** en Adobe Campaign.
* Exportar audiencias como audiencias o segmentos compartidos. Estos públicos pueden utilizarse con las diferentes soluciones de Adobe Experience Cloud que utiliza. Las audiencias se pueden exportar después de segmentar actividades en un flujo de trabajo con la actividad **[!UICONTROL Save audience]**.

La integración es compatible con dos tipos de Adobe Experience Cloud ID:

* **ID de visitante**: este tipo de ID le permite reconciliar visitantes de Adobe Experience Cloud con perfiles de Adobe Campaign. Tan pronto como se activa una conexión a través de Adobe IMS, se activa el servicio de ID de visitante de Marketing Cloud, que sustituye a la cookie permanente utilizada por Adobe Campaign. Esto le permite identificar a un visitante y luego vincularlo a un perfil.
  <br>Una ID de visitante está vinculada a un perfil en cuanto este hace clic en un correo electrónico enviado a través de Adobe Campaign:
   * Si el perfil ya tiene un ID de visitante, los datos del explorador del perfil permiten a Adobe Campaign recuperar y vincular automáticamente el perfil al ID de visitante.
   * Si no se encuentra ningún ID de visitante, se crea un nuevo ID. Esta ID de visitante se almacena en los registros de seguimiento de perfil.

  Las otras aplicaciones de Adobe Marketing Cloud reconocen entonces el ID con el mismo CNAME.

* **ID declarado**: este tipo de ID le permite reconciliar cualquier tipo de datos con elementos de la base de datos de Adobe Campaign. Se representa en Adobe Campaign como una clave de reconciliación predefinida. Al intercambiar datos, los identificadores de la base de datos de Adobe Campaign tienen un cifrado hash. A continuación, estos ID con hash se comparan con los ID con hash de la audiencia de Adobe Marketing Cloud implicada en la importación o exportación.
  <br>Esta integración admite identificadores declarados normales, identificadores declarados con hash e ID declarados cifrados.

  >[!NOTE]
  >
  >Ahora, la fuente de datos de ID declarado también se puede utilizar con la integración del servicio principal Personas.
  >
  >Si utiliza la integración del servicio principal Personas y desea añadir la integración de Audience Manager, necesitará la ayuda de un consultor de Adobe Audience Manager para evitar perder todas las sincronizaciones de ID recopiladas al realizar la transición al uso de esta fuente de datos de ID declarados en un contexto de Adobe Audience Manager.


  El cifrado permite compartir datos cifrados en fuentes de datos (por ejemplo, PII) utilizando el ID declarado especificando el algoritmo de cifrado.

  Por ejemplo, con la capacidad de descifrar direcciones de correo electrónico o números SMS cifrados, también puede enviar mensajes activados a los usuarios aunque su perfil no exista en la base de datos de Adobe Campaign.

El diagrama siguiente detalla cómo funciona esta integración. En este caso, AAM significa Adobe Audience Manager y ACS para Adobe Campaign Standard.

![](assets/aam_diagram.png)
