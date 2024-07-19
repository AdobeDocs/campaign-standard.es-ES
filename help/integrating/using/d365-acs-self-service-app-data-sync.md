---
title: Sincronización de datos entre Campaign y Microsoft Dynamics
description: Sincronización de datos entre Campaign y Dynamics
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
source-wordcount: '1839'
ht-degree: 0%

---

# Sincronizar datos

Puede sincronizar tablas de Microsoft Dynamics 365 a las métricas de marketing de Campaign y Campaign a Microsoft Dynamics 365. La sincronización se ejecuta mediante tres flujos de trabajo técnicos dedicados: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Consulte esta sección para [obtener más información](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Debe detener o iniciar el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para que se tengan en cuenta los cambios. [Más información](../../integrating/using/d365-acs-self-service-app-workflows.md)
>

## Asignación de tablas de Microsoft Dynamics 365 a Campaign

La página **[!UICONTROL Microsoft Dynamics 365 to Campaign]** muestra una lista de entidades en Microsoft Dynamics 365 y los recursos personalizados en Adobe Campaign con los que se sincronizarán. Puede agregar nuevas asignaciones, editar o eliminar las existentes.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top.png)

Esta es una descripción de cada una de las columnas de esta tabla:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**: esta columna identifica qué entidad de Microsoft Dynamics 365 será el origen de los datos para la asignación.

* **[!UICONTROL CAMPAIGN TABLE]**: esta columna identifica qué recurso de Adobe Campaign será el destino de los datos para la asignación.

* **[!UICONTROL ACTIONS]**: a continuación se enumeran las posibles acciones:

   * Haga clic en el icono **[!UICONTROL Edit]** para editar esta asignación.

   * Utilice el icono **[!UICONTROL Delete]** para eliminar una asignación de tabla.

   * Haga clic en el icono **[!UICONTROL Replay Data]** para volver a sincronizar todos los datos de la tabla de Microsoft Dynamics 365. Normalmente, la aplicación de integración solo sincroniza los datos de Microsoft Dynamics 365 que han cambiado recientemente.  Sin embargo, en algunos casos (por ejemplo, si ha realizado un cambio o ha cometido un error), es posible que desee volver a sincronizar todos los datos.  En estos casos, haría clic en este botón y, la próxima vez que detenga o inicie el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, los datos comenzarán a sincronizarse.

     Si hace clic en el botón **[!UICONTROL Replay Data]** y las comprobaciones se realizan correctamente, el icono se deshabilitará: indica que los datos de este par de asignación de tabla se volverán a sincronizar con la siguiente ejecución del flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

     No puede seleccionar la reproducción de los datos cuando se cumplen las siguientes condiciones:

      * Si hay 2.000.000 (o más) elementos en la métrica Registro de pendientes asociados con el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (mostrado en la página **[!UICONTROL Workflows]**)
      * Si hay 2 000 000 o más registros en la tabla de Microsoft Dynamics 365

     El número de registros que deben volver a sincronizarse varía. Si tiene un gran número de registros, puede tardar algún tiempo en completar el proceso de sincronización. Consulte la métrica **[!UICONTROL Backlog]** en la página **[!UICONTROL Workflows]**, ya que la aplicación de integración funciona para completar el proceso de sincronización.

     >[!IMPORTANT]
     >
     > Se recomienda detener el flujo de trabajo de integración al publicar cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Los cambios aplicables incluyen: actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificadores, etc. que utiliza actualmente la integración.
     >

## Creación de una nueva asignación {#add-a-new-mapping}

Para crear una nueva asignación, siga los pasos a continuación:

1. en la página **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, haga clic en el botón **[!UICONTROL Add New Mapping]**.

1. Utilice las listas desplegables para seleccionar las tablas de Microsoft Dynamics 365 y Campaign que desea asignar.
La mayoría de las demás entradas de la página dependerán de las tablas que elija.

   ![](assets/do-not-localize/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >No se puede asignar cada tabla más de una vez. Por lo tanto, observará que las selecciones desplegables no incluyen tablas que ya se han asignado.

1. Haga clic en **[!UICONTROL OK]** para confirmar: la aplicación necesitará un breve momento para leer la información de campo asociada con las tablas seleccionadas.

A continuación, puede continuar con la configuración de asignación. [Más información](#new-mapping-settings)

>[!IMPORTANT]
>
>Solo puede elegir las tablas de esta página cuando agregue la asignación por primera vez. Asegúrese de haber seleccionado las tablas correctas antes de hacer clic en el botón **[!UICONTROL Save]**: una vez guardado, los campos de selección de tabla serán **de solo lectura**.

### Editar una asignación existente

Si edita una asignación existente, verá que las selecciones de tabla no se pueden editar.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-table-read-only.png)

Esto es por diseño, ya que las entradas más abajo en la página se basan en los campos asociados con estas tablas. Si se cambiaran las tablas, todos los campos asociados con estas tablas serían no válidos.  Si desea cambiar la tabla a la que desea asignar, deberá volver a la página anterior, eliminar la asignación que desee cambiar y agregar una nueva asignación.

### Configuración de una asignación de tabla individual {#new-mapping-settings}

En esta sección aprenderá a configurar una asignación **única** de una tabla de Microsoft Dynamics 365 a una tabla de Adobe Campaign.

Puede definir la siguiente configuración:

* **[!UICONTROL Tables]**: en esta sección se muestra el nombre de la tabla de Microsoft Dynamics 365 y la tabla de Campaign a la que se asignará.
* **[!UICONTROL Field Mappings]**: obtenga más información en [esta sección](#field-mappings)
* **[!UICONTROL Field Replacements]**: obtenga más información en [esta sección](#field-replacements)
* **[!UICONTROL Filters]**: obtenga más información en [esta sección](#filters)
* **[!UICONTROL Advanced Settings]**: obtenga más información en [esta sección](#advanced-settings)

### Asignaciones de campos {#field-mappings}

#### Claves principales

Al añadir una nueva asignación de tabla de Microsoft Dynamics 365 a Campaign, debe identificar el campo de ID.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La clave principal de Microsoft Dynamics 365 es de solo lectura porque la aplicación la detectará.

Para Campaign, debe seleccionar qué campo es la clave única. Debe configurarse como un [recurso personalizado de ID de CRM](../../developing/using/uc-calling-resource-id-key.md) y no debe tener duplicados.

>[!NOTE]
>
>Solo podrá elegir el campo de identificación en la tabla cuando haya seleccionado **[!UICONTROL Add New Mapping]**. Si hace clic en el botón Editar para editar una asignación de tabla existente, el campo de ID será de solo lectura.

Las claves principales siempre serán los primeros nombres de campo enumerados en la sección **[!UICONTROL Field Mappings]**. Como recordatorio, el siguiente icono se muestra a la derecha para recordarle que estas son las claves principales.

![](assets/do-not-localize/d365-to-acs-icon-primary-key.png)

#### Agregar otras asignaciones de campo

La sección **[!UICONTROL Field Mappings]** le permite agregar asignaciones de campo que no sean las Claves principales. Para agregar una nueva asignación de un campo de Microsoft Dynamics 365 a Adobe Campaign, haga clic en el botón **[!UICONTROL Add new field mapping]**.

Seleccione los campos Microsoft Dynamics 365 y Campaign en las listas:

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Estas listas contienen los nombres de campo asociados con las tablas de Microsoft Dynamics 365 y Campaign seleccionadas en la parte superior de la página.

El conmutador **[!UICONTROL Apply updates]** le permite controlar si las actualizaciones de este campo se propagarán de Microsoft Dynamics 365 a Campaign:
* Si se activa ![](assets/do-not-localize/d365-to-acs-icon-switch-on.png), las actualizaciones de los valores de Microsoft Dynamics 365 se propagarán a Adobe Campaign a medida que se produzcan las actualizaciones.

* Si desactivó ![](assets/do-not-localize/d365-to-acs-icon-switch-off.png), el valor se propagará cuando los datos se carguen (o se reproduzcan) por primera vez, pero no se propagarán las actualizaciones incrementales del campo en Microsoft Dynamics 365.

>[!NOTE]
>
>Haga clic en el encabezado de la columna **[!UICONTROL Apply updates]** para actualizar **todos** los conmutadores a activados o desactivados.
>

Al seleccionar valores de campo, verá que el tipo de datos aparece debajo de los menús desplegables.   Esto es algo que se debe tener en cuenta al asignar valores de un campo a otro.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> No se pueden asignar varios campos de Microsoft Dynamics 365 a un único campo de Campaign.

### Reemplazos de campos {#field-replacements}

Utilice el botón **[!UICONTROL Add New Field Replacement]** para definir un nuevo reemplazo de campo.

Los reemplazos de campo le permiten identificar:

* un nombre de campo de Microsoft Dynamics 365 (que se ha agregado anteriormente en la sección de asignaciones de campos),
* un valor existente (que existe en Microsoft Dynamics 365), y
* un nuevo valor para escribir en Adobe Campaign

Se proporcionará una lista desplegable para la lista desplegable, la enumeración y los valores booleanos. Se utilizará un cuadro de texto para otros tipos numéricos y de cadena.

### Filtros {#filters}

Utilice el botón **[!UICONTROL Add New Filter]** para seleccionar qué registros de Microsoft Dynamics 365 se propagarán a Campaign. Puede elegir cualquier campo asociado a un registro para agregarlo a los filtros (no es necesario agregar el nombre del campo a las asignaciones de campos).

Para especificar un filtro, rellene la siguiente información:

* Nombre de campo de Microsoft Dynamics 365
* un valor de comparación, y
* un valor (de Microsoft Dynamics 365)
Si el nombre de campo, la comparación y el valor se evalúan como true para un registro determinado, el registro se propagará a Adobe Campaign.

Puede elegir cómo se evalúan estos filtros estableciendo la entrada con la etiqueta **[!UICONTROL Choose the filter comparison operator]**.  Si elige **And**, todos los filtros deben ser verdaderos para que un registro se propague a Campaign. Si elige **Or**, el registro se propagará si alguno de ellos se evalúa como verdadero.

La opción **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controla si desea que se eliminen de Campaign los registros que se han filtrado. Si selecciona **No**, los registros permanecerán en Adobe Campaign. Seleccione **Yes** para que la lógica de integración los elimine.

>[!NOTE]
>
> Si no se agregan filtros, todos los registros que se hayan modificado se propagarán a Adobe Campaign.
>

### Configuración avanzada {#advanced-settings}

Puede configurar las siguientes opciones adicionales al configurar una asignación:

* Establezca la opción **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** en **Sí**, si desea propagar las eliminaciones que se produzcan en Microsoft Dynamics 365 al campo correspondiente en Adobe Campaign (según la asignación de nombre de campo). Seleccione **No** para omitir las eliminaciones en Microsoft Dynamics 365.

* Establezca la opción **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** en **No** si desea propagar a Campaign el valor de visualización asociado con una lista de selección de Microsoft Dynamics 365. Seleccione **Yes** para propagar el valor técnico.

## Sincronización de eventos de marketing de Campaign con Microsoft Dynamics 365

La página **[!UICONTROL Campaign to Microsoft Dynamics 365]** le permite identificar qué eventos de marketing por correo electrónico se asignarán de Adobe Campaign a Microsoft Dynamics 365.

Las cuatro métricas que puede controlar son: **Envíos**, **Clics**, **Abrir** y **Devoluciones**.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-egress.png)

Seleccione **Sí** para confirmar que desea que los eventos de ese tipo fluyan a Microsoft Dynamics 365.

Haga clic [aquí](../../integrating/using/d365-acs-self-service-app-workflows.md) para obtener más información sobre estos flujos de eventos de correo electrónico.

## Flujo de trabajo de Opt-in/out {#opt-in-out-wf}

El flujo de trabajo **Inclusión/Exclusión** le permite identificar el flujo de información de inclusión/exclusión entre Microsoft Dynamics 365 y Adobe Campaign. Esto supone que los datos están asociados con la entidad de Microsoft Dynamics 365 &quot;contacto&quot; y el recurso de Adobe Campaign &quot;perfil&quot;.

Obtenga más información acerca de la administración de la exclusión en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Recuerde que debe hacer clic en &quot;Guardar&quot; para guardar las selecciones. Recuerde también que debe detener el flujo de trabajo de **Campaign to Microsoft Dynamics 365** y luego hacer clic en Reproducir para que la integración incorpore los cambios.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Dirección de sincronización de inclusión/exclusión

A continuación se muestra la lista de opciones disponibles para sincronizar datos:

* **[!UICONTROL Disabled]**: cuando se selecciona esta opción, no se moverá ninguna información de inclusión/exclusión entre Adobe Campaign y Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**: esta opción se usa para el flujo de inclusión/exclusión de Microsoft Dynamics 365 a Adobe Campaign únicamente. La aplicación de integración no le permitirá configurar el flujo en esta pantalla; en su lugar, haga clic en **[!UICONTROL Save button]** y vaya al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. En este flujo de trabajo, puede editar la asignación de contactos/tablas de perfil para identificar cómo desea que se asignen los campos de inclusión/exclusión.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**: esta opción hará visible la sección **Asignaciones**. Estas entradas le permitirán definir qué campos de Adobe Campaign asignarán datos a qué campos de Microsoft Dynamics 365. Esto significa que si actualiza manualmente un valor en Microsoft Dynamics 365, su valor se sobrescribirá con el valor de Adobe Campaign si cambia.

* **[!UICONTROL Bidirectional]**: esta opción hará visible la sección **Asignaciones**. Estos pares identificarán qué campos de Microsoft Dynamics 365 y Adobe Campaign se asignarán entre sí. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Asignaciones

Esta sección solo se aplica cuando el campo Opt-in/out synchronization direction está establecido en **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. Puede definir qué campos de Microsoft Dynamics 365 se asignan a qué entradas de Adobe Campaign.

Los nombres de campo de Microsoft Dynamics 365 incluyen todos los del tipo **booleano**.

Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos de inclusión/exclusión. Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos de inclusión/exclusión. **No se puede cambiar el conjunto de valores de esta lista**.
