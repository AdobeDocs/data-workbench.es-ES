---
description: El servidor de Insight permite definir dimensiones contables, simples, "varios a varios", numéricas, denormalizadas y temporales para incluirlas en su conjunto de datos.
title: Tipos de dimensiones extendidas
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Tipos de dimensiones extendidas{#types-of-extended-dimensions}

{{eol}}

El servidor de Insight permite definir dimensiones contables, simples, &quot;varios a varios&quot;, numéricas, denormalizadas y temporales para incluirlas en su conjunto de datos.

Cada tipo de dimensión tiene un conjunto de parámetros cuyos valores se editan para proporcionar instrucciones específicas para que Insight Server cree las dimensiones durante la fase de transformación de la construcción del conjunto de datos.

Aunque algunos parámetros difieren entre los tipos de dimensión, todos requieren la especificación de una dimensión principal (el parámetro Principal). La dimensión principal determina qué entradas de registro de los orígenes de registro se proporcionan como entrada para la nueva dimensión. En otras palabras, las entradas de registro asociadas a los elementos de la dimensión principal son las que están asociadas a la nueva dimensión antes de aplicar cualquier filtrado. La dimensión principal también determina la posición de la nueva dimensión dentro de la jerarquía del conjunto de datos, denominada esquema del conjunto de datos. Para obtener información sobre la interfaz que muestra el esquema del conjunto de datos, consulte [Herramientas de configuración de conjuntos de datos](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Después de que Insight Server utilice la dimensión principal para determinar qué entradas de registro deben considerarse en la creación de la dimensión, aplica las condiciones especificadas (el parámetro Condition ) para dejar en blanco las entradas de registro que no cumplen la condición. A continuación, el servidor identifica el valor del campo de entrada especificado (el parámetro Input ) para cada entrada de registro y aplica la operación especificada (el parámetro Operation ), si corresponde.

>[!NOTE]
>
>Si una entrada de registro no cumple la condición de una dimensión extendida, Insight Server sustituye los valores en blanco en todos los campos de la entrada de registro. La entrada de registro real sigue existiendo y la operación especificada determina si el valor en blanco de la variable [!DNL Input] se utiliza.
