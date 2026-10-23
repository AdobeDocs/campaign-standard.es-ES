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
TQID: 'https://experienceleague.adobe.com/25Ci4GFEJHIO3Ed2BTBF2qUmD4LKh3jwUC56K8JZgzA'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '238'
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
