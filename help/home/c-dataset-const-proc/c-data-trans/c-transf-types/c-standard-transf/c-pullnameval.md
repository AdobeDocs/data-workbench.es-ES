---
description: La transformación PullNameValues es una operación especial que toma los valores del campo cs-uri-query y separa cada uno de los pares nombre-valor en una cadena independiente.
solution: Analytics
title: PullNameValues
topic: Data workbench
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# PullNameValues{#pullnamevalues}

La transformación PullNameValues es una operación especial que toma los valores del campo cs-uri-query y separa cada uno de los pares nombre-valor en una cadena independiente.

Toda la colección de cadenas de par nombre-valor se genera en el campo de salida especificado como un vector de cadenas.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible en la entrada de registro dada. |  |
| Salida | Nombre de la cadena de salida. |  |

La [!DNL PullNameValues] transformación se utiliza en este ejemplo para capturar el uso del formulario de búsqueda por parte de los visitantes: qué botones se han seleccionado, qué valores se han escrito en el formulario, etc. El ejemplo utiliza una [!DNL String Match] condición (consulte [Condiciones](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) para aislar el uso de esta transformación solo en la página [!DNL /search.php]. El vector de pares nombre-valor se incluye en el campo x-search-namevalues.

![](assets/cfg_TransformationType_PullNameValues.png)

Utilizando la transformación definida anteriormente, si el campo cs-uri-stem coincidía con la página [!DNL /search.php] y cs-uri-query contenía lo siguiente:

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

entonces x-search-namevalues contendría un vector que contiene las tres cadenas siguientes:

* Searchfor=Bob
* Estado=Virginia
* isMale=true

