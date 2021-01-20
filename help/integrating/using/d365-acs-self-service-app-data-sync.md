---
title: Sincronizar datos entre Campaña y Microsoft Dynamics
description: Sincronizar datos entre Campaña y Dynamics
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '1795'
ht-degree: 0%

---


# Sincronizar datos

Puede sincronizar tablas de Microsoft Dynamics 365 con métricas de marketing de Campaña y Campaña con Microsoft Dynamics 365. La sincronización se ejecuta mediante tres flujos de trabajo técnicos dedicados: **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, **[!UICONTROL Campaign to Microsoft Dynamics 365]**, **[!UICONTROL Opt-In/Out]**. Consulte esta sección para [obtener más información](../../integrating/using/d365-acs-self-service-app-workflows.md).

>[!IMPORTANT]
>Debe detener/inicio el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para tener en cuenta los cambios. [Más información](../../integrating/using/d365-acs-self-service-app-workflows.md)


## Asignar tablas de Microsoft Dynamics 365 a Campaña

La página **[!UICONTROL Microsoft Dynamics 365 to Campaign]** muestra una lista de entidades en Microsoft Dynamics 365 y los recursos personalizados en Adobe Campaign con los que se sincronizarán. Puede agregar asignaciones nuevas, editar o eliminar asignaciones existentes.

![](assets/d365-to-acs-ui-page-ingress-top.png)

Esta es una descripción de cada una de las columnas de esta tabla:

* **[!UICONTROL MICROSOFT DYNAMICS 365 TABLE]**:: esta columna identifica qué entidad de Microsoft Dynamics 365 será la fuente de datos para la asignación.

* **[!UICONTROL CAMPAIGN TABLE]**:: esta columna identifica qué recurso de Adobe Campaign será el destino de los datos para la asignación.

* **[!UICONTROL ACTIONS]**:: a continuación se enumeran las posibles acciones:

   * Haga clic en el icono **[!UICONTROL Edit]** para editar esta asignación.

   * Utilice el icono **[!UICONTROL Delete]** para eliminar una asignación de tabla.

   * Haga clic en el icono **[!UICONTROL Replay Data]** para volver a sincronizar todos los datos de la tabla de Microsoft Dynamics 365. Normalmente, la aplicación de integración solo sincronizará los datos de Microsoft Dynamics 365 que hayan cambiado recientemente.  Sin embargo, en algunos casos (por ejemplo, si ha realizado un cambio o ha cometido un error) es posible que quiera que todos los datos se vuelvan a sincronizar.  En estos casos, debe hacer clic en este botón y, la próxima vez que detenga o inicio el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, los datos tendrán inicios para sincronizarse.

      Si hace clic en el botón **[!UICONTROL Replay Data]** y las comprobaciones se realizan correctamente, el icono se desactivará: indica que los datos de este par de asignación de tabla se volverán a sincronizar con la siguiente ejecución del flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**.

      No se puede seleccionar volver a reproducir los datos cuando se cumple el siguiente valor:

      * Si hay 2.000.000 (o más) elementos en la métrica Backlog asociados con el flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** (se muestra en la página **[!UICONTROL Workflows]**)
      * Si hay 2.000.000 o más registros en la tabla de Microsoft Dynamics 365

      El número de registros que se deben volver a sincronizar varía. Si tiene un gran número de registros, puede tardar algún tiempo en completar el proceso de sincronización. Consulte la métrica **[!UICONTROL Backlog]** en la página **[!UICONTROL Workflows]** mientras la aplicación de integración trabaja para completar el proceso de sincronización.

      >[!IMPORTANT]
      >
      > Es muy recomendable que detenga el flujo de trabajo de integración al publicar cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Los cambios aplicables incluyen: actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificadores, etc. que la integración está utilizando actualmente.




## Crear una nueva asignación {#add-a-new-mapping}

Para crear una nueva asignación, siga los pasos a continuación:

1. en la página **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, haga clic en el botón **[!UICONTROL Add New Mapping]**.

1. Utilice las listas desplegables para seleccionar las tablas de Campaña y Microsoft Dynamics 365 que se van a asignar.
La mayoría de las demás entradas de la página dependerán de las tablas que elija.

   ![](assets/d365-to-acs-ui-page-ingress-choose-tables.png)

   >[!NOTE]
   >No puede asignar cada tabla más de una vez. Por lo tanto, observará que las selecciones desplegables no incluirán tablas que ya se hayan asignado.

1. Haga clic **[!UICONTROL OK]** para confirmar: la aplicación necesitará un breve momento para leer la información de campo asociada con las tablas seleccionadas.

A continuación, puede continuar con la configuración de asignación. [Más información](#new-mapping-settings)

>[!IMPORTANT]
>
>Solo puede elegir las tablas de esta página cuando vaya a agregar la asignación por primera vez. Asegúrese de que ha seleccionado las tablas correctas antes de hacer clic en el botón **[!UICONTROL Save]**: una vez guardados, los campos de selección de tabla serán **de sólo lectura**.

### Editar una asignación existente

Si edita una asignación existente, verá que las selecciones de tabla no son editables.

![](assets/d365-to-acs-ui-page-ingress-table-read-only.png)

Esto se hace por diseño porque las entradas más abajo en la página se basan en los campos asociados con estas tablas. Si se cambiaran las tablas, todos los campos asociados con estas tablas quedarían invalidados.  Si desea cambiar la tabla a la que desea asignar, deberá volver a la página anterior, eliminar la asignación que desee cambiar y agregar una nueva asignación.

### Configurar una asignación de tabla individual {#new-mapping-settings}

En esta sección aprenderá a configurar una **asignación única** de una tabla de Microsoft Dynamics 365 en una tabla de Adobe Campaign.

Puede definir la siguiente configuración:

* **[!UICONTROL Tables]**:: esta sección lista el nombre de la tabla de Microsoft Dynamics 365 y la tabla de Campañas a la que se asignará.
* **[!UICONTROL Field Mappings]**:: obtener más información en  [esta sección](#field-mappings)
* **[!UICONTROL Field Replacements]**:: obtener más información en  [esta sección](#field-replacements)
* **[!UICONTROL Filters]**:: obtener más información en  [esta sección](#filters)
* **[!UICONTROL Advanced Settings]**:: obtener más información en  [esta sección](#advanced-settings)

### Asignaciones de campos {#field-mappings}

#### Claves principales

Al agregar un nuevo Microsoft Dynamics 365 a la asignación de tabla de Campaña, debe identificar el campo de ID.

![](assets/d365-to-acs-ui-page-ingress-mappings-first-key.png)

La clave principal de Microsoft Dynamics 365 es de solo lectura porque la aplicación la detectará.

Para la Campaña, debe seleccionar qué campo será la clave única. Debe configurarse como un [recurso personalizado de ID de CRM](../../developing/using/uc-calling-resource-id-key.md) y no debe tener duplicados.

>[!NOTE]
>
>Solo podrá elegir el campo de ID de la tabla cuando haya seleccionado **[!UICONTROL Add New Mapping]**. Si hace clic en el botón de edición para editar una asignación de tabla existente, el campo ID será de sólo lectura.

Las claves principales siempre serán los primeros nombres de campo enumerados en la sección **[!UICONTROL Field Mappings]**. Como recordatorio, el siguiente icono aparece a la derecha para recordarle que estas son las claves principales.

![](assets/d365-to-acs-icon-primary-key.png)

#### Añadir otras asignaciones de campos

La sección **[!UICONTROL Field Mappings]** le permite agregar asignaciones de campo que no sean las claves principales. Para agregar una nueva asignación de un campo de Microsoft Dynamics 365 a Adobe Campaign, haga clic en el botón **[!UICONTROL Add new field mapping]**.

Seleccione Microsoft Dynamics 365 y campos de Campaña en las listas:

![](assets/d365-to-acs-ui-page-ingress-new-field-mapping.png)

Estas listas contienen los nombres de campo asociados con las tablas de Campaña y Microsoft Dynamics 365 que ha seleccionado en la parte superior de la página.

El conmutador **[!UICONTROL Apply updates]** permite controlar si las actualizaciones de este campo se propagarán de Microsoft Dynamics 365 a Campaña:
* Si se activa ![](assets/d365-to-acs-icon-switch-on.png), las actualizaciones de los valores de Microsoft Dynamics 365 se propagarán a Adobe Campaign a medida que se produzcan las actualizaciones.

* Si desactiva ![](assets/d365-to-acs-icon-switch-off.png), el valor se propagará cuando los datos se carguen inicialmente (o se vuelvan a reproducir), pero las actualizaciones incrementales en el campo de Microsoft Dynamics 365 no se propagarán.

>[!NOTE]
>
>Haga clic en el encabezado de la columna **[!UICONTROL Apply updates]** para actualizar **todo** de los switches para activarlos o desactivarlos.


Al seleccionar valores de campo, verá que el tipo de datos se muestra debajo de los menús desplegables.   Esto es algo que hay que tener en cuenta al asignar valores de un campo a otro.

![](assets/d365-to-acs-ui-page-ingress-mappings-fields-selected.png)

>[!NOTE]
>
> No se pueden asignar varios campos de Microsoft Dynamics 365 a un solo campo de Campaña.

### Sustituciones de campo {#field-replacements}

Utilice el botón **[!UICONTROL Add New Field Replacement]** para definir un nuevo reemplazo de campo.

Los reemplazos de campo permiten identificar:

* un nombre de campo de Microsoft Dynamics 365 (que se ha agregado arriba en la sección de asignaciones de campo),
* un valor existente (que existe en Microsoft Dynamics 365) y
* un nuevo valor para escribir en Adobe Campaign

Se proporcionará una lista desplegable para los valores de lista de selección, lista desglosada y booleano. Se utilizará un cuadro de texto para otros tipos numéricos y de cadenas.

### Filtros {#filters}

Utilice el botón **[!UICONTROL Add New Filter]** para seleccionar qué registros de Microsoft Dynamics 365 se propagarán a la Campaña. Puede elegir cualquier campo asociado a un registro para agregarlo a los filtros (el nombre del campo no necesita agregarse a las asignaciones de campo).

Para especificar un filtro, rellene la siguiente información:

* Nombre de campo de Microsoft Dynamics 365
* un valor de comparación, y
* un valor (de Microsoft Dynamics 365)
Si el nombre del campo, la comparación y el valor se evalúan como true para un registro determinado, el registro se propagará a Adobe Campaign.

Puede elegir cómo se evalúan estos filtros configurando la entrada con la etiqueta **[!UICONTROL Choose the filter comparison operator]**.  Si elige **And**, todos los filtros deben ser verdaderos para que un registro se propague a la Campaña. Si elige **O**, el registro se propagará si alguno de ellos se evalúa como verdadero.

La opción **[!UICONTROL Do you want to delete records in Adobe Campaign Standard that will be filtered out from Microsoft Dynamics 365?]** controla si desea que los registros que han filtrado se eliminen de la Campaña. Si selecciona **No**, los registros permanecerán en Adobe Campaign. Seleccione **Sí** para que la lógica de integración los elimine.

>[!NOTE]
>
> Si no se agregan filtros, todos los registros que se hayan modificado se propagarán a Adobe Campaign.


### Configuración avanzada {#advanced-settings}

Puede configurar las siguientes opciones adicionales al configurar una asignación:

* Establezca la opción **[!UICONTROL Apply deletes in Microsoft Dynamics 365 to Campaign?]** en **Sí**, si desea propagar las eliminaciones que se producen en Microsoft Dynamics 365 al campo correspondiente en Adobe Campaign (según la asignación de nombres de campo). Seleccione **No** para omitir las eliminaciones en Microsoft Dynamics 365.

* Establezca la opción **[!UICONTROL Use technical values in Microsoft Dynamics 365 picklists?]** en **No** si desea propagar a la Campaña el valor de visualización asociado a una lista de selección de Microsoft Dynamics 365. Seleccione **Sí** para propagar el valor técnico.

## Sincronizar eventos de marketing de Campaña con Microsoft Dynamics 365

La página **[!UICONTROL Campaign to Microsoft Dynamics 365]** permite identificar qué eventos de mercadotecnia por correo electrónico se asignarán de Adobe Campaign a Microsoft Dynamics 365.

Las cuatro métricas que puede controlar son: **Envía**, **Clics**, **Abre** y **Devoluciones**.

![](assets/d365-to-acs-ui-page-workflows-egress.png)

Seleccione **Sí** para confirmar que desea que los eventos de ese tipo fluyan a Microsoft Dynamics 365.

Haga clic [aquí](../../integrating/using/d365-acs-self-service-app-workflows.md) para obtener más información sobre estos flujos de evento de correo electrónico.

## Flujo de trabajo de adhesión/excluir {#opt-in-out-wf}

El flujo de trabajo **de inclusión/exclusión** permite identificar el flujo de información de adhesión/salida entre Microsoft Dynamics 365 y Adobe Campaign. Esto supone que los datos están asociados al &quot;contacto&quot; de la entidad de Microsoft Dynamics 365 y al &quot;perfil&quot; del recurso de Adobe Campaign.

Obtenga más información sobre la administración de exclusión en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

Recuerde que debe hacer clic en &quot;Guardar&quot; para guardar sus selecciones. Recuerde también que debe detener el flujo de trabajo **de la Campaña a Microsoft Dynamics 365** y, a continuación, hacer clic en reproducir para que la integración incorpore los cambios.

![](assets/d365-to-acs-ui-page-workflows-optinout-disabled.png)

### Adhesión/extraer dirección de sincronización

A continuación se muestra la lista de opciones disponibles para sincronizar datos:

* **[!UICONTROL Disabled]**:: cuando se selecciona esta opción, no se moverá ninguna información de adhesión/excluir entre Adobe Campaign y Microsoft Dynamics 365.

* **[!UICONTROL Unidirectional (Microsoft Dynamics 365 to Campaign)]**:: esta opción se utiliza para el flujo de la inclusión y la exclusión desde Microsoft Dynamics 365 solo a Adobe Campaign. La aplicación de integración no le permitirá configurar el flujo en esta pantalla; en su lugar, haga clic en **[!UICONTROL Save button]** y vaya al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]**. En este flujo de trabajo, puede editar la asignación de la tabla de contactos/perfiles para identificar cómo desea que se asignen los campos de inclusión/exclusión.

* **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]**:: esta opción hará visible la sección  **** Asignaciones. Estas entradas le permitirán definir qué campos de Adobe Campaign asignarán datos a los campos de Microsoft Dynamics 365. Esto significa que si se actualiza manualmente un valor en Microsoft Dynamics 365, el valor de Adobe Campaign sobrescribirá su valor si esto sucede.

* **[!UICONTROL Bidirectional]**:: esta opción hará visible la sección  **** Asignaciones. Estos pares identificarán los campos de Microsoft Dynamics 365 y Adobe Campaign que se asignarán entre sí. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md).

### Asignaciones

Esta sección sólo se aplica cuando el campo de dirección de sincronización de inclusión/exclusión está establecido en **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**. Puede definir qué campos de Microsoft Dynamics 365 se asignan a qué entradas de Adobe Campaign.

Los nombres de campo de Microsoft Dynamics 365 incluyen todos los que son de tipo **booleano**.

Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos para la inclusión y la exclusión. Los nombres de campo de Adobe Campaign son un conjunto fijo de valores específicos para la inclusión y la exclusión. **No se puede cambiar** el conjunto de valores de esta lista.
