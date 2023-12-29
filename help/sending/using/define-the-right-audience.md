---
title: Definición de la audiencia correcta
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: '"Cuando tenga preparado el contenido, aprenda a definir cuidadosamente quién recibirá el mensaje".'
feature: Deliverability
role: User
level: Intermediate
exl-id: 1e06fd9d-e850-4856-8f7b-b581dbe157df
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 71%

---

# Definición de la audiencia correcta {#define-the-right-audience}

La población objetivo es clave: cree sus listas con cuidado, pruebe sus correos electrónicos con clientes de correo electrónico y dispositivos móviles populares, y asegúrese de que sus listas de correos electrónicos estén actualizadas (sin direcciones desconocidas u obsoletas). También puede enviar pruebas que ayuden a configurar un ciclo de validación completo.

Aprenda más sobre las poblaciones objetivo [en esta sección](../../audiences/using/selecting-an-audience-in-a-message.md)

## Selección de la audiencia de destino correcta {#target-the-right-audience}

Cuando tenga preparado el contenido, debe definir cuidadosamente quién recibirá el mensaje.

Para que su envío se realice correctamente, envíe el contenido personalizado más relevante a los destinatarios adecuados. Adobe Campaign le permite crear la población más adecuada: puede seleccionar destinatarios según su edad, ubicación, lo que compraron, si hicieron clic en un vínculo en un envío anterior, etc. Con Adobe Campaign, también puede definir perfiles, grupos de control y direcciones semilla de prueba para asegurarse de que el destinatario es correcto.

## Asignaciones de destino {#target-mappings}

De forma predeterminada, las plantillas de envío se dirigen a **Perfiles**. Adobe Campaign ofrece otras asignaciones de destino para los envíos, que puede cambiar según sus necesidades.

Estas asignaciones se presentan [en esta sección](../../automating/using/query.md#targeting-dimensions-and-resources).

También puede crear y utilizar una asignación de destino personalizada. Para obtener más información, consulte [esta sección](../../administration/using/target-mappings-in-campaign.md).

## Datos externos {#external-data}

Puede enviar a destinatarios que estén almacenados en un archivo externo en lugar de guardarlos en la base de datos. Para ello, diseñe un flujo de trabajo que cargue datos en la base de datos desde un archivo y cree una audiencia asociada.  Más información [en este caso de uso](../../automating/using/use-case-calling-workflow.md). Consulte también [Invocación de un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md).

## Envíos a suscriptores {#send-to-subscribers}

Para enviar mensajes a los suscriptores de una newsletter, puede enviar directamente a los destinatarios de los suscriptores al servicio informativo correspondiente. Obtenga más información [en esta sección](../../audiences/using/about-subscriptions.md).

**Sugerencia** : Puede crear una audiencia de Lista dirigida a los suscriptores del boletín informativo mediante un flujo de trabajo. A continuación, puede seleccionar esta audiencia en una entrega. Para obtener más información, consulte [Creación de audiencias de lista](../../audiences/using/creating-audiences.md#creating-list-audiences).

## Pruebas, perfiles de prueba y grupos de control {#proofs-test-control-groups}

Para probar el envío, utilice pruebas antes de enviar al destinatario principal.
Asegúrese de seleccionar los destinatarios de prueba adecuados, ya que validan el formulario y el contenido del mensaje. Se presentan los pasos para enviar pruebas [en esta sección](../../sending/using/sending-proofs.md).

Más información sobre los perfiles de prueba [en esta sección](../../audiences/using/managing-test-profiles.md).

Puede utilizar [Grupos de control](../../sending/using/control-group.md) para medir el impacto de sus campañas al excluir una parte de su audiencia. A continuación, podrá comparar el comportamiento de la población de destinatarios que recibió el mensaje con el comportamiento de los contactos a los que no estaban destinados. En función de los registros de envío, también puede destinar un grupo de control en campañas futuras.

## Deduplicación de direcciones {#deduplicate-addresses}

Es importante evitar tener direcciones de correo electrónico duplicadas, ya que esto puede perjudicar al destinatario:

* El mismo mensaje se puede enviar más de una vez cuando se divide un destinatario.

* Si un destinatario cancela la suscripción después de recibir un mensaje, su perfil duplicado seguirá recibiendo mensajes futuros.

Las direcciones duplicadas protegen su reputación de envío y garantizan una buena gestión de cuarentena.

Obtenga más información [en este caso de uso](../../automating/using/deduplicating-data-imported-file.md).
