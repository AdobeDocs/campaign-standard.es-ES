---
solution: Campaign Standard
product: campaign
title: Introducción a los informes dinámicos
description: Con los informes dinámicos, arrastre y suelte las variables y dimensiones en el entorno improvisado y analice el éxito de las campañas.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: b471fddd49037770e33a113374afd60c2e79e69b
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 6%

---


# Introducción a los informes dinámicos {#about-dynamic-reports}

El Sistema de informes dinámico proporciona informes totalmente personalizables y en tiempo real. Agrega acceso a los datos de perfil, permitiendo la análisis demográfica por dimensiones de perfil como sexo, ciudad y edad, además de datos funcionales de campaña de correo electrónico como aperturas y clics. Con la interfaz de arrastrar y soltar, puede explorar datos, determinar el rendimiento de sus campañas de correo electrónico en relación con los segmentos de clientes más importantes y medir su impacto en los destinatarios.

>[!NOTE]
>
>Solo los usuarios con derechos de administración o con unidades organizativas establecidas en **Todo** pueden crear o guardar un nuevo informe. Para obtener más información, consulte [esta sección](../../administration/using/users-management.md).

## Acceso a informes dinámicos {#accessing-dynamic-reports}

Se puede acceder a los informes:

* En la página de inicio, seleccione la ficha **[!UICONTROL Reports]** en la barra superior o la tarjeta **[!UICONTROL Reports]** para acceder a los informes de todos los envíos.

   ![](assets/campaign_reports_access.png)

* En cada programa, campaña y mensaje, desde el botón **Informes** haga clic en **Informes dinámicos** para solo vista los informes específicos del envío.

   ![](assets/campaign_reports_description.png)

Ciertos informes no pueden estar disponibles inmediatamente después de un envío, según el tiempo que tarde en recopilar y procesar la información.

Los informes dinámicos se dividen en dos categorías:

* **Plantillas**, que se pueden modificar copiándolas mediante la opción  **Guardar** como (**Proyecto > Guardar como...)**) en la plantilla.
* **Los informes**  personalizados (identificados en azul), que se pueden crear directamente haciendo clic en el botón  **Crear nuevo** proyecto en la página  **** Informes.

>[!NOTE]
>
>Los datos se filtran según las unidades organizativas.

![](assets/dynamic_report_overview.png)

## Contrato de uso de sistema de informes dinámico {#dynamic-reporting-usage-agreement}

El propósito del acuerdo de uso de sistema de informes dinámico es funcionar como un consentimiento emergente para el procesamiento de datos. De forma predeterminada, el acuerdo solo es visible y solo pueden aceptarlo o rechazarlo los usuarios asignados con derechos de administración.

Hay tres opciones disponibles:

* **[!UICONTROL Ask me later]**:: Al hacer clic en  **Preguntarme más tarde**, la ventana dejará de mostrarse durante 24 horas. Hasta que no acepte o rechace el acuerdo, las dimensiones de perfil no aparecerán en los informes y la información de identificación personal de los clientes no se recopilará ni se enviará.
* **[!UICONTROL Accept]**:: Al aceptar este contrato, autoriza a Adobe Campaign a recopilar la información de identificación personal de sus clientes y a transferirla al sistema de informes o al centro de datos.
* **[!UICONTROL Decline]**:: Al rechazar el acuerdo, las dimensiones de perfil no aparecerán en los informes y la información de identificación personal de los clientes no se recopilará ni se enviará. Tenga en cuenta que en este caso, externalID se recopilará y se utilizará para identificar a los usuarios finales.

La siguiente tabla muestra lo que sucede después de aceptar este acuerdo según la región.

|  | Sistema de informes dinámico | Conector de Microsoft Dynamics 365 |
|---|---|---|
| América y APAC (Asia Pacífico) | **Función disponible**. <br>Toda la información lista para usar (por ejemplo, ciudad, país o región, estado, sexo y segmentos según la edad) y la información de perfiles personalizados ingresaron al centro de sistema de informes de EE.UU. Para obtener más información sobre las dimensiones de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Función disponible**. <br>Todos los campos de perfiles predeterminados y personalizados y los campos de evento de Adobe Campaign Standard se procesan en el centro de datos de EE. UU. |
| EMEA (Europa, Oriente Medio y África) | **Función disponible**. <br>Toda la información lista para usar (por ejemplo, ciudad, país o región, estado, sexo y segmentos según la edad) y la información de perfiles personalizados ingresaron al centro de sistema de informes de EMEA. Para obtener más información sobre las dimensiones de perfil, consulte esta [página](../../reporting/using/list-of-components-.md) | **Función disponible.** <br>Todos los campos de perfiles predeterminados y personalizados y los campos de evento de Adobe Campaign Standard procesados en el centro de datos de EMEA. <br>**[!UICONTROL Control data]**que contiene los datos de registro de Adobe I/O y las ID de los eventos de usuario final del cliente enviados y almacenados en el centro de datos de EE. UU. |

La siguiente tabla muestra lo que sucede después de rechazar este acuerdo en función de su región. Tenga en cuenta que, aunque rechace este acuerdo, seguirá estando disponible el sistema de informes en envíos y la integración con Microsoft Dynamics 365.

| Región | Sistema de informes dinámico | Conector de Microsoft Dynamics 365 |
|---|---|---|
| América y APAC (Asia Pacífico) | **Función disponible**. <br> No se ha insertado información de perfiles predeterminados y personalizados en el centro de sistema de informes de EE. UU., excepto ExternalID. | **Función disponible**. <br>No se han enviado al centro de datos de EE. UU. campos de perfil predeterminados o personalizados, a excepción del ID externo y el ID de Destinatario. <br>Todos los campos de Adobe Campaign Standard evento procesados en el centro de datos de EE. UU., excepto el ID de página espejo. <br>Para obtener más información sobre la integración de Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |
| EMEA (Europa, Oriente Medio y África) | **Función disponible**. <br>No se insertó información de perfiles predeterminados ni personalizados en el centro de sistema de informes de EMEA, excepto ExternalID. | **Función disponible.** <br>No se han enviado al centro de datos de EMEA campos de perfil predeterminados o personalizados, a excepción del ID externo y el ID de Destinatario. <br>Todos los campos de Adobe Campaign Standard evento procesados en el centro de datos de EMEA, excepto el ID de página espejo.  <br>**[!UICONTROL Control data]**que contiene los datos de registro de Adobe I/O y las ID de los eventos de usuario final del cliente enviados y almacenados en el centro de datos de EE. UU.<br>Para obtener más información sobre la integración de Microsoft Dynamics 365, consulte esta  [página](../../integrating/using/d365-acs-get-started.md). |

Esta opción no es definitiva, siempre puede cambiarla seleccionando **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** en **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

El valor se puede cambiar en cualquier momento. El valor 1 corresponde a **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** y 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
