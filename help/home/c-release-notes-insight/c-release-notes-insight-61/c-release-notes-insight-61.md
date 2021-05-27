---
description: Las notas de la versión de la Data Workbench 6.1 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.
title: Notas de la versión Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# Notas de la versión Data Workbench 6.1{#data-workbench-release-notes}

Las notas de la versión de la Data Workbench 6.1 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.

## Nuevas funciones {#section-1225066ea8f44cf68e42e019d0bca816}

La Data Workbench 6.1 incluye estas nuevas funciones:

| Funciones | Descripción |
|--- |--- |
| Actualización de Windows de 64 bits | Los componentes servidor de Data Workbench, servidor de informes y cliente se actualizan para que se ejecuten únicamente en sistemas operativos Windows de 64 bits. |
| Puntuación de tendencia | La puntuación de la audiencia le permite identificar la lealtad del cliente y percibir estadísticamente quién probablemente convierta una venta o interactúe con un artículo o una campaña. La puntuación de tendencia ahora incluye estas visualizaciones para ver modelos y mostrar la correlación cambiante de las métricas seleccionadas.<ul><li>El visor de modelos examina un modelo de regresión logística generado con la Puntuación de tendencia, mostrando las ponderaciones de coeficiente de cada variable de entrada (incluido el término constante) y su intervalo de errores estadístico. </li><li>Los gráficos de alza y ganancia se utilizan para evaluar el aumento potencial de un modelo de datos puntuado.</li><li>La matriz de confusión ofrece cuatro recuentos por la combinación de Positivo Real (AP), Negativo Real (AN), Predicted Positive (PP) y Predicted Negative (PN).</li> <li>A partir de la versión 6.1, ahora tiene la opción Guardar para guardar las puntuaciones de tendencia en dos tipos: dimensiones, dimensiones y métricas.</li><li>Ahora puede hacer clic en Ctrl-Alt y arrastrar y soltar para agregar elementos en Puntuación de tendencia y el Generador de clústeres. Anteriormente, para agregar elementos de tabla, había que arrastrarlos de la tabla al cuadro Elementos .</li></ul> |
| Data Workbench ahora en chino | Ahora, Data Workbench admite chino simplificado para la aplicación cliente. Data Workbench también admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales. |
| Funciones matemáticas | Ahora puede agregar funciones matemáticas a métricas, transformaciones matemáticas y celdas de hojas de cálculo para calcular más aún los conjuntos de datos. |
| Llamadas estadísticas | Las tablas ahora ofrecen un resumen de estadísticas de las columnas de métricas. La desactivación puede mostrar la media, la desviación estándar, los valores mínimo y máximo, la varianza y el recuento total de la columna. Se puede tener en cuenta en cualquier selección y evaluación. |
| Filtro de matriz de correlación | La matriz de correlación se ha actualizado con un filtro binario para permitirle restringir los valores de una o ambas métricas correlacionadas, lo que le permite enfocar mejor la comparación. Además, ahora puede agregar elementos Dimension desde una tabla Dimension haciendo clic en Ctrl + Alt y arrastrando elementos a la columna o fila matriz que desea evaluar. |
| Ocultar etiqueta de visitas en el orden previsto en la visualización de canales | Alterne entre mostrar y ocultar las etiquetas de visitas en el orden previsto en una visualización de canal; para ello, haga clic con el botón derecho en el título y seleccione Ocultar visitas en el orden previsto . |

## Ordenar columnas de tabla{#sorting-table-columns}

Ordene las columnas de la tabla alfabéticamente o por ordinales.

Para seleccionar mejor elementos en una tabla de Dimension, puede ordenar la primera columna alfabéticamente o mediante números ordinales seleccionando la opción de menú **[!UICONTROL Sort]**.

El carácter # se mostrará cuando una columna se ordene por ordinales (valor predeterminado).

**Seleccionar opción de orden**

Para cambiar las opciones de clasificación entre ordinal y alfabeto, haga clic con el botón derecho y seleccione **[!UICONTROL Sort]**. Haga clic en la flecha para invertir el orden.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Para ordenar otras columnas, haga clic en el nombre de la columna haciendo clic en ordinal.

## Ocultar etiquetas de visitas en el orden previsto en el canal

Alterne para abrir etiquetas de visitas en el orden previsto en una visualización de canal.

La visualización Embudo identifica el punto en el que un cliente abandona una campaña de marketing o se desvía de una ruta de conversión definida al interactuar con su sitio web o campaña multicanal. La parte izquierda de la visualización de canal muestra los resultados de una visita o visitantes, mientras que la derecha muestra las &quot;Visitas en el orden previsto&quot; de aquellos que abandonan una ruta especificada.

![](assets/c_funnel_hide_fallout.png)

En una visualización **[!UICONTROL Funnel]**, puede hacer clic con el botón derecho en el título y seleccionar **[!UICONTROL Hide Fallout]** en el menú para ocultar las etiquetas de visitas en el orden previsto.

## Problemas conocidos {#section-ff2180c6871c413480e15fa915c253b9}

* Al importar un espacio de trabajo, se muestra un mensaje de error aunque la importación se haya realizado correctamente.

   Solución alternativa: Haga clic en OK para ignorar el error. El espacio de trabajo se importa correctamente.

**Problemas de localización de chino simplificados**

* El título del cuadro de diálogo y el mensaje que se muestran después de hacer clic en &quot;Enviar&quot; al configurar el objetivo en la visualización Puntuación son ilegibles.

   Solución alternativa: Ninguno.
* Al utilizar ajuste de palabras en la visualización de hoja de cálculo, las palabras localizadas no se ajustan correctamente. Se añaden caracteres extra no deseados a la cadena.

   Solución alternativa: Ninguna
* No se puede iniciar [!DNL Insight.exe] si el directorio de instalación tiene un nombre que no sea inglés.

   Solución alternativa: Mantenga los nombres predeterminados o cambie el nombre utilizando solo caracteres ingleses en la ruta de la carpeta para iniciar los ejecutables.
