---
title: Sincronizar datos entre Campaign y Microsoft Dynamics
description: Sincronizar datos entre Campaign y Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 66623c76-96aa-45cd-9637-19d8a9732c04
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---

# Sincronizar datos

Puede sincronizar tablas de Microsoft Dynamics 365 con métricas de marketing de Campaign y Campaign en Microsoft Dynamics 365. La sincronización se ejecuta a través de tres flujos de trabajo técnicos específicos: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Consulte esta sección para [más información](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Debe detener/iniciar el **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo para que se tengan en cuenta los cambios. [Más información](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Asignación de tablas de Microsoft Dynamics 365 a Campaign

La variable **[!UICONTROL Microsoft Dynamics 365 to Campaign]** muestra una lista de entidades en Microsoft Dynamics 365 y los recursos personalizados en Adobe Campaign con los que se sincronizarán. Puede agregar nuevas asignaciones, editar o eliminar asignaciones existentes.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

A continuación se muestra una descripción de cada una de las columnas de esta tabla:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: esta columna identifica qué entidad de Microsoft Dynamics 365 será la fuente de datos para la asignación.

* **[!UICONTROL CAMPAIGN TABLE]**: esta columna identifica qué recurso de Adobe Campaign será el destino de los datos para la asignación.

* **[!UICONTROL ACTIONS]**: a continuación se enumeran las posibles acciones:

   * Haga clic en el **[!UICONTROL Edit]** para editar esta asignación.

   * Utilice la variable  **[!UICONTROL Delete]** para eliminar una asignación de tabla.

   * Haga clic en el **[!UICONTROL Replay Data]** para volver a sincronizar todos los datos de la tabla de Microsoft Dynamics 365. Normalmente, la aplicación de integración solo sincroniza los datos de Microsoft Dynamics 365 que hayan cambiado recientemente.  Sin embargo, en algunos casos (por ejemplo, si ha realizado un cambio o ha cometido un error) es posible que desee volver a sincronizar todos los datos.  En estos casos, haría clic en este botón y, la próxima vez que detenga/inicie el **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo, los datos empezarían a sincronizarse.

      Si hace clic en el botón **[!UICONTROL Replay Data]** y las comprobaciones son correctas, el icono se desactivará: indica que los datos de este par de asignación de tabla se sincronizarán de nuevo con la siguiente ejecución del **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo.

      No puede seleccionar que se vuelvan a reproducir los datos cuando los siguientes sean verdaderos:

      * Si hay 2000 000 (o más) elementos en la métrica Backlog asociados con la variable **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo (mostrado en la **[!UICONTROL Workflows]** page)
      * Si hay 2.000.000 registros o más en la tabla de Microsoft Dynamics 365

      El número de registros que deben sincronizarse de nuevo varía. Si tiene un gran número de registros, puede tardar algún tiempo en completar el proceso de sincronización. Consulte la **[!UICONTROL Backlog]** en la variable **[!UICONTROL Workflows]** mientras la aplicación de integración trabaja para completar el proceso de sincronización.

      >[!IMPORTANT]
      >
      > Se recomienda detener el flujo de trabajo de integración al publicar cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Los cambios aplicables incluyen: actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificadores, etc. que la integración está utilizando actualmente.


## Crear una nueva asignación {#add-a-new-mapping}

Para crear una nueva asignación, siga los pasos a continuación:

1. en el **[!UICONTROL Microsoft Dynamics 365 to Campaign]** , haga clic en el botón **[!UICONTROL Add New Mapping]** botón.

1. Utilice las listas desplegables para seleccionar las tablas de Microsoft Dynamics 365 y Campaign que desea asignar.
La mayoría de las demás entradas de la página dependerán de las tablas que elija.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >No se puede asignar cada tabla más de una vez. Por lo tanto, verá que las selecciones desplegables no incluirán tablas que ya se hayan asignado.

1. Haga clic en **[!UICONTROL OK]** para confirmar: la aplicación necesitará un breve momento para leer la información de campo asociada con las tablas seleccionadas.

A continuación, puede continuar con la configuración de asignación. [Más información](#new-mapping-settings)

>[!IMPORTANT]
>
>Solo puede elegir las tablas de esta página cuando agrega la asignación por primera vez. Asegúrese de haber seleccionado las tablas correctas antes de hacer clic en el **[!UICONTROL Save]** botón: una vez guardados, los campos de selección de tabla se **solo lectura**.

### Editar una asignación existente

Si edita una asignación existente, verá que las selecciones de tabla no son editables.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Esto se hace por diseño, ya que las entradas más abajo en la página se basan en los campos asociados con estas tablas. Cambiar las tablas invalidaría todos los campos asociados con estas tablas.  Si desea cambiar la tabla a la que desea asignar, deberá volver a la página anterior, eliminar la asignación que desee cambiar y agregar una nueva asignación.

### Configuración de una asignación de tabla individual {#new-mapping-settings}

En esta sección, aprenderá a configurar un **single** asignación de una tabla de Microsoft Dynamics 365 a una tabla de Adobe Campaign.

Puede definir la siguiente configuración:

* **[!UICONTROL Tables]**: esta sección enumera el nombre de la tabla de Microsoft Dynamics 365 y la tabla de Campaign a la que se asignará.
* **[!UICONTROL Field Mappings]**: obtenga más información en [esta sección](#field-mappings)
* **[!UICONTROL Field Replacements]**: obtenga más información en [esta sección](#field-replacements)
* **[!UICONTROL Filters]**: obtenga más información en [esta sección](#filters)
* **[!UICONTROL Advanced Settings]**: obtenga más información en [esta sección](#advanced-settings)

### Asignaciones de campos {#field-mappings}

#### Claves principales

Al agregar una nueva asignación de Microsoft Dynamics 365 a la tabla de Campaign, debe identificar el campo de ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La clave principal de Microsoft Dynamics 365 es de solo lectura porque la aplicación la detectará.

Para Campaign, debe seleccionar qué campo será la clave única. Debe configurarse como un [Recurso personalizado CRM ID](../../developing/using/uc-calling-resource-id-key.md) y no deben tener duplicados.

>[!NOTE]
>
>Solo podrá elegir el campo ID de la tabla cuando haya seleccionado **[!UICONTROL Add New Mapping]**. Si hace clic en el botón editar para editar una asignación de tabla existente, el campo ID será de solo lectura.

Las claves principales siempre serán los primeros nombres de campo enumerados en la variable **[!UICONTROL Field Mappings]** para obtener más información. Como recordatorio, el siguiente icono aparece a la derecha para recordarle que estas son las claves principales.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Añadir otras asignaciones de campos

La variable **[!UICONTROL Field Mappings]** permite agregar asignaciones de campo que no sean las claves principales. Para agregar una nueva asignación de un campo de Microsoft Dynamics 365 a Adobe Campaign, haga clic en el botón **[!UICONTROL Add new field mapping]** botón.

Seleccione los campos Microsoft Dynamics 365 y Campaign en las listas:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Estas listas contienen los nombres de campo asociados con las tablas de Microsoft Dynamics 365 y Campaign que ha seleccionado en la parte superior de la página.

La variable **[!UICONTROL Apply updates]** el conmutador le permite controlar si las actualizaciones de este campo se propagarán de Microsoft Dynamics 365 a Campaign:
* Si está encendido ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), las actualizaciones de los valores de Microsoft Dynamics 365 se propagarán a Adobe Campaign a medida que ocurran las actualizaciones.

* Si se ha apagado ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), el valor se propagará cuando los datos se carguen (o se reproduzcan) por primera vez, pero las actualizaciones incrementales del campo en Microsoft Dynamics 365 no se propagarán.

>[!NOTE]
>
>Haga clic en el **[!UICONTROL Apply updates]** encabezado de columna que se va a actualizar **all** de los interruptores en encendido o apagado.

Al seleccionar valores de campo, verá que el tipo de datos aparece debajo de los menús desplegables.   Esto se debe tener en cuenta al asignar valores de un campo a otro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> No se pueden asignar varios campos de Microsoft Dynamics 365 a un solo campo de Campaign.

### Sustituciones de campos {#field-replacements}

Utilice la variable **[!UICONTROL Add New Field Replacement]** para definir un nuevo reemplazo de campo.

Los reemplazos de campo le permiten identificar:

* un nombre de campo de Microsoft Dynamics 365 (que se ha añadido anteriormente en la sección asignaciones de campo),
* un valor existente (que existe en Microsoft Dynamics 365), y
* un nuevo valor para escribir en Adobe Campaign

Se proporcionará una lista desplegable para los valores booleanos, de lista de selección y de lista desglosada. Se utilizará un cuadro de texto para otros tipos numéricos y de cadenas.

### Filtros {#filters}

Utilice la variable **[!UICONTROL Add New Filter]** para seleccionar qué registros de Microsoft Dynamics 365 se propagarán a Campaign. Puede elegir cualquier campo asociado con un registro para agregarlo a los filtros (no es necesario agregar el nombre del campo a las asignaciones de campo).

Para especificar un filtro, rellene la siguiente información:

* Nombre del campo de Microsoft Dynamics 365
* un valor de comparación, y
* un valor (de Microsoft Dynamics 365) Si el nombre del campo, la comparación y el valor se evalúan como true para un registro determinado, el registro se propagará a Adobe Campaign.

Puede elegir cómo se evalúan estos filtros estableciendo la entrada etiquetada **[!UICONTROL Choose the filter comparison operator]**.  Si elige **Y**, todos los filtros deben ser verdaderos para que un registro se propague a Campaign. Si elige **O**, el registro se propagará si alguno de ellos evalúa como verdadero.

La opción **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controla si desea que se eliminen de Campaign los registros que se han filtrado. Si selecciona **No** a continuación, los registros permanecerán en Adobe Campaign. Select **Sí** para que la lógica de integración los elimine.

>[!NOTE]
>
> Si no se agregan filtros, todos los registros modificados se propagarán a Adobe Campaign.

### Configuración avanzada {#advanced-settings}

Al configurar una asignación, puede configurar las siguientes opciones adicionales:

* Configure las variables **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** a **Sí**, si desea propagar las eliminaciones que se producen en Microsoft Dynamics 365 al campo correspondiente de Adobe Campaign (en función de la asignación de nombres de campo). Select **No** para ignorar las eliminaciones en Microsoft Dynamics 365.

* Configure las variables **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** a **No** si desea propagar a Campaign el valor de visualización asociado a una lista de selección de Microsoft Dynamics 365. Select **Sí** para propagar el valor técnico.

## Sincronizar eventos de marketing de Campaign con Microsoft Dynamics 365

La variable **[!UICONTROL Campaign to Microsoft Dynamics 365]** permite identificar qué eventos de marketing por correo electrónico se asignarán de Adobe Campaign a Microsoft Dynamics 365.

Las cuatro métricas que puede controlar son: **Envíos**, **Clics**, **Aperturas** y **Devoluciones**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Select **Sí** para confirmar que desea que los eventos de ese tipo fluyan a Microsoft Dynamics 365.

Haga clic en [here](../../integrating/using/d365-acs-self-service-app-workflows.md) para obtener más información sobre estos flujos de eventos de correo electrónico.

## Flujo de trabajo de inclusión/exclusión {#opt-in-out-wf}

La variable **Inclusión/exclusión** el flujo de trabajo le permite identificar el flujo de información de inclusión/exclusión entre Microsoft Dynamics 365 y Adobe Campaign. Esto supone que los datos están asociados a la entidad &quot;contact&quot; de Microsoft Dynamics 365 y al &quot;perfil&quot; de recursos de Adobe Campaign.

Obtenga más información sobre la administración de exclusión en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Recuerde que debe hacer clic en &quot;Guardar&quot; para guardar las selecciones. Recuerde también que debe detener el **Campaña a Microsoft Dynamics 365** y, a continuación, haga clic en reproducir para la integración para incorporar los cambios.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Dirección de sincronización de la inclusión/exclusión

A continuación se muestra la lista de opciones disponibles para sincronizar datos:

* **[!UICONTROL Disabled]**: cuando se selecciona esta opción, no se moverá ninguna información de inclusión/exclusión entre Adobe Campaign y Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: esta opción se utiliza para el flujo de inclusión/exclusión desde Microsoft Dynamics 365 a Adobe Campaign solamente. La aplicación de integración no permite configurar el flujo en esta pantalla; en su lugar, haga clic en el botón **[!UICONTROL Save button]** y vaya a la **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo. En este flujo de trabajo, puede editar la asignación de tablas de contactos/perfiles para identificar cómo desea que se asignen los campos de inclusión/exclusión.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: esta opción hace visible la variable **Asignaciones** para obtener más información. Estas entradas le permiten definir qué campos de Adobe Campaign asignarán datos a qué campos de Microsoft Dynamics 365. Esto significa que si se actualiza manualmente un valor en Microsoft Dynamics 365, el valor de Adobe Campaign sobrescribirá su valor si esto ocurre.

* **[!UICONTROL Bidirectional]**: esta opción hace visible la variable **Asignaciones** para obtener más información. Estos pares identificarán qué campos de Microsoft Dynamics 365 y Adobe Campaign se asignarán entre sí. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Asignaciones

Esta sección solo se aplica cuando el campo de dirección de sincronización de inclusión/exclusión está establecido en **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. Puede definir qué campos de Microsoft Dynamics 365 se asignan a qué entradas de Adobe Campaign.

Los nombres de campo de Microsoft Dynamics 365 incluyen todos los que son del tipo **booleano**.

Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos de inclusión/exclusión. Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos de inclusión/exclusión. **El conjunto de valores de esta lista no se puede cambiar**.
