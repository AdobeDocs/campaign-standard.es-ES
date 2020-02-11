---
title: Envío de pruebas
description: Aprenda a enviar pruebas.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# Envío de pruebas {#sending-proofs}

Una prueba es un mensaje específico que le permite probar un mensaje antes de enviarlo al destino principal.

Los destinatarios de la prueba se encargan de aprobar el mensaje (su contenido y forma). Se definen en los perfiles **de prueba**. Para obtener más información sobre esto, consulte [Administración de perfiles](../../audiences/using/managing-test-profiles.md)de prueba.

Para enviar una prueba, los perfiles de prueba deben incluirse en la audiencia del mensaje.

En un mensaje:

1. Haga clic en el botón **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Seleccione el tipo de prueba que desee utilizar:

   * **[!UICONTROL Email rendering]**:: seleccione esta opción para probar la forma en que se recibe el mensaje según las bandejas de entrada objetivo. Para obtener más información, consulte Representación [por](../../sending/using/email-rendering.md)correo electrónico.
   * **[!UICONTROL Proof]**:: seleccione esta opción para probar el mensaje antes de enviarlo al destino principal. Los destinatarios de la prueba se encargan de aprobar la entrega comprobando tanto su contenido como su formato.
   * **[!UICONTROL Proof + Email rendering]**:: esta opción combina las dos opciones anteriores.
   ![](assets/bat_select1.png)

1. Confirme su elección.

   Las pruebas se envían a los perfiles de prueba.

   ![](assets/bat_select2.png)

1. Puede ver las pruebas mediante la lista **[!UICONTROL Proofs]** desplegable.

   ![](assets/bat_view.png)

1. Seleccione una prueba para acceder a su resumen. En un mensaje de correo electrónico, si ha seleccionado la opción Representación **por** correo electrónico como tipo de prueba, el **[!UICONTROL Access email rendering]** icono se muestra a la derecha de la etiqueta de prueba. Consulte Representación [por correo electrónico](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Según los comentarios de las personas que reciban la prueba, se le puede solicitar que modifique el contenido de la entrega. Una vez realizadas las modificaciones, debe reiniciar la preparación del correo electrónico y volver a enviar una prueba. Se puede acceder a cada nueva prueba mediante el **[!UICONTROL Show proofs]** botón .

Debe enviar tantas pruebas como sea necesario hasta que haya finalizado el contenido de la entrega. Una vez finalizado, puede enviar el envío al objetivo principal y cerrar el ciclo de aprobación.

**Tema relacionado:**

[Envío de una prueba, preparación y envío de un vídeo por correo electrónico](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
