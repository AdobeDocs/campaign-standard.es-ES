---
title: Resolución de problemas
description: Obtenga información sobre cómo solucionar problemas al compartir recursos.
page-status-flag: nunca activado
uuid: 1c764dd8-e09f-4e8e-9ccd-88ab3d714284
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: servicio de trabajo con campaña y audiencia-administrador-o-personas-núcleo
discoiquuid: c28e1d90-8074-4127-a6fc-ed39d69cdb19
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Resolución de problemas{#troubleshooting}

Pueden producirse errores al utilizar la integración con Audience Manager o el servicio principal Personas.

En este caso, asegúrese de que los siguientes elementos están correctamente configurados:

* **Cuentas externas**

   En **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL External accounts]**, asegúrese de que las siguientes cuentas de S3 externas están correctamente configuradas. Los servidores S3 mencionados deberían haberse configurado durante el aprovisionamiento.

   * **[!UICONTROL importSharedAudience]**:: Cuenta S3 dedicada a la importación de audiencias.
   * **[!UICONTROL exportSharedAudience]**:: Cuenta S3 dedicada a la exportación de audiencias.

* **Fuentes de datos compartidas**

   En **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Shared Data Sources]**, compruebe que el origen de datos compartido está configurado correctamente.

   **[!UICONTROL Priority]** se utiliza cuando tiene varias fuentes de datos definidas. Priority decide qué fuente de datos se utilizará para coincidir con el alias recibido en el orden definido. **[!UICONTROL Priority]** solo se necesita para la implementación de Triggers.

   Compruebe que la clave de reconciliación es correcta. Es el valor hash/cifrado de este campo el que se utiliza para exportar e importar audiencias.

   En caso de hash o cifrado del ID declarado, compruebe que se utilizan los mismos parámetros o algoritmos de codificación en el sitio web.

   Solo se admite un algoritmo de codificación: AES en modo CBC con un tamaño de clave de 128, 192 o 256 bits, con relleno PKCS.

   Si se selecciona el algoritmo de codificación AES, deben establecerse correctamente los siguientes campos adicionales:

   * **Clave** de cifrado para AES
   * **Cifrado IV** (vector de inicialización) para AES
   * **Canal** (Correo electrónico/SMS/Otro): Este campo permite descifrar directamente direcciones de correo electrónico y números SMS. Asegúrese de que la clave de reconciliación coincide con la configuración del campo **Canal** . Si selecciona "Otro", este descifrado específico no se producirá y la clave de reconciliación se utilizará para reconciliar los datos.
   Es posible que las audiencias de Experience Cloud no se compartan porque el flujo de trabajo técnico se ha detenido o pausado. Para acceder al flujo de trabajo, haga clic directamente en la **[!UICONTROL Import shared audience]** **[!UICONTROL Show ImportShared Audience workflow]** opción del origen de datos.

Al importar una audiencia o compartirla mediante el servicio principal Personas, puede que falten algunos datos. Solo se transfieren los registros cuya ID (“ID de visitante” o “ID declarada”) se haya podido conciliar con la dimensión del perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.
