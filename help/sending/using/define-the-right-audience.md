---
title: Definición del público correcto
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: true
description: Cuando tenga preparado el contenido, aprenda a definir cuidadosamente quién recibirá el mensaje.
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
TQID: 'https://experienceleague.adobe.com/keRwWGnvoXbhg4XhReRZzSF1L9x93BbNu8YhBWtUoNM'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
    internal-label: Campaigns
  - id: 63876777-85c3-57e1-a2da-81f02956c63c
    internal-label: Deliverability
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 74%
---
# Definición del público correcto {#define-the-right-audience}

La población objetivo es clave: cree sus listas con cuidado, pruebe sus correos electrónicos con clientes de correo electrónico y dispositivos móviles populares, y asegúrese de que sus listas de correos electrónicos estén actualizadas (sin direcciones desconocidas u obsoletas). También puede enviar pruebas que ayuden a configurar un ciclo de validación completo.

Aprenda más sobre las poblaciones objetivo [en esta sección](../../audiences/using/selecting-an-audience-in-a-message.md)

## Selección del público destinatario correcto {#target-the-right-audience}

Cuando tenga preparado el contenido, debe definir cuidadosamente quién recibirá el mensaje.

Para que su envío se realice correctamente, envíe el contenido personalizado más relevante a los destinatarios adecuados. Adobe Campaign le permite crear el público destinatario más adecuado: puede seleccionar destinatarios según su edad, localización, lo que compraron, si hicieron clic en un vínculo en un envío anterior, etc. Con Adobe Campaign, también puede definir perfiles de prueba, grupos de control y direcciones semilla para asegurarse de que el público destinatario sea correcto.

## Asignaciones de destino {#target-mappings}

De manera predeterminada, las plantillas de envío tienen como destino **Perfiles**. Adobe Campaign ofrece otras asignaciones de destino para los envíos, que puede cambiar según sus necesidades.

Estas asignaciones se presentan [en esta sección](../../automating/using/query.md#targeting-dimensions-and-resources).

También puede crear y utilizar una asignación de destino personalizada. Para obtener más información, consulte [esta sección](../../administration/using/target-mappings-in-campaign.md).

## Datos externos {#external-data}

Puede enviar a destinatarios que estén almacenados en un archivo externo en lugar de guardarlos en la base de datos. Para ello, diseñe un flujo de trabajo que cargue datos en la base de datos desde un archivo y cree una audiencia asociada.  Obtenga más información [en este caso de uso](../../automating/using/use-case-calling-workflow.md). Consulte también [Invocación de un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Envíos a suscriptores {#send-to-subscribers}

Para enviar mensajes a los suscriptores de una newsletter, puede enviar directamente a los destinatarios de los suscriptores al servicio informativo correspondiente. Obtenga más información [en esta sección](../../audiences/using/about-subscriptions.md).

**Sugerencia**: puede crear una audiencia de lista dirigida a los suscriptores de la newsletter mediante un flujo de trabajo. A continuación, puede seleccionar esta audiencia en una entrega. Para obtener más información, consulte [Creación de audiencias de lista](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Pruebas, perfiles de prueba y grupos de control {#proofs-test-control-groups}

Para probar el envío, utilice pruebas antes de enviar al destinatario principal.
Asegúrese de seleccionar los destinatarios de prueba adecuados, ya que validan el formulario y el contenido del mensaje. Los pasos para enviar pruebas se presentan [en esta sección](../../sending/using/sending-proofs.md).

Obtenga más información acerca de los perfiles de prueba [en esta sección](../../audiences/using/managing-test-profiles.md).

Puede usar [Grupos de control](../../sending/using/control-group.md) para medir el impacto de sus campañas al excluir una parte de su audiencia. A continuación, podrá comparar el comportamiento de la población de destinatarios que recibió el mensaje con el comportamiento de los contactos a los que no estaban destinados. En función de los registros de envío, también puede destinar un grupo de control en campañas futuras.

## Deduplicación de direcciones {#deduplicate-addresses}

Es importante evitar tener direcciones de correo electrónico duplicadas, ya que esto puede perjudicar al destinatario:

* El mismo mensaje se puede enviar más de una vez cuando se divide un destinatario.

* Si un destinatario cancela la suscripción después de recibir un mensaje, su perfil duplicado seguirá recibiendo mensajes futuros.

Las direcciones duplicadas protegen su reputación de envío y garantizan una buena gestión de cuarentena.

Obtenga más información [en este caso de uso](../../automating/using/deduplicating-data-imported-file.md).
