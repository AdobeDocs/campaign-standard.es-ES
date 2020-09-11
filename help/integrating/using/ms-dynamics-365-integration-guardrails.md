---
title: Barreras de protección de integración de Microsoft Dynamics 365
description: Microsoft Dynamics 365 con protecciones de integración Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd1cbf907eb160b6bbc1a2a2d3dd1c601ac13635
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 0%

---


# Guardias y límites de integración

## Guardias de integración

Al planificar el uso de esta integración, deben tenerse en cuenta las siguientes barreras. Consulte con el representante técnico de su Adobe si cree que excede estas protecciones.

* Deberá obtener una licencia del paquete de Campaña adecuado para admitir el volumen de llamadas del motor ACS generado por la integración. Exceder el volumen de llamadas al motor con licencia podría causar una degradación en el rendimiento de la Campaña.

   Utilice lo siguiente para ayudarle a calcular el volumen de llamadas del motor a partir de la integración:

   * Inserciones de registros (es decir, nuevo registro): 1 llamada al motor
   * El registro elimina: 1 llamada al motor
   * Actualizaciones de registros: 2 llamadas de motor (sólo 1 llamada si el registro de destino es idéntico al registro de origen, es decir, si no se modifica el registro ACS)

   Al calcular el volumen de llamadas del motor ACS en general, es importante tener en cuenta otras fuentes de llamadas del motor, como páginas de aterrizaje, WebApps, JSSP, API, registros de aplicaciones móviles, etc.

   Información del paquete de Campaña de vista aquí: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* La integración admite un máximo de 30 millones de contactos.

* La oferta de integración estándar incluye compatibilidad con hasta cinco entidades personalizadas

* Las entidades personalizadas con más de 500.000 registros necesitarán horas de consulta adicionales para realizar una importación inicial basada en archivos única (por entidad personalizada) mediante el flujo de trabajo de Campaña (lo que conlleva un coste adicional)

* La oferta de integración estándar incluye compatibilidad con entidades personalizadas de hasta 50 columnas de tamaño.

* Deberá crear y publicar sus recursos personalizados antes de implementar la integración.

* La profundidad máxima de tabla al enlazar tablas es de dos (por ejemplo: tabla1->tabla2->tabla3)

* La compatibilidad con los tipos de datos de Dynamic 365 es limitada. Si el modelo de datos contiene un tipo de datos distinto de los tipos de datos simples (por ejemplo, cadenas, enteros, decimales, etc.), es posible que tenga que actualizar el modelo de datos antes de utilizar la integración.

* La conservación de los datos existentes en las entidades personalizadas de Campaña puede acarrear costes de consultoría adicionales para preparar los datos para la integración.

* Es posible que sea necesario establecer ventanillas de mantenimiento integradas entre el Adobe y el cliente, ya que la ingesta inicial puede causar una desaceleración de la Campaña.

* Se le recomienda que comunique instancias conocidas de aumento significativo o &quot;picos&quot; en el uso de la integración (por ejemplo, un aumento brusco de los registros nuevos o actualizados), ya que esto podría causar desaceleraciones en la sincronización de datos.

* Como parte de la integración, se espera que complete los pasos de configuración previos a la integración en Microsoft Azure y Dynamics 365. Consulte los pasos de configuración [en esta página](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

* Se espera que traiga los modelos de datos de Dynamics 365 y Campaña a la integración y que los mantenga.

## Límites de integración

La integración se diseñó para resolver el caso de uso general del movimiento de datos común entre Dynamics 365 y Campaña, pero no se pretende abordar todos los casos de uso específicos de cada cliente:

* La integración no emite ninguna eliminación de privacidad (por ejemplo, RGPD). La responsabilidad de cumplir las solicitudes de privacidad de los usuarios finales recae en el cliente; estas solicitudes deben realizarse en Campaña (a través de Adobe Experience Platform Privacy Service) y Dynamics 365 de forma independiente. Si lo desea, la integración puede generar eliminaciones regulares para facilitar la sincronización de datos.

* No se sincronizarán datos de perfiles ni de entidades personalizadas de la Campaña a Dynamics 365, a excepción de la información de exclusión (si la configura el cliente).

* La administración de suscripciones de campaña (es decir, suscripciones/cancelaciones de suscripción) no es compatible de forma nativa.

* No se admite la composición y activación de campañas de correo electrónico de Campaña desde Dynamics 365.

* La integración no admitirá la remodelación de datos entre los modelos de datos de Dynamics 365 y Campaña. Se espera que la integración sincronice una tabla de Dynamics 365 con una tabla de Campaña.

* No hay una interfaz de usuario de autoservicio con la versión actual de la integración.
