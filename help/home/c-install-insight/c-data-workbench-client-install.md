---
description: A continuación se indican los requisitos y recomendaciones para instalar la estación de trabajo (cliente) en Data Workbench.
title: Requisitos de Workstation
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---

# Requisitos de Workstation{#workstation-requirements}

A continuación se indican los requisitos y recomendaciones para instalar la estación de trabajo (cliente) en Data Workbench.

Consulte [Requisitos del sistema del servidor](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/c-msr-server.html?lang=en) para conocer los requisitos adicionales del sistema de Data Workbench.

>[!IMPORTANT]
>
>Los componentes de servidor, servidor de informes y cliente se actualizan para que se ejecuten en sistemas operativos Windows de 64 bits.

**Antes de empezar**

Asegúrese de haber completado las siguientes tareas antes de instalar la estación de trabajo de Data Workbench (cliente):

* **** ***AddExcluded*** Processesses for  *MS System Center Endpoint Protection in Windows 2012* Server para los siguientes ejecutables:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   Esto habilitará derechos de lista de permitidos para estos ejecutables de interfaz.

* **Instale Microsoft Excel para exportar los datos de análisis.** Para exportar datos de espacios de trabajo como archivos de Microsoft Excel (  [!DNL .xls] o  [!DNL .xlsx]), el equipo en el que instale la Data Workbench debe tener Excel instalado y registrado. Si Excel no se ha registrado y la Data Workbench intenta acceder a él por primera vez, muestra un cuadro de diálogo de registro. Si no está seguro de si la copia está registrada, inicie Excel manualmente y, si aparece un cuadro de diálogo de registro, complete el proceso de registro.

   >[!NOTE]
   >
   >Con el lanzamiento de la Data Workbench 6.4, se ha interrumpido la compatibilidad con Excel 2007. Además, como la Data Workbench solo se ejecuta en Microsoft Windows para la arquitectura de 64 bits, se recomienda instalar también una versión de 64 bits de Microsoft Excel.

* **Instalación de Adobe  [!DNL Acrobat] para imprimir espacios de trabajo escalados en PDF.** Para imprimir espacios de trabajo escalados en formato Adobe PDF, el equipo en el que haya instalado la Data Workbench debe tener  [!DNL Acrobat] instalado el Adobe.

* **Proporcionar acceso a una impresora para imprimir espacios de trabajo.** Para imprimir espacios de trabajo desde la Data Workbench, el equipo en el que instale la Data Workbench debe tener acceso a una impresora. La Data Workbench puede imprimir espacios de trabajo en impresoras a color o monocromas y no requiere postscript u otras funciones de impresora avanzadas. Para obtener resultados óptimos, Adobe recomienda imprimir espacios de trabajo en color.
* **Implementar medidas de seguridad.** Debe seguir las políticas de seguridad empresarial normales de su empresa para equipos de Data Workbench. Para cumplir con sus propósitos principales, la Data Workbench solo requiere la capacidad de conectarse a un servidor (a través de los puertos 80 y 443) y a cualquier servidor que recopile datos. Puede utilizar el hardware de la Data Workbench para cualquier otro fin siempre que mantenga el software de Data Workbench y asigne al menos 10 GB de espacio de almacenamiento para la Data Workbench.
* Para representar visualizaciones con precisión, el equipo en el que instale el área de trabajo debe tener instalado un **adaptador de gráficos** apropiado (consulte Requisitos del adaptador de gráficos a continuación).

**Requisitos del cliente de Data Workbench**

**Sistema operativo**

* Microsoft Windows 7 de 64 bits
* Microsoft Windows 8.1 de 64 bits
* Microsoft Windows 10 de 64 bits

>[!NOTE]
>
>Windows XP no es compatible con la Data Workbench 6.1 y versiones posteriores.

**Resolución**

* Requerido: 1024 x 768 (XGA)
* Recomendado: 1920 x 1200 (WUXGA)

**Adaptador de gráficos**

* Requerido: Aceleración de hardware OpenGL para admitir OpenGL 3.2
* Recomendado: Adaptador de vídeo dedicado (p. ej., adaptador NVIDIA o ATI)

**Procesador**

* Requerido: Intel o AMD de 1,2 GHz o superior
* Recomendado: ICore 2 Duo

**RAM**

* Requerido: 2 GB
* Recomendado: 4 GB

**Conectividad**

* Requerido: Enlace de 512 Kbps a la DPU
* Recomendado: Enlace a la DPU de 2 Mbps o más rápido

**Sistema de archivos**

NTFS

**Almacenamiento en disco**

Al menos diez (10) GB o bueno espacio libre en la unidad de disco duro

**Impresión**

Acceso a la impresora (impresoras a color o escala gris) para imprimir espacios de trabajo e informes

**Otro**

* Ratón dedicado
* Entorno de trabajo de bajo brillo
* Monitor de superficie plana
