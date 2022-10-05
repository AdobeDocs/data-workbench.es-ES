---
description: Muchos de los perfiles internos que recibió con su aplicación de Adobe incluyen sus propios archivos de configuración de conjuntos de datos.
title: Acerca de los archivos de inclusión de conjunto de datos
uuid: e04d412e-7d73-4a7d-b0b6-0c2347c6201b
exl-id: a23d3f83-4e92-4787-9f77-ee9914cb8893
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 4%

---

# Acerca de los archivos de inclusión de conjunto de datos{#about-dataset-include-files}

{{eol}}

Muchos de los perfiles internos que recibió con su aplicación de Adobe incluyen sus propios archivos de configuración de conjuntos de datos.

Dado que los perfiles internos son subperfiles del perfil del conjunto de datos, sus archivos de configuración del conjunto de datos contienen reglas que proporcionan parámetros adicionales para las fases de procesamiento de registros o transformación de la construcción del conjunto de datos. Los archivos de configuración del conjunto de datos para perfiles internos y para cualquier perfil heredado que cree se denominan archivos de inclusión de conjunto de datos.

Un archivo de inclusión de conjunto de datos contiene un subconjunto de los parámetros contenidos en los archivos de configuración del conjunto de datos principal ( [!DNL Log Processing.cfg] o [!DNL Transformation.cfg]) para el perfil del conjunto de datos. Los conjuntos de datos incluyen archivos que contienen parámetros asociados con el procesamiento de registros se denominan [!DNL Log Processing Dataset Include] archivos (consulte [Archivos de inclusión de conjunto de datos de procesamiento de registros](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab)), mientras que el conjunto de datos incluye archivos asociados a la transformación se llaman [!DNL Transformation Dataset Include] Archivos. Consulte [Archivos de inclusión de conjunto de datos de transformación](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace). Puede crear varios archivos de inclusión de conjuntos de datos para utilizarlos en el proceso de construcción del conjunto de datos. El conjunto de datos completo incluye todos los campos, transformaciones y dimensiones extendidas definidos en todos los archivos de configuración del conjunto de datos para el perfil del conjunto de datos y cualquier perfil heredado.
