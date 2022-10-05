---
description: Un conjunto de informes es una colección de espacios de trabajo que el servidor de informes genera en función de los valores especificados en un archivo de configuración de Report.cfg.
title: Explicación de los conjuntos de informes
uuid: 421055d7-0cf0-4664-b944-327a254a97a4
exl-id: 95609a1a-e70c-41e2-ace3-0cb09f77705a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 4%

---

# Explicación de los conjuntos de informes{#understanding-report-sets}

{{eol}}

Un conjunto de informes es una colección de espacios de trabajo que el servidor de informes genera en función de los valores especificados en un archivo de configuración de Report.cfg.

En [!DNL Insight] carpeta de instalación, cada subcarpeta dentro de la carpeta &lt;*nombre del perfil de trabajo*>\La carpeta Informes representa un conjunto de informes que se ha creado. Cada grupo de informes tiene su propio [!DNL Report.cfg] en esa subcarpeta.

>[!NOTE]
>
>En el [!DNL Profile Manager] en Data Workbench, los conjuntos de informes aparecen como subcarpetas dentro de la variable [!DNL Reports] carpeta. Para obtener más información sobre la variable [!DNL Profile Manager], consulte la [Guía del usuario de Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/home.html#Data_Workbench_Help).

Al definir la configuración específica de un grupo de informes en su [!DNL Report.cfg] , puede programar la creación y distribución de los informes, incluido quién recibe qué informes y en qué formatos.
