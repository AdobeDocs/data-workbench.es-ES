---
description: La transformación Acoplar toma un vector de cadenas y asigna cada valor a su propio campo.
title: Flatten
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
exl-id: 63f3e4bc-238f-4e15-8ae5-2f805bd080d3
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 4%

---

# Flatten{#flatten}

La transformación Acoplar toma un vector de cadenas y asigna cada valor a su propio campo.

| Parámetro | Descripción | Predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Puede introducir cualquier nombre aquí. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Predeterminado | El valor predeterminado que se debe utilizar si se cumple la condición y el valor de entrada no está disponible para la entrada de registro. |  |
| Entrada | Un vector de valores de cadena que se asignará a los nombres de campo de salida. |  |
| Salidas | Conjunto de nombres de campo de salida. |  |

Consideraciones para [!DNL Flatten]

* Si el vector de entrada contiene más valores de los que hay campos de salida definidos, los valores de entrada adicionales simplemente se pierden.
* Si el vector de entrada contiene menos valores que los campos de salida definidos, los campos de salida adicionales reciben el valor predeterminado (si se definen) o una cadena vacía si no se define ningún valor predeterminado.

En este caso, la transformación [!DNL Flatten] se utiliza para tomar un vector de productos (x-productos) y separarlos en cuatro campos (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Si el valor de entrada contenía las cadenas B57481, C46355 y Z97123, los campos de salida tendrían los valores que se muestran aquí:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vacío (hay más entradas que salidas y no se ha especificado ningún valor predeterminado).
