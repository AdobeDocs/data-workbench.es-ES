---
description: El servidor de Insight permite definir dimensiones contables, simples, de varios a varios, numéricas, denormalizadas y de tiempo para su inclusión en el conjunto de datos.
solution: Analytics
title: Tipos de dimensiones extendidas
topic: Data workbench
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipos de dimensiones extendidas{#types-of-extended-dimensions}

El servidor de Insight permite definir dimensiones contables, simples, de varios a varios, numéricas, denormalizadas y de tiempo para su inclusión en el conjunto de datos.

Cada tipo de dimensión tiene un conjunto de parámetros cuyos valores se editan para proporcionar instrucciones específicas al servidor de Insight para crear las dimensiones durante la fase de transformación de la construcción de conjuntos de datos.

Aunque algunos parámetros difieren entre los tipos de dimensión, todos requieren la especificación de una dimensión principal (el parámetro Principal). La dimensión principal determina qué entradas de registro de los orígenes de registro se proporcionan como entrada a la nueva dimensión. En otras palabras, las entradas de registro que están asociadas con los elementos de la dimensión principal son las que están asociadas con la nueva dimensión antes de aplicar cualquier filtro. La dimensión principal también determina la posición de la nueva dimensión dentro de la jerarquía del conjunto de datos, denominada esquema del conjunto de datos. Para obtener información sobre la interfaz que muestra el esquema del conjunto de datos, consulte Herramientas [de configuración](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)de conjuntos de datos.

Después de que el servidor de Insight utilice la dimensión principal para determinar qué entradas de registro se deben tener en cuenta al crear la dimensión, aplica las condiciones especificadas (el parámetro Condition) para dejar en blanco las entradas de registro que no cumplen la condición. A continuación, el servidor identifica el valor del campo de entrada especificado (el parámetro Input) para cada entrada de registro y aplica la operación especificada (el parámetro Operation), si corresponde.

>[!NOTE]
>
>Si una entrada de registro no cumple una condición de dimensión extendida, el servidor de perspectiva sustituye los valores en blanco para todos los campos de la entrada de registro. La entrada de registro real aún existe y la operación especificada determina si se utiliza el valor en blanco del [!DNL Input] campo.

