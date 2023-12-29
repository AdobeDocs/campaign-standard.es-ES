---
title: Resolución de problemas de integración
description: Obtenga información sobre cómo solucionar problemas al compartir recursos.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 18%

---

# Resolución de problemas{#troubleshooting}

Se pueden encontrar errores al utilizar la integración con el Audience Manager o el servicio principal Personas.

En este caso, asegúrese de que los siguientes elementos están correctamente configurados:

* **Cuentas externas**

  Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, asegúrese de que las siguientes cuentas externas S3 estén configuradas correctamente. Los servidores S3 mencionados deberían haberse configurado durante el aprovisionamiento.

   * **[!UICONTROL importSharedAudience]**: Cuenta S3 específica para la importación de audiencias.
   * **[!UICONTROL exportSharedAudience]**: Cuenta S3 específica para la exportación de audiencias.

* **Fuentes de datos compartidas**

  Entrada **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, compruebe que la fuente de datos compartidos está correctamente configurada.

  **[!UICONTROL Priority]** se utiliza cuando se definen varias fuentes de datos. La prioridad decide qué fuente de datos se utilizará para hacer coincidir el alias recibido en el orden definido. **[!UICONTROL Priority]** solo es necesario para la implementación de Déclencheur.

  Compruebe que la clave de reconciliación sea correcta. Es el valor cifrado/con hash de este campo el que se utiliza para exportar e importar audiencias.

  En caso de hash o cifrado del ID declarado, compruebe que se utilizan los mismos parámetros/algoritmos de cifrado en el sitio web.

  Solo se admite un algoritmo de cifrado: AES en modo CBC con un tamaño de clave de 128, 192 o 256 bits, con relleno PKCS.

  Si se selecciona el algoritmo de cifrado AES, se deben configurar correctamente los siguientes campos adicionales:

   * **Clave de cifrado** para AES
   * **Cifrado IV** (Vector de inicialización) para AES
   * **Canal** (Correo electrónico/SMS/Otros): Este campo permite descifrar directamente las direcciones de correo electrónico y los números de SMS. Asegúrese de que la clave de reconciliación coincida con la configuración del **Canal** field. Si selecciona &quot;Otro&quot;, este descifrado específico no se producirá y la clave de reconciliación se utilizará para reconciliar los datos.

  Es posible que las audiencias del Experience Cloud no se compartan porque el flujo de trabajo técnico se ha detenido o pausado. Acceda a la **[!UICONTROL Import shared audience]** haciendo clic directamente en el **[!UICONTROL Show ImportShared Audience workflow]** en la fuente de datos.

Al importar una audiencia o compartirla mediante el servicio principal Personas, puede que falten algunos datos. Solo se transfieren los registros cuya ID (“ID de visitante” o “ID declarada”) se haya podido reconciliar con la dimensión del perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.
