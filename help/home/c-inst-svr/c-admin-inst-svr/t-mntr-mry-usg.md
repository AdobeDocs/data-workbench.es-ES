---
description: Información sobre la evaluación y supervisión de la carga de espacio de direcciones.
solution: Analytics
title: Monitorización del uso de la memoria
uuid: e7f1c51b-d874-43f4-a074-1c064b5f298a
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 2%

---


# Monitorización del uso de la memoria{#monitoring-memory-usage}

Información sobre la evaluación y supervisión de la carga de espacio de direcciones.

**Supervisión de la carga del espacio de direcciones**

**Frecuencia recomendada:** Diario

La carga del espacio de direcciones es una medida de la fracción del espacio de direcciones máximo que [!DNL Insight Server] utiliza una configuración correcta. Aunque los parámetros de configuración se cambien para reducir el uso de memoria, normalmente no disminuyen hasta que se reinicia el [!DNL Insight Server] servicio.

Se ha incorporado un margen de seguridad en el máximo de carga del espacio de direcciones para tener en cuenta los incrementos inesperados en la utilización del espacio de direcciones. Nunca debes reducir deliberadamente este margen de seguridad. Existe para situaciones de emergencia y no para la compatibilidad con la funcionalidad agregada a la aplicación Adobe.

>[!NOTE]
>
>Para que haya más espacio de direcciones disponible y evitar errores de agotamiento de memoria, asegúrese de que el sistema operativo tenga activado el conmutador /3GB y de que funcione el montón de baja fragmentación.

Los errores registrados en el registro de datos de [!DNL Insight Server] evento pueden proporcionar una pista de que se están desarrollando problemas con la carga del espacio de direcciones:

* Los errores &quot;El bloque de bytes X solicitado es demasiado grande&quot; indican que algo puede tener un impacto excesivo en la carga del espacio de direcciones, el rendimiento y el ancho de banda de la red. Estos bloques de gran tamaño pueden contribuir en gran medida al uso del espacio de direcciones, tanto mediante el uso de mucha memoria como mediante la exigencia de grandes bloques contiguos de espacio de direcciones.

   Para solucionar este problema, puede reducir la cardinalidad de las dimensiones más grandes, lo que aumenta la carga del espacio de direcciones. Si no puede reducir la cardinalidad de las dimensiones, debe intentar mantener la carga del espacio de direcciones lo suficientemente pequeña como para poder gestionar un aumento inesperado.
* Los errores de &quot;Presupuesto de memoria excedido&quot; indican que es posible que necesite aumentar el límite de memoria de Consulta. La memoria utilizada por las consultas es proporcional a la cardinalidad de dimensión y, en algunos casos, a la longitud de los nombres de elementos. Si aumenta el límite de memoria de la Consulta, aumenta la carga total del espacio de direcciones y reduce las dimensiones grandes.

>[!NOTE]
>
>De forma predeterminada, se permite el uso de páginas grandes y la búsqueda asignada a memoria está deshabilitada. En DWB 6.7 y versiones posteriores, esto se puede cambiar en la configuración del conjunto de datos. Cualquier cambio requiere un reinicio del servidor.

**Para evaluar la carga del espacio de direcciones**

Para evaluar con precisión la carga del espacio de direcciones para su sistema, Adobe recomienda reprocesar el conjunto de datos, realizar algunas consultas normales sin reiniciar posteriormente [!DNL Insight Server]y luego ver la carga del espacio de direcciones medida siguiendo estos pasos.

Si no se [!DNL Insight Server] ha reprocesado ni consultado significativamente un elemento desde que se reinició por última vez, no debe extraer conclusiones de la carga de espacio de direcciones.

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Detailed Status]**.
1. En la interfaz Estado detallado, haga clic en **[!UICONTROL Memory Status]** para vista de su contenido. En el parámetro Carga de espacio de direcciones, puede ver la carga de espacio de direcciones expresada como porcentaje y una descripción entre paréntesis que indica el estado.

   La siguiente tabla presenta los intervalos y el estado de la carga del espacio de direcciones. Se muestra una acción recomendada para cada intervalo.

   | Carga del espacio de direcciones (%) | Estado | Acción recomendada |
   |---|---|---|
   | 0-15 | lean y media | Ninguna. |
   | 15-33 | light | Ninguna. |
   | 33-66 | moderado | Ninguna. |
   | 66-100 | pesado | Para evitar errores en el agotamiento de la memoria, no agregue una funcionalidad adicional significativa ni intente procesar más datos. |
   | 100-125 | fiabilidad comprometida | Ajuste la configuración del conjunto de datos para reducir la carga del espacio de direcciones. |
   | 125 o bueno | error inminente | Ajuste la configuración del conjunto de datos para reducir la carga del espacio de direcciones. Es posible que no vea el estado inminente del error antes de que se produzca el error. |

   Si ve una carga de espacio de direcciones superior al 100%, debe cambiar la configuración lo antes posible para reducir el uso de espacio de direcciones.

