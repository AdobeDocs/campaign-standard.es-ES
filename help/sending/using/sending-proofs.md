---
title: Envío de pruebas
description: Aprenda a enviar pruebas.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Proofs
role: User
level: Intermediate
exl-id: 75b64c43-f066-45e7-8d61-95eba8f52b05
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 98%

---

# Envío de pruebas {#sending-proofs}

## Acerca de las pruebas {#about-proofs}

Una prueba es un mensaje específico que permite probar un mensaje antes de enviarlo al destino principal. Los destinatarios de la prueba se encargan de aprobar el mensaje (su contenido y forma).

Existen dos tipos de destinatarios de prueba:

* **Los perfiles de prueba** permiten llegar a destinatarios adicionales que no coinciden con los criterios de objetivo definidos.

  Se pueden añadir a la audiencia de un mensaje para detectar cualquier uso fraudulento de la base de datos de destinatario o para asegurarse de que los correos electrónicos llegan a las bandejas de entrada. Para obtener más información, consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

  >[!NOTE]
  >
  >Para enviar una prueba, los perfiles de prueba deben incluirse en la audiencia del mensaje.

* **Los perfiles de sustitución** le permiten colocarse en la posición de uno de los perfiles objetivo y obtener una representación exacta del mensaje que va a recibir el perfil. Para obtener más información, consulte [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md).

  >[!NOTE]
  >
  >Esta función solo está disponible para el canal de correo electrónico.

## Envío de una prueba {#sending-a-proof}

Para enviar pruebas, siga estos pasos:

1. Asegúrese de que los destinatarios de las pruebas estén configurados:
   * **Los perfiles de prueba** deben incluirse en la audiencia del mensaje.
   * **Los perfiles de sustitución** deben añadirse una vez que la preparación del mensaje se haya realizado correctamente (consulte [esta sección](../../sending/using/testing-messages-using-target.md)).

1. Haga clic en el botón **[!UICONTROL Send a test]**.

   ![](assets/bat_select.png)

1. Seleccione el tipo de prueba que desee utilizar:

   * **[!UICONTROL Email rendering]**: seleccione esta opción para probar la forma en que se recibe el mensaje según las bandejas de entrada objetivo. Para obtener más información, consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: seleccione esta opción para probar el mensaje antes de enviarlo al destinatario principal. Los destinatarios de prueba se encargan de aprobar el envío, comprobando tanto su contenido como su formato.
   * **[!UICONTROL Proof + Email rendering]**: esta opción combina las dos opciones anteriores.

   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >El procesamiento por correo electrónico solo está disponible con perfiles de prueba. Si no se han añadido perfiles de prueba al mensaje, solo está disponible la opción **[!UICONTROL Proof]**.

1. Confirme la elección.

   Las pruebas se envían a los destinatarios configurados.

   ![](assets/bat_select2.png)

1. Puede comprobar las pruebas en la lista desplegable **[!UICONTROL Proofs]**.

   ![](assets/bat_view.png)

1. Seleccione una prueba para acceder al resumen. En el caso de un correo electrónico, si ha seleccionado la opción de **Procesamiento de correo electrónico** como tipo de prueba, el icono **[!UICONTROL Access email rendering]** se muestra a la derecha de la etiqueta de prueba. Consulte [Procesamiento de correo electrónico](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

Según los comentarios de las personas que reciban la prueba, se le puede pedir que modifique el contenido del envío. Una vez realizadas las modificaciones, debe reiniciar la preparación del correo electrónico y volver a enviar una prueba. Se puede acceder a cada prueba nueva con el botón **[!UICONTROL Show proofs]**.

Debe enviar tantas pruebas como sea necesario hasta que haya finalizado el contenido de su envío. Una vez hecho esto, puede realizar el envío al destinatario principal y cerrar el ciclo de aprobación.

## Configuración de la línea de asunto de pruebas {#configuring-proofs-subject-line}

Cuando se envía una prueba, su línea de asunto se configura de forma predeterminada con el prefijo **“Prueba”** , así como con un contador que indica el número de la prueba.

![](assets/proof-prefix.png)

Para cambiar la línea de asunto predeterminada y utilizarla, siga estos pasos:

1. En el panel del mensaje, haga clic en el botón **[!UICONTROL Open properties]**.
1. En la sección **[!UICONTROL Advanced parameters]**, defina el prefijo que desee utilizar de forma predeterminada en la línea de asunto.

Para ocultar el número de la prueba en la línea de asunto, active la opción **[!UICONTROL Hide proof prefix counter]**.

>[!NOTE]
>
>Si desea ocultar todo el prefijo de prueba, deje el campo **[!UICONTROL Subject line prefix]** en blanco.

![](assets/proof-prefix-configuration.png)

1. Haga clic en **[!UICONTROL Confirm]**. La configuración se aplica de forma predeterminada a todas las pruebas enviadas para el mensaje seleccionado.

**Temas relacionados:**

* [Envío de una prueba, preparación y envío de un vídeo por correo electrónico](../../sending/using/get-started-sending-messages.md#video)
* [Prueba de mensajes de correo electrónico con perfiles de destino](../../sending/using/testing-messages-using-target.md)
* [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)
* [Previsualización de mensajes](../../sending/using/previewing-messages.md)
* [Configuración del canal de correo electrónico](../../administration/using/configuring-email-channel.md)
