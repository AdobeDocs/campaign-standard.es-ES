---
title: Preparación del envío
description: Aprenda a definir la preparación antes del envío.
page-status-flag: nunca activado
uuid: 1038dae2-164c-4579-9294-bdf2a4eb12d6
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: preparar y probar mensajes
discoiquuid: 003abc83-7f07-471f-ab2f-1d352d22c26f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Preparación del envío{#preparing-the-send}

La preparación corresponde al paso de calcular la población objetivo y generar el contenido del mensaje para cada perfil incluido en el destino. Una vez finalizada la preparación, los mensajes están listos para ser enviados, ya sea inmediatamente o en [la fecha y hora](../../sending/using/about-scheduling-messages.md)programadas.

1. Para empezar a preparar el envío, haga clic en el botón **Preparar** situado en la barra de acciones.

   ![](assets/preparing_delivery_2.png)

1. El **[!UICONTROL Deployment]** bloque muestra el progreso de la preparación y luego las estadísticas de preparación: número de mensajes dirigidos, número de mensajes que enviar, etc.

   Según el tamaño de la población objetivo, esta operación puede tardar algún tiempo.

   ![](assets/preparing_delivery.png)

1. Detenga la preparación en cualquier momento con el botón **Detener** , ubicado en la barra de acciones.

   Durante la fase de preparación no se envían mensajes. Por lo tanto, puede comenzar o parar esto sin riesgo de afectar nada.

   ![](assets/preparing_delivery_6.png)

1. El mensaje se guarda automáticamente durante la etapa de preparación de la entrega. Si necesita realizar cambios en la programación del mensaje después del paso de preparación, deberá asegurarse de volver a hacer clic en el **[!UICONTROL Prepare]** botón para que se tengan en cuenta dichos cambios. For more information on how to schedule a message, refer to this [page](../../sending/using/about-scheduling-messages.md).

   ![](assets/preparing_delivery_5.png)

1. Para ver los registros de preparación, haga clic en el botón situado en la parte inferior derecha del bloque.

   ![](assets/preparing_delivery_4.png)

1. Se abre la **[!UICONTROL Deployment]** ventana, corrija los errores y, a continuación, reinicie la preparación.

   El último mensaje de “log” muestra los mensajes de error y el número de errores. Un icono específico muestra el tipo de error encontrado: el icono amarillo indica un error de procesamiento no crítico; el icono rojo indica un error crítico que impide que se inicie la entrega.

   ![](assets/preparing_delivery_3.png)

1. Compruebe las estadísticas de preparación antes de confirmar el envío de los mensajes. Si el número de mensajes que se van a enviar no se corresponde con la configuración, edite la población objetivo (consulte [Selección de una audiencia en un mensaje](../../audiences/using/selecting-an-audience-in-a-message.md)) y reinicie la preparación.

Una vez finalizado el proceso de preparación, el mensaje estará listo para ser enviado. Para obtener más información sobre esto, consulte [Confirmación de envío](../../sending/using/confirming-the-send.md).

**Reglas de tipología**

Adobe Campaign incluye un conjunto de reglas de tipología integradas que se aplican durante la preparación del mensaje. Se utilizan para comprobar si un mensaje es válido y cumple los criterios de calidad. Consulte [Tipologías](../../administration/using/about-typology-rules.md). Puede definir sus propias reglas de tipología, por ejemplo, puede establecer reglas de fatiga globales entre canales que excluirán automáticamente los perfiles superpuestos de las campañas. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

**Comprobación de mensajes SMS**

Si ha insertado campos de personalización o texto condicional en el contenido de su mensaje SMS, estos factores pueden introducir caracteres que no se tienen en cuenta en la codificación GSM. Cuando se ejecuta la preparación, se supervisa la longitud del mensaje y se muestra un mensaje de advertencia si supera el límite.

Para más información sobre esto, consulte las secciones de codificación, longitud y transliteración [de](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration) SMS y [Personalización de mensajes](../../channels/using/personalizing-sms-messages.md) SMS.
