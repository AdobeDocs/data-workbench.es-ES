---
description: Instrucciones para ajustar el rendimiento de DPU.
solution: Analytics
title: Configuración de rendimiento de DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 6%

---


# Configuración de rendimiento de DPU{#dpu-performance-settings}

Instrucciones para ajustar el rendimiento de DPU.

Rellene los siguientes parámetros en el archivo * [!DNL Insight Server] installation directory*\Components\DPU.cfg.

| Parámetro | Descripción |
|---|---|
| Recuento de lotes de ejecución | Es un parámetro de ajuste. El valor predeterminado es 65536. Puede especificar de forma arbitraria recuentos por lotes de ejecución pequeños. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Lotes de ejecución | Es un parámetro de ajuste. El valor predeterminado es 128. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Tiempo de ejecución | Es un parámetro de ajuste. El valor predeterminado es 0,100. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Error al volcar el campo | Este parámetro se puede establecer en true o false. Si se establece en true, [!DNL Insight Server] crea un archivo denominado [!DNL Field Dump number.txt] en su directorio Trace cada vez que se producen errores en el motor de ejecución. El [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] es útil para la solución de problemas. |
| Ruta de perfil | Ubicación en la que se almacenan los archivos de todos los perfiles. La ubicación predeterminada es Perfiles\. |
| Límite de memoria de consulta | Cantidad de memoria (en bytes) que [!DNL Insight Server] se reserva para almacenar los resultados de la consulta. El valor predeterminado es 100000000 (100 MB). Si se requiere más espacio para los resultados de consulta (por ejemplo, para permitir más usuarios simultáneos), la configuración se puede aumentar, pero debe continuar comprobando la carga de la [!DNL Insight Server’s] memoria. |
| Ruta de estado | Ubicación de los archivos de estado del sistema. La ubicación predeterminada es State\. |
| Subprocesos | Parámetro de ajuste de rendimiento para [!DNL Insight Server] equipos con varios procesadores. En general, para cualquier sistema n-core, este valor debe establecerse en n. El valor predeterminado es 1. |
| Ruta del usuario | Ubicación de los archivos de usuarios autorizados. La ubicación predeterminada es Usuarios\. |

