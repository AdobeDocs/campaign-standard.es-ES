---
title: Generación de un archivo CSV para notificaciones push multilingües con Campaign Standard
description: La carga de un archivo CSV para generar contenido para su envío es una función que se utiliza para admitir notificaciones push multilingües.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Push
role: User
level: Intermediate
exl-id: bd9ec3f9-e047-42dc-ab64-9fb274cb4656
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1127'
ht-degree: 1%

---

# Generación de un archivo CSV para notificaciones push multilingües{#generating-csv-multilingual-push}

La carga de un archivo CSV para generar contenido para su envío es una función que se utiliza para admitir notificaciones push multilingües. El formato del archivo CSV debe cumplir ciertas directrices para que la carga del archivo se realice correctamente y, por lo tanto, para poder crear una entrega. En las siguientes secciones se describe el formato de archivo y sus consideraciones.

## Formato de archivo {#file-format}

La funcionalidad push multilingüe requiere 14 columnas en el archivo CSV:

1. título
1. messageBody
1. sano
1. adge
1. deeplinkURI
1. categoría
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. locale
1. language
1. quietPush

Compruebe el ejemplo de CSV haciendo clic en **[!UICONTROL Download a sample file]** en el **[!UICONTROL Manage Content Variants]** ventana. Para obtener más información, consulte esta [sección](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deeplinkURI, category, iosMediaAttachmentURL, androidMediaAttachmentURL**: contenido de carga útil push normal. Debe proporcionar esta información de manera similar a como se hace al crear envíos push.
* **Campos personalizados**: utilice el formato JSON para los campos personalizados, por ejemplo. `{"key1":"value1","key2":"value2"}`. Consulte el archivo de muestra anterior para ver un ejemplo de campos personalizados.
* **isContentAvailable**: indicador para la comprobación de Contenido disponible, el valor 1 implica verdadero, el valor 0 implica falso. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.
* **isMutableContent**: indicador para Contenido mutable, el valor 1 implica verdadero, el valor 0 implica falso. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.
* **locale**: configuración regional es el campo para las variantes de idioma, por ejemplo, &quot;en_us&quot; para inglés estadounidense y &quot;fr_fr&quot; para francés.
* **idioma**: nombre del idioma asociado con la configuración regional. Por ejemplo, si la configuración regional es &quot;en_us&quot;, el nombre del idioma debe ser &quot;Inglés-Estados Unidos&quot;.
* **quietPush**: indicador para el tipo de notificación push. Si es una notificación push regular, el valor debe ser 0. Si se trata de una inserción silenciosa, el valor debe ser 1. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.

## Restricciones y directrices para la creación de archivos .csv {#constraints-guideline-csv}

**El nombre de cada columna es fijo**.
Debe incluir el nombre de cada columna en el archivo CSV. Si no utiliza ninguna columna para el contenido, déjelo en blanco.

**Las columnas &quot;locale&quot; e &quot;language&quot; son obligatorias y el valor es único para cada fila.**
Un valor en blanco para esta columna provocará un error en la carga del archivo.

**El orden de las columnas importa**. El orden de las columnas del archivo cargado debe seguir el mismo formato que el archivo de muestra.

**Citar contenido de columna**. Dado que se trata de un archivo CSV (significa Valores separados por comas), cualquier contenido de columna que incluya una coma (,) debe citarse. Por ejemplo: &quot;¡Hola, Tom!&quot;

**La codificación UTF-8 es necesaria para caracteres internacionales.**

**Si genera el archivo mediante texto sin formato, separe cada columna con &quot;,&quot;.**

**La variante no coincide.** Si utiliza bloques de contenido y audiencias de destino con idiomas específicos, debe enumerar todos los idiomas de destino en el archivo CSV o se producirá un error al realizar el envío.

## Inserción del campo de personalización en el archivo CSV {#personalization-field-csv}

Si desea utilizar campos de personalización, debe incluir lo siguiente <span> en el archivo.

Para insertar el campo de personalización &quot;firstName&quot; en messageBody, el mensaje debe:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

El campo &quot;firstName&quot; se representa mediante:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

En el intervalo hay dos atributos obligatorios:

* Una es la clase que es estática. Independientemente del campo de personalización que planee utilizar, siempre será class=&quot;nl-dce-field nl-dce-done&quot;.

* Otro es data-nl-expr, que es la ruta del campo de personalización. Por ejemplo, si inserta el campo de personalización &quot;firstName&quot; desde la interfaz de usuario, la ruta de navegación será **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (como se muestra en la siguiente imagen). En este caso, la ruta es

  ```
  /context/profile/firstName. data-nl-expr="/context/profile/firstName".
  ```

![](assets/multilingual_push_2.png)

## Configuración regional y nombres de idioma {#locale-language-names}

Se admiten los siguientes idiomas:

| locale | language |
|:-:|:-:|
| af_za | Afrikáans (Sudáfrica) |
| sq_al | Albanés (Albania) |
| ar_dz | Árabe - Argelia |
| ar_bh | Árabe - Baréin |
| ar_iq | Árabe - Iraq |
| ar_il | Árabe (Israel) |
| ar_jo | Árabe - Jordania |
| ar_kw | Árabe - Kuwait |
| ar_lb | Árabe - Líbano |
| ar_ma | Árabe - Marruecos |
| ar_om | Árabe - Omán |
| ar_qa | Árabe (Qatar) |
| ar_sa | Árabe - Arabia Saudí |
| ar_sy | Árabe (Siria) |
| ar_tn | Árabe - Túnez |
| ar_ae | Árabe - Emiratos Árabes Unidos |
| ar_ye | Árabe - Yemen |
| hy_am | Armenio (Armenia) |
| az_az | Azerí (Azerbaiyán) |
| be_by | Bielorruso (Bielorrusia) |
| bs_ba | Bosnio (Bosnia) |
| bg_bg | Búlgaro (Bulgaria) |
| ca_es | Catalán (España) |
| zh_cn | Chino (simplificado) - China |
| zh_sg | Chino (simplificado) - Singapur |
| zh_hk | Chino (tradicional) - RAE de Hong Kong |
| zh_tw | Chino (tradicional) - Región de Taiwán |
| hr_hr | Croata - Croacia |
| cs_cz | Checo - Chequia |
| da_dk | Danés (Dinamarca) |
| nl_be | Neerlandés - Bélgica |
| nl_nl | Neerlandés - Países Bajos |
| en_au | Inglés (Australia) |
| en_bz | Inglés (Belice) |
| en_ca | Inglés (Canadá) |
| en_in | Inglés (India) |
| en_ie | Inglés (Irlanda) |
| en_jm | Inglés (Jamaica) |
| en_nz | Inglés (Nueva Zelanda) |
| en_ph | Inglés (Filipinas) |
| en_za | Inglés (Sudáfrica) |
| en_tt | Inglés (Trinidad y Tobago) |
| en_gb | Inglés (Reino Unido) |
| en_us | Inglés (Estados Unidos) |
| en_zw | Inglés (Zimbabue) |
| et_ee | Estonio (Estonia) |
| fi_fi | Finés (Finlandia) |
| fr_be | Francés (Bélgica) |
| fr_ca | Francés (Canadá) |
| fr_fr | Francés (Francia) |
| fr_lu | Francés (Luxemburgo) |
| fr_ch | Francés (Suiza) |
| de_at | Alemán (Austria) |
| de_de | Alemán (Alemania) |
| de_lu | Alemán (Luxemburgo) |
| de_ch | Alemán (Suiza) |
| el_cy | Griego (Chipre) |
| el_gr | Griego (Grecia) |
| gu_in | Gujarati (India) |
| he_il | Hebreo (Israel) |
| hi_in | Hindi (India) |
| hu_hu | Húngaro (Hungría) |
| is_is | Islandés (Islandia) |
| id_id | Indonesio (Indonesia) |
| it_it | Italiano (Italia) |
| it_ch | Italiano (Suiza) |
| ja_jp | Japonés (Japón) |
| kn_in | Kannada (India) |
| kk_kz | Kazajo (Kazajistán) |
| ko_kr | Coreano - Corea del Sur |
| lv_lv | Letón (Letonia) |
| lt_lt | Lituano (Lituania) |
| mk_mk | Macedonio (Macedonia) |
| ms_my | Malayo (Malasia) |
| mr_in | Marathi (India) |
| no_no | Noruego (Noruega) |
| pl_pl | Polaco (Polonia) |
| pt_br | Portugués (Brasil) |
| pt_pt | Portugués (Portugal) |
| pa_in | Punyabí (India) |
| ro_md | Rumano (Moldavia) |
| ro_ro | Rumano (Rumanía) |
| ru_kz | Ruso (Kazajistán) |
| ru_ru | Ruso (Rusia) |
| ru_ua | Ruso - Ucrania |
| a_in | Sánscrito (India) |
| sr_ba | Serbio (Bosnia) |
| sr_rs | Serbio (Serbia) |
| sk_sk | Eslovaco (Eslovaquia) |
| sl_si | Esloveno (Eslovenia) |
| es_ar | Español - Argentina |
| es_bo | Español - Bolivia |
| es_cl | Español - Chile |
| es_co | Español - Colombia |
| es_cr | Español (Costa Rica) |
| es_do | Español - República Dominicana |
| es_ec | Español - Ecuador |
| es_sv | Español - El Salvador |
| es_gt | Español - Guatemala |
| es_hn | Español (Honduras) |
| es_mx | Español - México |
| es_ni | Español (Nicaragua) |
| es_pa | Español - Panamá |
| es_py | Español - Paraguay |
| es_pe | Español (Perú) |
| es_pr | Español (Puerto Rico) |
| es_es | Español - España |
| es_uy | Español - Uruguay |
| es_ve | Español - Venezuela |
| sw_ke | Suajili (Kenia) |
| sv_fi | Sueco (Finlandia) |
| sv_se | Sueco (Suecia) |
| ta_in | Tamil (India) |
| tt_ru | Tártaro - Ruso |
| te_in | Telugu (India) |
| th_th | Tailandés (Tailandia) |
| tr_cy | Turco (Chipre) |
| tr_tr | Turco (Turquía) |
| uk_ua | Ucraniano - Ucrania |
| ur_in | Urdu (India) |
| ur_pk | Urdu (Pakistán) |
| vi_vn | Vietnamita (Vietnam) |
