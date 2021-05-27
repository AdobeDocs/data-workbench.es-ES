---
description: Durante el reprocesamiento, el servidor de Data Workbench reconstruye el conjunto de datos tal como ha especificado en los archivos de configuración de conjuntos de datos de transformación y procesamiento de registros .
title: Explicación del reprocesamiento y la transformación
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
exl-id: 12c69935-a981-492c-9124-71f6f06ff77b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 2%

---

# Explicación del reprocesamiento y la transformación{#understanding-reprocessing-and-retransformation}

Durante el reprocesamiento, el servidor de Data Workbench reconstruye el conjunto de datos tal como ha especificado en los archivos de configuración de conjuntos de datos de transformación y procesamiento de registros .

Para ello, el servidor de Data Workbench (InsightServer64.exe) debe completar la fase de procesamiento del registro y la fase de transformación de la construcción del conjunto de datos. Cuando termina el procesamiento de registros, se déclencheur que la transformación ocurra automáticamente, pero también puede ocurrir independientemente del procesamiento de registros.

Durante la fase de procesamiento del registro, los usuarios de Data Workbench no tienen acceso a los datos del conjunto de datos. Durante la fase de transformación, los usuarios de Data Workbench tienen acceso a los datos actualizados, pero los datos se muestrean en lugar de completarse. El análisis de datos puede continuar durante la transformación, pero las consultas se completarán tan rápido como se produzca la transformación.

## Reprocesamiento {#section-92f1e46bf1534b3dba39e9493190b8ab}

Cada vez que completa una de las siguientes tareas, el procesamiento de registros y, por lo tanto, la transformación, se produce automáticamente para reconstruir el conjunto de datos como ha especificado en los archivos de configuración del conjunto de datos:

* Agregue una nueva fuente de datos.
* Agregue un nuevo servidor de Data Workbench al clúster en el archivo [!DNL Profile.cfg] .
* Cambie el archivo [!DNL Cluster.cfg].
* Cambie el archivo [!DNL Log Processing.cfg] o un archivo [!DNL Log Processing Dataset Include], incluido, entre otros, lo siguiente:

   * Añadir un nuevo parámetro
   * Cambiar una transformación
   * Cambiar los parámetros Hora de inicio o Hora de finalización

* Actualice el archivo [!DNL Insight Server.exe].

También puede iniciar el reprocesamiento en cualquier momento introduciendo cualquier carácter o combinación de caracteres en el parámetro Reprocess del archivo [!DNL Log Processing.cfg] y guardando el archivo.

>[!NOTE]
>
>Para que se produzca el reprocesamiento, el parámetro Pause del archivo [!DNL Log Processing Mode.cfg] debe establecerse en false. El valor predeterminado de este parámetro es false, por lo que puede que no sea necesario cambiar el parámetro. Para obtener más información sobre [!DNL Log Processing Mode.cfg], consulte [Archivos de configuración adicionales](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Retransformación {#section-02446744549940ada8eba0573ec5575f}

Cada vez que se cambia información en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include], como cambiar una transformación o definir una nueva dimensión, la transformación se produce automáticamente.

Cada vez que cambia los archivos de búsqueda a los que se hace referencia en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include] (incluidos los archivos de búsqueda para las transformaciones [!DNL Categorize], [!DNL FlatFileLookup] y [!DNL ODBCLookup] ), debe iniciar la transformación introduciendo cualquier carácter o combinación de caracteres en el parámetro de reprocesamiento del archivo [!DNL Transformation.cfg] y guardando el archivo.
