---
title: Acerca de los informes dinámicos
seo-title: Acerca de los informes dinámicos
description: Acerca de los informes dinámicos
seo-description: Con informes dinámicos, arrastre y suelte variables y dimensiones en su entorno improvisado y analice el éxito de sus campañas.
page-status-flag: no activado nunca
uuid: a 84 a 18 bd -4 e 33-466 e-a 6 ce-d 7008 fe 12746
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: acerca de los informes
discoiquuid: bbb 41 c 38-12 c 1-4625-85 d 5-69627 e 2 f 4 b 39
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 08b2363076adcc101b741ab66b85285e7a510baa

---


# About dynamic reports{#about-dynamic-reports}

>[!NOTE]
>
>Only users with administration rights or with organizational units set to **All** can create or save a new report. For more on this, refer to this [section](../../administration/using/types-of-users.md).

![](assets/dynamic_report_intro.png)

Informes dinámicos proporciona informes totalmente personalizables y en tiempo real. Agrega acceso a los datos de perfil, lo cual permite realizar análisis demográficos según dimensiones de perfil como sexo, ciudad y edad, además de datos funcionales de campaña de correo electrónico, como aperturas y clics. Con la interfaz de arrastrar y soltar, puede explorar los datos, determinar cómo funcionaron las campañas de correo electrónico en los segmentos más importantes de los clientes y medir su impacto en los destinatarios.

Gracias a su menú de arrastrar y soltar y a visualizaciones personalizables, la función de informes dinámicos permite combinar dimensiones, métricas y intervalo de tiempo en cualquier combinación, con un número ilimitado de desgloses y comparaciones.


**Temas relacionados:**

* [Lista de informes](../../reporting/using/defining-the-report-period.md)
* [Unidades organizativas](../../administration/using/organizational-units.md)
* [Vídeo de informes](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html) dinámicos

## Accessing dynamic reports {#accessing-dynamic-reports}

Se puede acceder a los informes:

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* In each program, campaign, and message, from the **Reports** button by clicking **Dynamic Reports** to only view the reports specific to the delivery.

   ![](assets/campaign_reports_description.png)

Ciertos informes no pueden estar disponibles inmediatamente después de la entrega, según el tiempo que se tarda en recopilar y procesar información.

Los informes dinámicos se dividen en dos categorías:

* **Las plantillas**, que se pueden modificar copiándolas con la opción **Guardar como** (**Proyecto &gt; Guardar como.**) en la plantilla.
* **Informes personalizados** (identificados en azul), que se pueden crear directamente haciendo clic en el **botón Crear nuevo proyecto** en la página principal **de informes** .

>[!NOTE]
>
>Los datos se filtran según las unidades de la organización.

![](assets/dynamic_report_overview.png)


## Dynamic reporting usage agreement {#dynamic-reporting-usage-agreement}

Los informes dinámicos permiten filtrar el informe según los datos de perfil con las dimensiones de perfil.

Las dimensiones de perfil solo se pueden mostrar y utilizar en los informes después de aceptar el acuerdo de uso dinámico de informes. De forma predeterminada, el acuerdo solo es visible y solo puede ser aceptado o rechazado por usuarios asignados con derechos de administración.

Este acuerdo permite la transferencia y almacenamiento en Estados Unidos de los siguientes datos de perfil: ciudad, país/región, estado, sexo y segmentos por edad.

Al aceptar este contrato, todos los datos europeos y no europeos se transferirán a Estados Unidos.

![](assets/pii_window.png)

Hay tres opciones disponibles:

* **[!UICONTROL Ask me later]**: Al hacer clic en Preguntarme más tarde, la ventana dejará de mostrarse durante 24 horas.
* **[!UICONTROL Accept]**: Al aceptar este contrato, autoriza a Adobe Campaign a recopilar la información de identificación personal de sus clientes y transferirlos a Estados Unidos.
* **[!UICONTROL Decline]**: Al rechazar el acuerdo, las dimensiones de perfil no aparecerán en los informes y la información de identificación personal de los clientes no se recopilará ni enviará.

This choice is not final, you can always change it by selecting **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** in **[!UICONTROL Administration]** &gt; **[!UICONTROL Application Settings]** &gt; **[!UICONTROL Options]**.

El valor puede cambiarse en cualquier momento. The value -1 corresponds to **[!UICONTROL Ask me later]**, 1 **[!UICONTROL Accept]** and 0 **[!UICONTROL Decline]**.

![](assets/pii_window_2.png)

