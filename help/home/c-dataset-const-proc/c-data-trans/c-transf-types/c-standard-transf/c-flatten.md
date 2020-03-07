---
description: La transformación Acoplar toma un vector de cadenas y asigna cada valor a su propio campo.
solution: Analytics
title: Acoplar
topic: Data workbench
uuid: 00b06a5c-506b-45fe-9773-44d65b8ec233
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acoplar{#flatten}

La transformación Acoplar toma un vector de cadenas y asigna cada valor a su propio campo.

| Parámetro | Descripción | Valor predeterminado |
|---|---|---|
| Nombre | Nombre descriptivo de la transformación. Aquí puede introducir cualquier nombre. |  |
| Comentarios | Opcional. Notas sobre la transformación. |  |
| Condición | Condiciones en las que se aplica esta transformación. |  |
| Valor predeterminado | El valor predeterminado que se usará si se cumple la condición y el valor de entrada no está disponible para la entrada de registro. |  |
| Entrada | Un vector de valores de cadena que se asignará a los nombres de campo de salida. |  |
| Salidas | Conjunto de nombres de campo de salida. |  |

Consideraciones para [!DNL Flatten]

* Si el vector de entrada contiene más valores de los que hay campos de salida definidos, los valores de entrada adicionales simplemente se eliminan.
* Si el vector de entrada contiene menos valores que los campos de salida definidos, los campos de salida adicionales reciben el valor predeterminado (si se definen) o una cadena vacía si no se define ningún valor predeterminado.

Aquí, la [!DNL Flatten] transformación se utiliza para tomar un vector de productos (x-products) y separarlos en cuatro campos (x-product1, ..., x-product4).

![](assets/cfg_TransformationType_Flatten.png)

Si el valor de entrada contenía las cadenas B57481, C46355 y Z97123, los campos de salida tendrían los valores que se muestran aquí:

* x-product1 = B57481
* x-product2 = C46355
* x-product3 = Z97123
* x-product4 = Vacío (hay más entradas que salidas y no se ha especificado ningún valor predeterminado).

