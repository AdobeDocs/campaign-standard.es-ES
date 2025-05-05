---
title: Prueba de mensajes de correo electrónico con perfiles de destino
description: Obtenga información sobre cómo probar mensajes mediante perfiles de destino y direcciones de sustitución.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
context-tags: seedMember,overview
feature: Control Groups
role: User
level: Intermediate
exl-id: aa68914f-0497-40ba-98c8-4d4b2c6705fb
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1533'
ht-degree: 4%

---

# Prueba de mensajes de correo electrónico con perfiles de destino {#testing-message-profiles}

## Información general {#overview}

Además de [perfiles de prueba](../../audiences/using/managing-test-profiles.md), puede probar un mensaje de correo electrónico colocándose en la posición de uno de los perfiles de destino. Esto le permite obtener una representación exacta del mensaje que recibirá el perfil (campos personalizados, información dinámica y personalizada, incluidos los datos adicionales de flujos de trabajo...).

>[!IMPORTANT]
>
>Esta función le permite enviar información personal de perfil a direcciones de correo electrónico externas. Tenga en cuenta que la ejecución de solicitudes de privacidad (RGPD y CCPA) en Campaign Standard NO ejecutará esa solicitud de manera externa.

Los pasos principales son los siguientes:

1. Configure el mensaje y luego inicie la fase **Preparación**.
1. **Seleccione uno o varios perfiles** entre los perfiles a los que apunta el mensaje.
1. Asocie a cada perfil una **dirección de sustitución** a la que se enviarán las pruebas.
1. (opcional) Para cada perfil, defina un **prefix** para añadirlo a la línea de asunto de la prueba.
1. **Vista previa** en el Designer de correo electrónico sobre cómo se mostrará el mensaje para los perfiles.
1. Envíe las pruebas.

   >[!IMPORTANT]
   >
   >[!DNL Campaign Standard] procesa las pruebas como envíos estándar. Como resultado, al enviar pruebas utilizando la sustitución de perfiles, se añaden registros a los &quot;logs&quot; de envío y seguimiento de los perfiles seleccionados.

![](assets/do-not-localize/how-to-video.png) [Descubra esta funcionalidad en vídeo](#video)

## Selección de perfiles y direcciones de sustitución {#selecting-profiles}

Para utilizar perfiles de destino para realizar pruebas, primero debe seleccionarlos y luego definir las direcciones de sustitución que recibirán las pruebas. Para ello, puede [seleccionar perfiles específicos](#selecting-individual-profiles) entre los perfiles de destino o [importar perfiles de una audiencia existente](#importing-from-audience).

>[!NOTE]
>
>Puede seleccionar un máximo de 100 perfiles para realizar pruebas.

### Selección de perfiles individuales {#selecting-individual-profiles}

1. En el panel del mensaje, asegúrese de que la preparación del mensaje se haya realizado correctamente y, a continuación, haga clic en el bloque **[!UICONTROL Audience]**.

   ![](assets/substitution_preparation.png)

1. En la ficha **[!UICONTROL Profile substitutions]**, haga clic en el botón **[!UICONTROL Create element]** para seleccionar los perfiles que desea utilizar para la prueba.

   ![](assets/substitution_tab.png)

1. Haga clic en el botón de selección de perfiles para mostrar la lista de perfiles objetivo por el mensaje.

   ![](assets/substitution_recipient_selection.png)

1. Seleccione el perfil que desea utilizar para la prueba, luego ingrese en el campo **[!UICONTROL Address]** la dirección de sustitución deseada y haga clic en **[!UICONTROL Confirm]**. Todas las pruebas dirigidas al perfil se envían a esta dirección de correo electrónico, en lugar de a la definida en la base de datos para este perfil.

   Si desea agregar un prefijo específico a la línea de asunto de las pruebas, rellene el campo **[!UICONTROL Subject line prefix]**.

   >[!NOTE]
   >
   >El prefijo de línea de asunto puede contener hasta 500 caracteres.

   ![](assets/substitution_address.png)

   El prefijo se mostrará de la siguiente manera:

   ![](assets/substitution_prefixsample.png)

1. El perfil se añade a la lista, con su dirección de sustitución y prefijo asociados. Repita los pasos anteriores para todos los perfiles que desee usar en la prueba y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/substitution_recipients_confirm.png)

   Si desea enviar una prueba a varias direcciones de sustitución para un mismo perfil, debe añadir este perfil tantas veces como sea necesario.

   En el siguiente ejemplo, la prueba basada en el perfil de John Smith se envía a dos direcciones de sustitución diferentes:

   ![](assets/substitution_multiple_addresses.png)

1. Una vez definidos todos los perfiles y direcciones de sustitución, puede enviar una prueba para probar el mensaje. Para ello, haga clic en el botón **[!UICONTROL Test]** y luego seleccione el tipo de prueba que desea realizar.

   Tenga en cuenta que si no se ha agregado ningún perfil de prueba al destino del mensaje, las opciones **[!UICONTROL Email rendering]** y **[!UICONTROL Proof + Email rendering]** no están disponibles.  Para obtener más información sobre la entrega de pruebas, consulte [esta sección](../../sending/using/sending-proofs.md).

   ![](assets/substitution_send_test.png)

>[!IMPORTANT]
>
>Si realiza algún cambio en el mensaje, asegúrese de volver a iniciar la preparación del mensaje. De lo contrario, los cambios no se reflejarán en la prueba.

### Importación de perfiles de una audiencia {#importing-from-audience}

Campaign Standard permite importar una audiencia de perfiles que puede utilizar para realizar pruebas. Esto le permite, por ejemplo, enviar a una dirección de correo electrónico única un conjunto completo de mensajes dirigidos a diferentes perfiles.

Además, si la audiencia ya está configurada con las columnas dirección y prefijo, podrá importar esta información en la pestaña **[!UICONTROL Profile substitutions]**. Un ejemplo de importación de audiencias con direcciones de sustitución se detalla en [esta sección](#use-case).

>[!NOTE]
>
>Al importar una audiencia, solo se seleccionan los perfiles correspondientes al destinatario del mensaje y se añaden a la pestaña **[!UICONTROL Profile substitutions]**.

Para importar perfiles para utilizarlos en pruebas desde una audiencia, siga estos pasos:

1. En el panel del mensaje, asegúrese de que la preparación del mensaje se ha realizado correctamente y, a continuación, haga clic en el bloque **[!UICONTROL Audience]**.

   ![](assets/substitution_preparation.png)

1. En la pestaña **[!UICONTROL Profile substitutions]**, haga clic en **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_audience_import.png)

1. Seleccione la audiencia que desea utilizar e introduzca la dirección de sustitución y el prefijo que se utilizará para las pruebas enviadas a la audiencia.

   >[!NOTE]
   >
   >El prefijo de línea de asunto puede contener hasta 500 caracteres.

   ![](assets/substitution_audience_define.png)

   Si las direcciones de sustitución o los prefijos que se van a utilizar ya se han definido en la audiencia, seleccione la opción **[!UICONTROL From Audience]** y, a continuación, especifique la columna que se utilizará para recuperar esta información.

   ![](assets/substitution_fromaudience.png)

1. Haga clic en el botón **[!UICONTROL Import]**. Los perfiles de la audiencia correspondiente al destinatario del mensaje se agregan a la ficha **[!UICONTROL Profile substitution]**, así como las direcciones de sustitución y los prefijos asociados.

![](assets/substitution_audience_imported.png)

>[!NOTE]
>
>Si vuelve a importar la misma audiencia, con direcciones de sustitución o prefijos diferentes, los perfiles se agregan a la lista además de los de la importación anterior.

## Vista previa del mensaje con perfiles de destino

>[!NOTE]
>
>La vista previa solo está disponible con el Designer de correo electrónico.

Para poder obtener una vista previa de los mensajes mediante perfiles de destino, asegúrese de agregar estos perfiles a la lista **[!UICONTROL Profile substitution]** (consulte [Definición de perfiles y direcciones de sustitución](#selecting-profiles)).

Si desea utilizar campos de personalización en el mensaje, se deben agregar **antes de** que inicie la preparación del mensaje. De lo contrario, no se tienen en cuenta en la vista previa. Como resultado, asegúrese de volver a iniciar la preparación del mensaje si se realiza algún cambio en los campos personalizados.

Para obtener una vista previa de los mensajes mediante la sustitución de perfiles, siga estos pasos:

1. En el panel del mensaje, haga clic en la instantánea de contenido para abrir el mensaje en el Designer de correo electrónico.

   ![](assets/substitution_preview_access.png)

1. Seleccione la ficha **[!UICONTROL Preview]** y luego haga clic en **[!UICONTROL Change profile]**.

   ![](assets/substitution_preview_changeprofile.png)

1. Haga clic en la ficha **[!UICONTROL Profile Substitution]** para mostrar los perfiles de sustitución que se han agregado a las pruebas.

   Seleccione los perfiles que desee usar para la vista previa y luego haga clic en **[!UICONTROL Select]**.

   ![](assets/substitution_preview_selection.png)

1. Se muestra una vista previa del mensaje. Utilice las flechas para desplazarse entre los perfiles seleccionados.

   ![](assets/substitution_preview.png)

## Ejemplo de uso {#use-case}

En este caso de uso, queremos enviar a un conjunto de perfiles específicos un boletín de correo electrónico personalizado. Antes de enviar la newsletter, queremos previsualizarla con algunos de los perfiles de destino y enviar pruebas a las direcciones de correo electrónico internas definidas en un archivo externo.

Los pasos principales para este caso de uso son los siguientes:

1. Cree la audiencia que quiera usar para hacer pruebas.
1. Cree un flujo de trabajo para segmentar perfiles y enviar la newsletter.
1. Configure las sustituciones de perfil del mensaje.
1. Vista previa del mensaje con perfiles de destino.
1. Envíe pruebas.

### Paso 1: Crear la audiencia que se utilizará para la prueba

1. Prepare el archivo que desea importar para crear la audiencia. En nuestro caso, debe contener la dirección de sustitución que se utilizará para la prueba y un prefijo que se añadirá en la línea de asunto de la prueba.

   En este ejemplo, la dirección de correo electrónico &quot;oliver.vaughan@internal.com&quot; recibe una prueba del mensaje dirigido al perfil con la dirección de correo electrónico &quot;john.doe@mail.com&quot; El prefijo &quot;JD&quot; se añade a la línea de asunto de la prueba.

   ![](assets/substitution_uc1.png)

1. Cree el flujo de trabajo para crear una audiencia a partir del archivo. Para ello, añada y configure las siguientes actividades:

   * Actividad **[!UICONTROL Load file]**: importa el archivo CSV (para obtener más información sobre esta actividad, consulte [esta sección](../../automating/using/load-file.md)).
   * Actividad **[!UICONTROL Reconciliation]**: vincula la información del archivo con la información de la base de datos. En este ejemplo, use la dirección de correo electrónico del perfil como campo de reconciliación (para obtener más información sobre esta actividad, consulte [esta sección](../../automating/using/reconciliation.md)).
   * **[!UICONTROL Save audience]** actividad: crea una audiencia basada en el archivo importado (para obtener más información sobre esta actividad, consulte [esta sección](../../automating/using/save-audience.md)).

   ![](assets/substitution_uc2.png)

1. Ejecute el flujo de trabajo y, a continuación, vaya a la pestaña **[!UICONTROL Audiences]** para comprobar que la audiencia se ha creado con la información deseada.

   En este ejemplo, la audiencia está formada por tres perfiles. Cada uno de ellos está vinculado a una dirección de correo electrónico de sustitución que recibirá la prueba, con un prefijo que se utilizará en la línea de asunto de la prueba.

   ![](assets/substitution_uc3.png)

### Paso 2: Creación de un flujo de trabajo para perfiles de destinatario y envío de la newsletter

1. Agregue actividades **[!UICONTROL Query]** y **[!UICONTROL Email delivery]** y, a continuación, configúrelas según sus necesidades (consulte las secciones [Consulta](../../automating/using/query.md) y [Envío de correo electrónico](../../automating/using/email-delivery.md) ).

   ![](assets/substitution_uc4.png)

1. Ejecute el flujo de trabajo y asegúrese de que la preparación del mensaje se haya realizado correctamente.

### Paso 3: Configuración de la pestaña Sustitución de perfiles del mensaje

1. Abra la actividad **[!UICONTROL Email delivery]**. En el panel del mensaje, haga clic en el bloque **[!UICONTROL Audience]**.

   ![](assets/substitution_uc5.png)

1. Seleccione la ficha **[!UICONTROL Profile substitutions]** y luego haga clic en **[!UICONTROL Import from an audience]**.

   ![](assets/substitution_uc6.png)

1. En el campo **[!UICONTROL Audience]**, seleccione la audiencia creada a partir del archivo.

   ![](assets/substitution_uc7.png)

1. Defina la dirección de sustitución y el prefijo de línea de asunto que se utilizarán al enviar las pruebas.

   Para ello, seleccione la opción **[!UICONTROL From audience]** y luego seleccione la columna de la audiencia que contiene la información.

   ![](assets/substitution_uc8.png)

1. Haga clic en el botón **[!UICONTROL Import]**. Los perfiles de la audiencia se añaden a la lista, con sus direcciones de sustitución y prefijos de línea de asunto asociados.

   ![](assets/substitution_uc9.png)

   >[!NOTE]
   >
   >En nuestro caso, todos los perfiles de la audiencia están dirigidos por la actividad **[!UICONTROL Query]**. Si uno de estos perfiles no formaba parte del destinatario de mensajes, no se añadía a la lista.

### Paso 4: Previsualizar el mensaje con perfiles de destino

1. En el panel del mensaje, haga clic en la instantánea de contenido para abrir el mensaje en el Designer de correo electrónico.

   ![](assets/substitution_uc10.png)

1. Seleccione la ficha **[!UICONTROL Preview]** y luego haga clic en **[!UICONTROL Change profile]**.

   ![](assets/substitution_uc_preview.png)

1. Haga clic en la ficha **[!UICONTROL Profile Substitution]** para mostrar los perfiles de sustitución que se han agregado anteriormente.

   Seleccione los perfiles que desee usar para la vista previa y luego haga clic en **[!UICONTROL Select]**.

   ![](assets/substitution_uc_selectpreview.png)

1. Se muestra una vista previa del mensaje. Utilice las flechas para desplazarse entre los perfiles seleccionados.

   ![](assets/substitution_uc_previewprofile.png)

### Paso 5: Envío de pruebas

1. En el panel del mensaje, haga clic en el botón **[!UICONTROL Test]** y confirme.

   ![](assets/substitution_uc_sendproof.png)

1. Las pruebas se envían de acuerdo con lo que se ha configurado en la pestaña **[!UICONTROL Profile substitutions]**.

   ![](assets/substitution_uc_proofs.png)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo puede probar los mensajes de correo electrónico mediante la sustitución de perfiles.

>[!VIDEO](https://video.tv.adobe.com/v/36462?quality=12&captions=spa)

Hay disponibles [más vídeos de procedimientos para el Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
