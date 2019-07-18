---
title: Solución de problemas
seo-title: Solución de problemas
description: Solución de problemas
seo-description: Descubra cómo solucionar problemas al compartir recursos.
page-status-flag: no activado nunca
uuid: 1 c 764 dd 8-e 09 f -4 e 8 e -9 ccd -88 ab 3 d 714284
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: c 28 e 1 d 90-8074-4127-a 6 fc-ed 39 d 69 cdb 19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Troubleshooting{#troubleshooting}

Pueden producirse errores al utilizar la integración con el servicio principal de Audience Manager o Personas.

En este caso, asegúrese de que los siguientes elementos estén correctamente configurados:

* **Cuentas externas**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, make sure that the following external S3 accounts are correctly configured. Los servidores S 3 mencionados deben configurarse durante el aprovisionamiento.

   * **[!UICONTROL importSharedAudience]**: Cuenta S 3 dedicada a importar audiencias.
   * **[!UICONTROL exportSharedAudience]**: Cuenta S 3 dedicada a exportar audiencias.

* **Fuentes de datos compartidas**

   In **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, check that the shared data source is set properly.

   **[!UICONTROL Priority]** se usa cuando se definen varias fuentes de datos. La prioridad decide qué fuente de datos se utilizará para coincidir con alias recibidos en el orden definido. **[!UICONTROL Priority]** solo es necesario para la implementación de Activadores.

   Compruebe que la clave de reconciliación sea correcta. Es el valor hash/cifrado de este campo que se utiliza para exportar e importar audiencias.

   En caso de hash o cifrado del ID declarado, compruebe que se usen los mismos parámetros o algoritmos de codificación en el sitio web.

   Solo se admite un algoritmo de codificación: AES en modo CBC con un tamaño de clave de 128, 192 o 256 bits, con relleno PKCS.

   Si se selecciona el algoritmo de codificación AES, los campos adicionales siguientes deben configurarse correctamente:

   * **Clave de cifrado** para AES
   * **Codificación IV** (Vector de inicialización) para AES
   * **Canal** (Correo electrónico/SMS/Otro): Este campo permite descifrar directamente las direcciones de correo electrónico y los números SMS. Make sure that the reconciliation key matches the setting of the **Channel** field. Si selecciona "Otro", este descifrado específico no se llevará a cabo y la clave de reconciliación se utilizará para reconciliar los datos.
   Es posible que las audiencias de Experience Cloud no se compartan porque el flujo de trabajo técnico se ha detenido o detenido. Access the **[!UICONTROL Import shared audience]** workflow by clicking directly the **[!UICONTROL Show ImportShared Audience workflow]** option in your Data source.

Puede ocurrir que no se pierdan algunos datos al compartir una audiencia mediante el servicio principal Personas o al importar una audiencia. Solo se transferirán los registros de los que se pudo reconciliar el ID (' ID de visitante'o «ID declarado ') con la dimensión de perfil. Los ID de los segmentos del servicio principal Personas que no son reconocidos por Adobe Campaign no se importan.
