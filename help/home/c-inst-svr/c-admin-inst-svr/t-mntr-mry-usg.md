---
description: Información sobre la evaluación y supervisión de la carga del espacio de direcciones.
title: Monitorización del uso de la memoria
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
exl-id: b8c0b33b-dbec-4947-911b-11c8a83bbc9c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---

# Monitorización del uso de la memoria{#monitoring-memory-usage}

{{eol}}

Información sobre la evaluación y supervisión de la carga del espacio de direcciones.

**Supervisión de la carga del espacio de direcciones**

**Frecuencia recomendada:** Diario

La carga del espacio de dirección es una medida de la fracción del espacio de dirección máximo que configuró correctamente [!DNL Insight Server] usa. Aunque los parámetros de configuración se cambien para reducir el uso de memoria, normalmente no disminuyen hasta que [!DNL Insight Server] se reinicia.

Se ha incorporado un margen de seguridad en el máximo de carga del espacio de direcciones para tener en cuenta los incrementos inesperados en la utilización del espacio de direcciones. Nunca debe reducir deliberadamente este margen de seguridad. Existe para situaciones de emergencia y no para el soporte de funcionalidad agregada a su aplicación de Adobe.

>[!NOTE]
>
>Para que haya más espacio de direcciones disponible y evitar errores de agotamiento de memoria, asegúrese de que su sistema operativo tenga el conmutador /3GB habilitado y que el montículo de baja fragmentación esté funcionando.

Errores registrados en la variable [!DNL Insight Server] el registro de datos de evento puede proporcionar una pista de que se están desarrollando problemas con la carga del espacio de direcciones:

* Los errores &quot;El bloque de bytes X solicitado es demasiado grande&quot; indican que algo puede estar teniendo un impacto excesivo en la carga del espacio de direcciones, el rendimiento y el ancho de banda de la red. Estos grandes bloques pueden contribuir en gran medida al uso del espacio de direcciones, tanto mediante el uso de mucha memoria como mediante la necesidad de grandes bloques contiguos de espacio de direcciones.

   Para solucionar este problema, puede reducir la cardinalidad de sus dimensiones más grandes, lo que aumenta la carga del espacio de direcciones. Si no puede reducir la cardinalidad de las dimensiones, debe intentar mantener el espacio de dirección lo suficientemente pequeño como para poder gestionar un aumento inesperado.
* Los errores &quot;Se excedió el presupuesto de memoria&quot; indican que es posible que tenga que aumentar el límite de memoria de consulta. La memoria utilizada por las consultas es proporcional a la cardinalidad de la dimensión y, en algunos casos, a la longitud de los nombres de los elementos. Si aumenta el límite de memoria de consulta, aumentará la carga total de espacio de dirección y reducirá las dimensiones grandes.

>[!NOTE]
>
>De forma predeterminada, se permite el uso de páginas grandes y la búsqueda asignada a memoria está deshabilitada. En DWB 6.7 y posteriores, esto se puede cambiar en la configuración del conjunto de datos. Cualquier cambio requiere un reinicio del servidor.

**Para evaluar la carga del espacio de direcciones**

Para evaluar con precisión la carga del espacio de direcciones para su sistema, Adobe recomienda reprocesar el conjunto de datos, realizando algunas consultas normales sin reiniciar posteriormente [!DNL Insight Server]y, a continuación, viendo la carga del espacio de dirección medido siguiendo estos pasos.

Si una [!DNL Insight Server] no se ha reprocesado ni consultado de forma significativa desde que se reinició por última vez, no debe extraer conclusiones de la carga del espacio de direcciones.

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Detailed Status]**.
1. En la interfaz Estado detallado, haga clic en **[!UICONTROL Memory Status]** para ver su contenido. En el parámetro de carga del espacio de dirección, puede ver la carga del espacio de dirección expresada como porcentaje y una descripción paréntesis que indica el estado.

   La siguiente tabla presenta intervalos y el estado de carga del espacio de direcciones. Se indica una acción recomendada para cada intervalo.

   | Carga del espacio de direcciones (%) | Estado | Acción recomendada |
   |---|---|---|
   | 0-15 | magra y media | Ninguno. |
   | 15-33 | light | Ninguno. |
   | 33-66 | moderar | Ninguno. |
   | 66-100 | pesada | Para evitar fallos en el agotamiento de la memoria, no agregue una funcionalidad adicional significativa ni intente procesar más datos. |
   | 100-125 | fiabilidad comprometida | Ajuste la configuración del conjunto de datos para reducir la carga del espacio de direcciones. |
   | 125 o bueno | error inminente | Ajuste la configuración del conjunto de datos para reducir la carga del espacio de direcciones. Es posible que no vea el estado inminente del error antes de que se produzca el error. |

   Si ve una carga del espacio de dirección superior al 100%, debe cambiar la configuración lo antes posible para reducir el uso del espacio de dirección.
