---
title: Desglose por dominios
description: Con el informe predeterminado Desglose por dominios, obtenga información sobre los datos de rendimiento de las entregas en función de cada uno de los dominios del cliente.
audience: reporting
content-type: reference
topic-tags: list-of-reports
context-tags: deliveryDomainBreakdownReport,main;campaignDomainBreakdownReport,main;programDomainBreakdownReport,main
feature: Reporting
role: Leader
level: Intermediate
exl-id: 513d74ae-10c0-4d41-a7d1-8ed655e1a2d1
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Desglose por dominios{#breakdown-by-domains}

Este informe contiene los datos de rendimiento de cada dominio representado en la audiencia de un envío de correo electrónico. Si se trata de un informe de campaña o de programa, los datos de rendimiento están disponibles para varias audiencias. Estos datos le permiten analizar el comportamiento de cada dominio en reacción a eventos específicos. Por ejemplo, visualización de vínculos, dirección URL en la lista de bloqueados de la, etc.

![](assets/delivery_reports_6.png)

La tabla **Estadísticas de difusión** contiene los datos disponibles para los posibles errores encontrados en cada dominio, como:

* **Procesado/enviado**: El número de correos electrónicos enviados.
* **Entregado**: El número de correos electrónicos entregados.
* **Devoluciones + Errores**: El número de mensajes que no se pudieron entregar.
* **Rechazo grave**: El número total de errores permanentes, como una dirección de correo electrónico incorrecta.
* **Devolución suave**: El número total de errores temporales, como una bandeja de entrada completa.

La segunda tabla, **Tracking statistics**, contiene los datos disponibles para la reacción del destinatario a la entrega, como:

* **Entregado**: El número de correos electrónicos entregados
* **Abrir**: El número de veces que se abrió un mensaje en una entrega.
* **Clic**: El número de veces que se hizo clic en el contenido en una entrega.
* **Cancelación de la suscripción**: El número de clics en el vínculo de suscripción.
* **Página espejo**: El número de clics en el vínculo de la página espejo.
* **En la lista de bloqueados de la**: El número de destinatarios que han declarado un correo electrónico como correo no deseado. [Más información](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)
