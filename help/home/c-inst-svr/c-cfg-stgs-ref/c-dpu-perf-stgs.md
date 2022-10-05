---
description: Instrucciones para ajustar el rendimiento de DPU.
title: Configuración de rendimiento de DPU
uuid: e2b87548-7eb3-4f82-a94e-8ec7c3dc27c2
exl-id: 738c3a76-f8b4-4d84-86ee-ce9b99f50dae
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 7%

---

# Configuración de rendimiento de DPU{#dpu-performance-settings}

{{eol}}

Instrucciones para ajustar el rendimiento de DPU.

Complete los siguientes parámetros en la sección * [!DNL Insight Server] directorio de instalación*\Components\DPU.cfg .

| Parámetro | Descripción |
|---|---|
| Recuento de lotes de ejecución | Este es un parámetro de ajuste. El valor predeterminado es 65536. Puede especificar recuentos por lotes de ejecución arbitrariamente pequeños. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Lotes de ejecución | Este es un parámetro de ajuste. El valor predeterminado es 128. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Hora de ejecución | Este es un parámetro de ajuste. El valor predeterminado es 0,100. Póngase en contacto con Adobe antes de realizar cambios en este valor. |
| Volcado de campo en error | Este parámetro se puede establecer en true o false. Si se establece en true, [!DNL Insight Server] crea un archivo con el nombre [!DNL Field Dump number.txt] en su directorio Trace siempre que se produzcan errores en el motor de ejecución. La variable [!DNL Field Dump] &lt; [!DNL number]> [!DNL .txt] es útil para la resolución de problemas. |
| Ruta de acceso del perfil | Ubicación en la que se almacenan los archivos de todos los perfiles. La ubicación predeterminada es Profiles\. |
| Límite de memoria de consulta | Cantidad de memoria (en bytes) que [!DNL Insight Server] se reserva para almacenar los resultados de la consulta. El valor predeterminado es 100000000 (100 MB) Si se necesita más espacio para los resultados de la consulta (por ejemplo, para permitir usuarios más simultáneos), la configuración se puede aumentar, pero debe seguir comprobando la variable [!DNL Insight Server’s] carga de memoria. |
| Ruta de estado | Ubicación de los archivos de estado del sistema. La ubicación predeterminada es State\. |
| Subprocesos | Un parámetro de ajuste de rendimiento para [!DNL Insight Server] máquinas con varios procesadores. En general, para cualquier sistema n-core, este valor debe establecerse en n. El valor predeterminado es 1. |
| Ruta del usuario | Ubicación de los archivos de los usuarios autorizados. La ubicación predeterminada es Usuarios\. |
