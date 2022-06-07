---
title: Interfaz de informes
description: Obtenga más información sobre la base de la interfaz de informes dinámicos y cómo navegar por las distintas pestañas y menús.
audience: reporting
content-type: reference
topic-tags: about-reporting
feature: Reporting
role: Leader
level: Beginner
exl-id: 37e9acff-9576-472f-9fdf-2c0f6da773d1
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 3%

---

# Interfaz de informes{#reporting-interface}

La barra de herramientas superior permite, por ejemplo, modificar, guardar o imprimir el informe.

![](assets/dynamic_report_toolbar.png)

Utilice la variable **Proyecto** para:

* **Abrir...**: Abre un informe o una plantilla creados anteriormente.
* **Guardar como...**: Duplica las plantillas para poder modificarlas.
* **Actualizar proyecto**: Actualiza el informe en función de los nuevos datos y los cambios realizados en los filtros.
* **Descargar CSV**: Exporta los informes a un archivo CSV.

La variable **Editar** le permite:

* **Deshacer**: Cancela la última acción del panel.
* **Borrar todo**: Elimina todos los paneles del tablero.

La variable **Insertar** permite personalizar los informes mediante la adición de gráficos y tablas al tablero:

* **Nuevo panel en blanco**: Agrega un nuevo panel en blanco al tablero.
* **Nueva forma libre**: Agrega una nueva tabla improvisada al tablero.
* **Nueva línea**: Agrega un nuevo gráfico de líneas al tablero.
* **Nueva barra**: Agrega un nuevo gráfico de barras al tablero.

**Temas relacionados:**

* [Adición de paneles](../../reporting/using/adding-panels.md)
* [Adición de visualizaciones](../../reporting/using/adding-visualizations.md)
* [Adición de componentes](../../reporting/using/adding-components.md)
* [Uso compartido de informes automáticamente con los interesados mediante correo electrónico](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)

## Pestañas {#tabs}

Las pestañas de la izquierda permiten crear el informe y filtrar los datos según sea necesario.

![](assets/dynamic_report_interface.png)

Estas pestañas le permiten acceder a los siguientes elementos:

* **[!UICONTROL Panels]**: agregue un panel en blanco o una forma libre al informe para filtrar los datos. Para obtener más información, consulte la sección Adición de paneles .
* **[!UICONTROL Visualizations]**: arrastre y suelte una selección de elementos de visualización para proporcionar al informe una dimensión gráfica. Para obtener más información, consulte la sección Adición de visualizaciones .
* **[!UICONTROL Components]**: personalice los informes con diferentes dimensiones, métricas, segmentos y períodos de tiempo.

## Barra de herramientas {#toolbar}

La barra de herramientas se encuentra encima del espacio de trabajo. Compuesto por diferentes pestañas, le permite, por ejemplo, modificar, guardar, compartir o imprimir su informe.

![](assets/dynamic_report_toolbar.png)

**Temas relacionados:**

* [Adición de paneles](../../reporting/using/adding-panels.md)
* [Adición de visualizaciones](../../reporting/using/adding-visualizations.md)
* [Adición de componentes](../../reporting/using/adding-components.md)

### Pestaña Proyecto {#project-tab}

![](assets/tab_project.png)

Utilice la variable **Proyecto** para:

* **Abrir...**: Abre un informe o una plantilla creados anteriormente.
* **Guardar como...**: Duplica las plantillas para poder modificarlas.
* **Actualizar proyecto**: Actualiza el informe en función de los nuevos datos y los cambios realizados en los filtros.
* **Descargar CSV**: Exporta los informes a un archivo CSV.
* **[!UICONTROL Print]**: Imprima el informe.

### Ficha Editar {#edit-tab}

![](assets/tab_edit.png)

La variable **Editar** le permite:

* **Deshacer**: Cancela la última acción del panel.
* **Borrar todo**: Elimina todos los paneles del tablero.

### Insertar, ficha {#insert-tab}

![](assets/tab_insert.png)

La variable **Insertar** permite personalizar los informes mediante la adición de gráficos y tablas al tablero:

* **Nuevo panel en blanco**: Agrega un nuevo panel en blanco al tablero.
* **Nueva forma libre**: Agrega una nueva tabla improvisada al tablero.
* **Nueva línea**: Agrega un nuevo gráfico de líneas al tablero.
* **Nueva barra**: Agrega un nuevo gráfico de barras al tablero.

### Compartir, ficha {#share-tab}

![](assets/tab_share_1.png)

La variable **[!UICONTROL Share]** le permite enviar sus informes con los usuarios de Adobe Campaign a través de correos electrónicos recurrentes o de una sola toma. Los usuarios de destino recibirán un correo electrónico con el informe adjunto.

* **[!UICONTROL Send report now]**: Envíe el informe a una lista de destinatarios seleccionados mediante un correo electrónico de una sola toma.

   1. En el **[!UICONTROL Send report]** , añada una descripción si es necesario.

      ![](assets/tab_share_4.png)

   1. Seleccione los destinatarios en la lista desplegable . Tenga en cuenta que no puede seleccionar usuarios fuera de la organización.
   1. Marque **[!UICONTROL Show scheduling options]** si desea enviar correos electrónicos recurrentes. Esto también se puede hacer seleccionando **[!UICONTROL Send Report on schedule]** en el **[!UICONTROL Share]** pestaña .
   1. Haga clic en **[!UICONTROL Send now]**. A continuación, los destinatarios recibirán un correo electrónico con el informe adjunto.

* **[!UICONTROL Send report on schedule]**: Programe el informe y envíe correos electrónicos recurrentes a sus destinatarios.

   1. En el **[!UICONTROL Send report]** , añada una descripción si es necesario.
   1. Seleccione los destinatarios en la lista desplegable . Tenga en cuenta que no puede seleccionar usuarios fuera de la organización.

      ![](assets/tab_share_5.png)

   1. Seleccione la fecha de inicio y finalización para configurar la validez del correo electrónico en la variable **[!UICONTROL Starting on]** y **[!UICONTROL Ending on]** campos.
   1. Elija la frecuencia con la que se enviará el correo electrónico.

      ![](assets/tab_share_2.png)

   1. Haga clic en **[!UICONTROL Send on schedule]**, los destinatarios recibirán su correo electrónico recurrente en función de la frecuencia elegida.

* **[!UICONTROL Scheduled reports]**: Busque y configure todo el informe programado.

   1. En el **[!UICONTROL Scheduled reports]** , busque todos los informes enviados recurrentes.

      ![](assets/tab_share_3.png)

   1. Si necesita eliminar uno de los informes programados, seleccione el informe programado que desee eliminar y haga clic en **[!UICONTROL Delete the section]**.
   1. Para configurar o comprobar los informes programados, haga clic directamente en el informe que debe cambiar.
   1. La variable **[!UICONTROL Edit scheduled report]** , ahora puede cambiar los destinatarios o la frecuencia del correo electrónico si es necesario.

Los usuarios de destino recibirán un correo electrónico con el informe adjunto directamente en sus bandejas de entrada. Los usuarios siempre pueden decidir dejar de recibir correos electrónicos recurrentes mediante un vínculo de baja disponible en cada correo electrónico recurrente.

**Temas relacionados:**

* [Uso compartido de informes automáticamente con los interesados mediante correo electrónico](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
