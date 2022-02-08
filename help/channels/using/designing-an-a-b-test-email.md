---
title: Diseño de un correo electrónico de prueba A/B
description: Descubra la funcionalidad de la prueba A/B y siga estos pasos para crear un correo electrónico a partir de una plantilla de prueba A/B en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
feature: Email
role: User
level: Beginner
exl-id: 07cbf39c-4f53-49b1-8e85-c6df39f014b5
source-git-commit: 2adead5903eb2710207d7aeaaa85418bd616ca5d
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 95%

---

# Diseño de un correo electrónico de prueba A/B{#designing-an-a-b-test-email}

La funcionalidad de prueba A/B en Adobe Campaign le permite definir entre dos y tres variantes de correo electrónico. Cada variante se envía a las muestras de población para determinar cuál tiene el mejor resultado. Una vez determinada, la variante ganadora se envía a la población restante.

Puede elegir entre variar el contenido, el asunto o el remitente del correo electrónico.

>[!NOTE]
>
>No es posible realizar pruebas A/B en correos electrónicos creados en Adobe Experience Manager.

## Creación de un correo electrónico de prueba A/B {#creating-an-a-b-test-email}

Se puede crear una prueba A/B con el asistente de creación de correo electrónico estándar, al que se añade un paso de configuración de prueba A/B. La creación de un correo electrónico estándar se detalla en la sección [Creación de un correo electrónico](../../channels/using/creating-an-email.md).

En el contexto específico de una prueba A/B:

1. Cree un nuevo correo electrónico a partir de una de las tres plantillas específicas de prueba A/B, según el elemento que desee modificar:

   * Prueba A/B en el remitente.
   * Prueba A/B en contenido.
   * Prueba A/B en el asunto.

   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Las plantillas de prueba A/B y de seguimiento están ocultas de forma predeterminada. Compruebe la casilla de verificación A/B en el lado izquierdo (**[!UICONTROL Filter]** panel lateral) para mostrarlas.

1. Defina las propiedades generales y la audiencia de destino del mensaje de correo electrónico, igual que para un correo electrónico estándar. Consulte la sección [Creación de audiencias](../../audiences/using/creating-audiences.md).
1. En el cuarto paso del asistente de creación, defina los parámetros de prueba A/B:

   * **[!UICONTROL Number of variants]**: puede elegir utilizar dos o tres variantes. Si elige tres variantes, esta opción no se puede modificar una vez confirmado este paso en el asistente.
   * **[!UICONTROL Winning strategy]**: seleccione el criterio que se debe usar para determinar la variante ganadora.
   * **[!UICONTROL Target breakdown]**: elija qué porcentaje de destinatario debe recibir cada variante. El porcentaje restante recibe la variante ganadora una vez que se haya determinado. Los perfiles de destino se seleccionan de forma aleatoria.

      >[!NOTE]
      >
      >Si la población total es inferior a 50 k, cada variante debe representar al menos el 10 % de la población total.

   * **[!UICONTROL Winner sending method]**: elija si desea que la variante ganadora se envíe automáticamente una vez determinada o si desea confirmar manualmente el envío a la población restante.
   * **[!UICONTROL Test duration]**: especifique la duración de la prueba. La variante ganadora se determina automáticamente después de esta duración. Puede elegir manualmente la variante ganadora antes del final de la prueba en el panel de correo electrónico.

      La prueba debe ser de al menos una hora para que todos los datos de seguimiento se recopilen y se tengan en cuenta correctamente para seleccionar la variante ganadora.
   ![](assets/ab_parameters.png)

1. Una vez definidos los parámetros de prueba A/B, pase al siguiente paso del asistente y defina el contenido del correo electrónico. En función de la plantilla que haya elegido, puede definir varios asuntos, varios nombres de remitente o varios contenidos diferentes. Utilice el carrusel para desplazarse entre las distintas variantes. Para obtener más información, consulte la sección del [editor de contenido](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/create_ab_testing2.png)

1. Confirme el correo electrónico que ha creado. A continuación, se muestra el panel de correo electrónico.
1. Programe el envío. La fecha definida indica el inicio de la prueba A/B.
1. Compruebe los parámetros de prueba A/B que se muestran en el bloque **[!UICONTROL A/B test parameters]**. Puede modificarlos hasta que confirme el envío de la prueba (paso 9) seleccionando el bloque.

   ![](assets/create_ab_testing3.png)

1. Prepare el envío de correo electrónico para analizar el destinatario y el número de mensajes que se van a enviar. Consulte la sección [Preparación del envío](../../sending/using/preparing-the-send.md).
1. Antes de enviar la prueba A/B, compruebe su correo electrónico enviando pruebas.
1. Una vez finalizada la preparación, confirme el envío de la prueba. Una vez confirmados, los parámetros de prueba A/B no pueden modificarse.

   La prueba A/B comienza en la fecha definida en la **[!UICONTROL Schedule]**. Puede realizar un seguimiento del progreso mediante los bloques **[!UICONTROL A/B test]** y **[!UICONTROL Deployment]**.

   Puede seleccionar manualmente la variante ganadora en cualquier momento si desea reducir la duración de la prueba.

   Una vez finalizada la prueba, se muestra una tabla de resumen en el bloque **[!UICONTROL A/B Test]**, lo que le permite observar los distintos indicadores de todas las variantes que se han probado.

1. Si ha seleccionado **[!UICONTROL Send after confirmation]** como método de envío, debe seleccionar manualmente la variante ganadora para que se inicie el envío a la población restante. Si ha seleccionado **[!UICONTROL Automatic]**, la variante ganadora se envía automáticamente a la población restante en cuanto el sistema la haya determinado.

   >[!NOTE]
   >
   >Si hay un empate, la variante ganadora debe seleccionarse manualmente. Puede notificar al creador de correo electrónico y a los modificadores que se ha elegido una variante o que es necesario seleccionarla. Consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

El correo electrónico se ha definido y enviado. Puede acceder a sus registros e informes para calcular el éxito de la campaña.

## Acerca de los indicadores de prueba A/B {#about-a-b-test-indicators}

En el panel de correo electrónico, hay varios indicadores disponibles para ayudarle a medir la prueba A/B: cantidad de clics, aperturas, devoluciones, etc.

Tenga en cuenta que el indicador de **[!UICONTROL Estimated recipient reactivity]** es una tasa que compara el número de destinatarios que hicieron clic con el número de destinatarios que abrieron el correo electrónico. Por ejemplo, si 10 destinatarios abrieron el correo electrónico y 5 destinatarios hicieron clic en él, la tasa de reacción es del 50 %.
