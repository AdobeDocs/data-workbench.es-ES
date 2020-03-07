---
description: Los siguientes son requisitos y recomendaciones para instalar la estación de trabajo (cliente) en el área de trabajo de datos.
solution: Analytics
title: Requisitos de estación de trabajo
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Requisitos de estación de trabajo{#workstation-requirements}

Los siguientes son requisitos y recomendaciones para instalar la estación de trabajo (cliente) en el área de trabajo de datos.

Consulte Requisitos [del sistema del](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) servidor para conocer los requisitos adicionales del sistema del Área de trabajo de datos.

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para ejecutarse en sistemas operativos Windows de 64 bits.

**Antes de empezar**

Antes de instalar la estación de trabajo del área de trabajo de datos (cliente), asegúrese de que las tareas se han completado:

* **Agregar** procesos ****** excluidos para la protección de extremo de System Center de *MS en servidores* Windows 2012 para los siguientes ejecutables:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   Esto permitirá derechos de &quot;lista blanca&quot; para estos ejecutables de interfaz.

* **Instale Microsoft Excel para exportar datos de análisis.** Para exportar datos desde espacios de trabajo como archivos de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), el equipo en el que instale Área de trabajo de datos debe tener Excel instalado y registrado. Si no se ha registrado Excel y Área de trabajo de datos intenta acceder a él por primera vez, Excel muestra un cuadro de diálogo de registro. Si no está seguro de si la copia está registrada, inicie Excel manualmente y, si aparece un cuadro de diálogo de registro, complete el proceso de registro.

   >[!NOTE]
   >
   >Con el lanzamiento de Área de trabajo de datos 6.4, la compatibilidad con Excel 2007 se ha interrumpido. Además, dado que Área de trabajo de datos solo se ejecuta en Microsoft Windows para la arquitectura de 64 bits, se recomienda instalar una versión de 64 bits de Microsoft Excel.

* **Instalación de Adobe[!DNL Acrobat]para imprimir espacios de trabajo escalados en PDF.** Para imprimir espacios de trabajo escalados en formato Adobe PDF, el equipo en el que haya instalado Área de trabajo de datos debe tener Adobe [!DNL Acrobat] instalado.

* **Acceso a una impresora para imprimir espacios de trabajo.** Para imprimir espacios de trabajo desde Área de trabajo de datos, el equipo en el que instale Área de trabajo de datos debe tener acceso a una impresora. Área de trabajo de datos puede imprimir espacios de trabajo en impresoras en color o monocromas y no requiere postscript u otras características avanzadas de la impresora. Para obtener resultados óptimos, Adobe recomienda imprimir espacios de trabajo en color.
* **Aplicar medidas de seguridad.** Debe seguir las directivas de seguridad empresarial normales de su empresa para equipos del área de trabajo de datos. Para cumplir sus objetivos principales, el Área de trabajo de datos sólo requiere la capacidad de conectarse a un servidor (a través de los puertos 80 y 443) y a cualquier servidor que recopile datos. Puede utilizar el hardware de Área de trabajo de datos para cualquier otro fin siempre que mantenga el software de Área de trabajo de datos y asigne al menos 10 GB de espacio de almacenamiento para Área de trabajo de datos.
* Para representar visualizaciones con precisión, el equipo en el que instale el área de trabajo debe tener instalado un adaptador **de** gráficos adecuado (consulte los requisitos del adaptador de gráficos más adelante).

**Requisitos del cliente de Área de trabajo de datos**

**Sistema operativo**

* Microsoft Windows 7 de 64 bits
* Microsoft Windows 8.1 de 64 bits
* Microsoft Windows 10 de 64 bits

>[!NOTE]
>
>Windows XP no es compatible con Área de trabajo de datos 6.1 y versiones posteriores.

**Resolución**

* Requerido: 1024 x 768 (XGA)
* Recomendado: 1920 x 1200 (WUXGA)

**Adaptador de gráficos**

* Requerido: Aceleración de hardware OpenGL para OpenGL 3.2
* Recomendado: Adaptador de vídeo dedicado (por ejemplo, adaptador NVIDIA o ATI)

**Procesador**

* Requerido: Intel o AMD de 1,2 GHz o superior
* Recomendado: ICore 2 Duo-Class

**RAM**

* Requerido: 2 GB
* Recomendado: 4 GB

**Conectividad**

* Requerido: Vínculo de 512 Kbps al DPU
* Recomendado: Vínculo a la DPU de 2 Mbps o más rápido

**Sistema de archivos**

NTFS

**Almacenamiento en disco**

Al menos diez (10) GB o bueno espacio libre en la unidad de disco duro

**Impresión**

Acceso a la impresora (impresoras de color o escala gris) para imprimir espacios de trabajo e informes

**Otro**

* Ratón dedicado
* Entorno de trabajo de bajo brillo
* Monitor con superficie mate

