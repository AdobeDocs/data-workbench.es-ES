---
description: Un conjunto de informes es una colección de espacios de trabajo que el servidor de informes genera en función de los valores especificados en un archivo de configuración de Report.cfg.
title: Explicación de los conjuntos de informes
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 4%

---

# Explicación de los conjuntos de informes{#understanding-report-sets}

Un conjunto de informes es una colección de espacios de trabajo que el servidor de informes genera en función de los valores especificados en un archivo de configuración de Report.cfg.

En la carpeta de instalación [!DNL Insight], cada subcarpeta dentro de la carpeta &lt;*nombre del perfil de trabajo*>\Reports representa un conjunto de informes que se ha creado. Cada conjunto de informes tiene su propio archivo de configuración [!DNL Report.cfg] dentro de esa subcarpeta.

>[!NOTE]
>
>En la [!DNL Profile Manager] de la Data Workbench, los conjuntos de informes aparecen como subcarpetas dentro de la carpeta [!DNL Reports]. Para obtener más información sobre [!DNL Profile Manager], consulte la [Guía del usuario de Data Workbench](https://docs.adobe.com/content/help/en/data-workbench/using/home.html#Data_Workbench_Help).

Al definir la configuración específica para un conjunto de informes en su archivo [!DNL Report.cfg], puede programar la creación y distribución de los informes, incluido quién recibe qué informes y en qué formatos.
