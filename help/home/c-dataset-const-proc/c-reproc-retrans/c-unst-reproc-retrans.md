---
description: Durante el reprocesamiento, el servidor del área de trabajo de datos reconstruye el conjunto de datos tal como se especificó en los archivos de configuración del conjunto de datos de transformación y procesamiento de registros.
solution: Analytics
title: Explicación del reprocesamiento y la transformación
topic: Data workbench
uuid: 0253bc8c-8883-41eb-8a9f-e0685613ff5c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Explicación del reprocesamiento y la transformación{#understanding-reprocessing-and-retransformation}

Durante el reprocesamiento, el servidor del área de trabajo de datos reconstruye el conjunto de datos tal como se especificó en los archivos de configuración del conjunto de datos de transformación y procesamiento de registros.

Para ello, el servidor del área de trabajo de datos (InsightServer64.exe) debe completar la fase de procesamiento del registro y la fase de transformación de la construcción de conjuntos de datos. Cuando termina el procesamiento del registro, se desencadena la transformación automáticamente, pero también puede producirse la transformación independientemente del procesamiento del registro.

Durante la fase de procesamiento del registro, los usuarios del área de trabajo de datos no tienen acceso a los datos del conjunto de datos. Durante la fase de transformación, los usuarios del área de trabajo de datos tienen acceso a los datos actualizados, pero los datos se muestrean en lugar de completarse. El análisis de datos puede continuar durante la transformación, pero las consultas se completarán tan pronto como se produzca la transformación.

## Reprocesamiento {#section-92f1e46bf1534b3dba39e9493190b8ab}

Cada vez que se completa una de las siguientes tareas, el procesamiento de registros y, por lo tanto, la transformación, se produce automáticamente para reconstruir el conjunto de datos como se especificó en los archivos de configuración del conjunto de datos:

* Agregue una nueva fuente de datos.
* Agregue un nuevo servidor del área de trabajo de datos al clúster en el [!DNL Profile.cfg] archivo.
* Cambie el [!DNL Cluster.cfg] archivo.
* Cambie el [!DNL Log Processing.cfg] archivo o un [!DNL Log Processing Dataset Include] archivo, incluso lo siguiente, entre otros:

   * Agregar un parámetro nuevo
   * Cambiar una transformación
   * Cambiar los parámetros Hora de inicio o Hora de finalización

* Actualice el [!DNL Insight Server.exe] archivo.

También puede iniciar el reprocesamiento en cualquier momento introduciendo cualquier carácter o combinación de caracteres en el parámetro Reprocesar del [!DNL Log Processing.cfg] archivo y guardando el archivo.

>[!NOTE]
>
>Para que se vuelva a procesar, el parámetro Pausa del [!DNL Log Processing Mode.cfg] archivo debe establecerse en false. El valor predeterminado de este parámetro es false, por lo que puede que no sea necesario cambiar el parámetro. Para obtener más información sobre [!DNL Log Processing Mode.cfg], consulte Archivos de configuración [adicionales](/help/home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md).

## Retransformación {#section-02446744549940ada8eba0573ec5575f}

Cada vez que se cambia cualquier información del [!DNL Transformation.cfg] archivo o de un [!DNL Transformation Dataset Include] archivo, como cambiar una transformación o definir una nueva dimensión, la transformación se produce automáticamente.

Cada vez que cambie los archivos de búsqueda a los que se hace referencia en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo (incluidos los archivos de búsqueda para [!DNL Categorize], [!DNL FlatFileLookup]y [!DNL ODBCLookup] transformaciones), debe iniciar la transformación introduciendo cualquier carácter o combinación de caracteres en el parámetro Reprocesar del [!DNL Transformation.cfg] archivo y guardando el archivo.
