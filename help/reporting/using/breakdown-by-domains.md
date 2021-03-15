---
solution: Campaign Standard
product: campaign
title: Desglose por dominios
description: Con el informe Desglose por dominios integrado, obtenga información sobre los datos de rendimiento de los envíos en función de cada dominio del cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Creación de informes
role: Encabezado
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 3%

---


# Desglose por dominios{#breakdown-by-domains}

Este informe contiene los datos de rendimiento de cada dominio representado en la audiencia para una entrega de correo electrónico. Si se trata de un informe de campaña o programa, los datos de rendimiento están disponibles para varias audiencias. Estos datos le permiten analizar el comportamiento de cada dominio en respuesta a eventos específicos. Por ejemplo, visualización de vínculos, dirección URL en lista de bloqueados, etc.

![](assets/delivery_reports_6.png)

La tabla **Broadcast statistics** contiene los datos disponibles para detectar posibles errores encontrados con cada dominio, como:

* **Procesado/enviado**: Número de correos electrónicos enviados.
* **Entrega**: Número de correos electrónicos enviados.
* **Devoluciones + Errores**: Número de mensajes que no se pudieron enviar.
* **Rechazo** grave: El número total de errores permanentes, como una dirección de correo electrónico incorrecta.
* **Rechazo** leve: El número total de errores temporales, como una bandeja de entrada completa.

La segunda tabla, **Tracking statistics**, contiene los datos disponibles para la reacción del destinatario al envío, como:

* **Entrega**: El número de correos electrónicos enviados
* **Abrir**: Número de veces que se abrió un mensaje en una entrega.
* **Haga clic en**: Número de veces que se hizo clic en el contenido en una entrega.
* **Cancelación de suscripción**: El número de clics en el vínculo de suscripción.
* **Página espejo**: El número de clics en el vínculo de la página espejo.
* **Al lista de bloqueados**: El número de destinatarios que han declarado un correo electrónico como correo no deseado o no deseado. [Obtenga más información](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

