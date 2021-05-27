---
description: La transformación PullNameValues es una operación especial que toma los valores del campo cs-uri-query y separa cada uno de los pares nombre-valor en una cadena independiente.
title: PullNameValues
uuid: b24db987-78e8-4afc-9113-89aedc0170b2
exl-id: 3660ff6e-87dc-42cf-a897-0e2e0e021c07
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 4%

---

# PullNameValues{#pullnamevalues}

La transformación PullNameValues es una operación especial que toma los valores del campo cs-uri-query y separa cada uno de los pares nombre-valor en una cadena independiente.

La colección completa de cadenas de par nombre-valor se muestra en el campo de salida especificado como un vector de cadenas.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible en la entrada de registro determinada. |  |
| Salida | Nombre de la cadena de salida. |  |

La transformación [!DNL PullNameValues] se utiliza en este ejemplo para capturar el uso del formulario de búsqueda por parte de los visitantes: qué botones se han seleccionado, qué valores se han escrito en el formulario, etc. El ejemplo utiliza una condición [!DNL String Match] (consulte [Conditions](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) para aislar el uso de esta transformación a la página [!DNL /search.php] únicamente. El vector de pares de nombre-valor se muestra en el campo x-search-namevalúa.

![](assets/cfg_TransformationType_PullNameValues.png)

Utilizando la transformación definida anteriormente, si el campo cs-uri-stem coincidía con la página [!DNL /search.php] y la consulta cs-uri contenía lo siguiente:

* Searchfor=Bob&amp;State=Virginia&amp;isMale=true

a continuación, x-search-namevalues contendría un vector que contenía las tres cadenas siguientes:

* Searchfor=Bob
* Estado=Virginia
* isMale=true
