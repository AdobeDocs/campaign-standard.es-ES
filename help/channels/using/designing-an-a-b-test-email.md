---
title: Diseño de un correo electrónico de prueba A/B
description: Descubra la funcionalidad de la prueba A/B y siga estos pasos para crear un correo electrónico a partir de una plantilla de prueba A/B en Adobe Campaign.
page-status-flag: never-activated
uuid: 104f6973-68a7-4692-a90a-a5570a980ec7
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: e249ba70-90d0-43f2-868c-ce9fdc7e642d
context-tags: delivery,abTesting,back;deliveryCreation,wizard;delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Diseño de un correo electrónico de prueba A/B{#designing-an-a-b-test-email}

La funcionalidad de prueba A/B de Adobe Campaign permite definir entre dos y tres variantes de correo electrónico. Cada variante se envía a las muestras de población para determinar cuál tiene el mejor resultado. Una vez determinada, la variante ganadora se envía a la población restante.

Puede elegir entre variar el contenido, el asunto o el remitente del correo electrónico.

>[!NOTE]
>
>No es posible realizar pruebas A/B en correos electrónicos creados en Adobe Experience Manager.

## Creating an A/B test email {#creating-an-a-b-test-email}

Se puede crear una prueba A/B con el asistente de creación de correo electrónico estándar, al que se agrega un paso de configuración de prueba A/B. La creación de un correo electrónico estándar se detalla en la sección [Creación de un correo electrónico](../../channels/using/creating-an-email.md) .

En el contexto específico de una prueba A/B:

1. Cree un nuevo correo electrónico a partir de una de las tres plantillas específicas de prueba A/B, según el elemento que desee modificar:

   * Prueba A/B en el remitente
   * Prueba A/B en contenido
   * Prueba A/B sobre el sujeto
   ![](assets/create_ab_testing.png)

   >[!NOTE]
   >
   >Las plantillas de prueba A/B y de seguimiento están ocultas de forma predeterminada. Compruebe la casilla de verificación A/B en el lado izquierdo (panel **[!UICONTROL Filter]**lateral) para mostrarlos.

1. Defina las propiedades generales y la audiencia de destino del correo electrónico, al igual que para un correo electrónico estándar. Consulte la sección [Creación de audiencias](../../audiences/using/creating-audiences.md) .
1. En el cuarto paso del asistente de creación, defina los parámetros de prueba A/B:

   * **[!UICONTROL Number of variants]**:: Puede elegir utilizar dos o tres variantes. Si elige tres variantes, esta opción no se puede modificar una vez confirmado este paso en el asistente.
   * **[!UICONTROL Winning strategy]**:: Seleccione el criterio que se utilizará para determinar la variante ganadora.
   * **[!UICONTROL Target breakdown]**:: Elija qué porcentaje del objetivo recibirá cada variante. El porcentaje restante recibirá la variante ganadora una vez que se haya determinado. Los perfiles de destino se seleccionan de forma aleatoria.
   * **[!UICONTROL Winner sending method]**:: Elija si desea que la variante ganadora se envíe automáticamente una vez determinada o si desea confirmar manualmente el envío a la población restante.
   * **[!UICONTROL Test duration]**:: Especifique la duración de la prueba. La variante ganadora se determina automáticamente después de esta duración. Puede elegir manualmente la variante ganadora antes del final de la prueba en el panel de correo electrónico.

      La prueba debe ser de al menos una hora para que todos los datos de seguimiento se recopilen y se tengan en cuenta correctamente para seleccionar la variante ganadora.
   ![](assets/ab_parameters.png)

1. Una vez definidos los parámetros de prueba A/B, pase al siguiente paso del asistente y defina el contenido del correo electrónico. En función de la plantilla que haya elegido, puede definir varios temas, varios nombres de remitente o varios contenidos diferentes. Utilice el carrusel para desplazarse entre las distintas variantes del elemento. Para obtener más información, consulte la sección del editor [de](../../designing/using/designing-content-in-adobe-campaign.md) contenido.

   ![](assets/create_ab_testing2.png)

1. Confirme la creación del correo electrónico. Luego se mostrará el tablero de correo electrónico.
1. Programe el envío. La fecha definida indica el inicio de la prueba A/B.
1. Compruebe los parámetros de prueba A/B que se muestran en el **[!UICONTROL A/B test parameters]**bloque. Puede modificarlas hasta que confirme el envío de la prueba (paso 9) seleccionando el bloque.

   ![](assets/create_ab_testing3.png)

1. Prepare el envío de correo electrónico para analizar el destino y el número de mensajes que se van a enviar. Consulte la sección [Preparación del envío](../../sending/using/preparing-the-send.md) .
1. Antes de enviar la prueba A/B, compruebe su correo electrónico enviando pruebas.
1. Una vez finalizada la preparación, confirme el envío de la prueba. Una vez confirmados, los parámetros de prueba A/B no pueden modificarse.

   La prueba A/B comienza en la fecha definida en la **[!UICONTROL Schedule]**.Puede rastrear su progreso usando los**[!UICONTROL A/B test]** bloques y **[!UICONTROL Deployment]**.

   Puede seleccionar manualmente la variante ganadora en cualquier momento si desea reducir la duración de la prueba.

   Una vez finalizada la prueba, se muestra una tabla de resumen en el **[!UICONTROL A/B Test]**bloque y esto le permite ver los distintos indicadores de las distintas variantes que se probaron.

1. Si ha seleccionado **[!UICONTROL Send after confirmation]**como método de envío, debe seleccionar manualmente la variante ganadora para empezar a enviarla a la población restante. Si ha seleccionado**[!UICONTROL Automatic]**, la variante ganadora se envía automáticamente a la población restante en cuanto el sistema la haya determinado.

   >[!NOTE]
   >
   >Si hay un empate, la variante ganadora debe seleccionarse manualmente. Puede notificar al creador de correo electrónico y a los modificadores que se ha elegido una variante o que es necesario seleccionarla. Consulte Notificaciones [de](../../administration/using/sending-internal-notifications.md)Adobe Campaign.

El correo electrónico se ha definido y enviado. Puede acceder a sus registros e informes para medir el éxito de la campaña.

**Tema** relacionado:

[Creación de un vídeo de correo electrónico](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)

## Acerca de los indicadores de prueba A/B {#about-a-b-test-indicators}

En el tablero de correo electrónico, hay varios indicadores disponibles para ayudarle a medir la prueba A/B: cantidad de clics, aperturas, devoluciones, etc.

Tenga en cuenta que el **[!UICONTROL Estimated recipient reactivity]**indicador es una tasa que compara el número de destinatarios que hicieron clic con el número de destinatarios que abrieron el correo electrónico. Por ejemplo, si 10 destinatarios abrieron el correo electrónico y 5 hicieron clic en él. La tasa de reactividad es del 50%.
