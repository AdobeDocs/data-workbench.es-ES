---
description: Las notas de la versión de Área de trabajo de datos 6.1 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.
solution: Analytics
title: Notas de la versión de Área de trabajo de datos 6.2
topic: Data workbench
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.1 Release Notes{#data-workbench-release-notes}

Las notas de la versión de Área de trabajo de datos 6.1 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.

## Nuevas funciones {#section-1225066ea8f44cf68e42e019d0bca816}

Área de trabajo de datos 6.1 incluye estas nuevas funciones:

| Funciones  | Descripción |
|--- |--- |
| Actualización de Windows de 64 bits | Los componentes del servidor del área de trabajo de datos, el servidor de informes y el cliente se actualizan para que se ejecuten únicamente en sistemas operativos Windows de 64 bits. |
| Puntuación de tendencia | La puntuación de la audiencia le permite identificar la lealtad del cliente y percibir estadísticamente quién puede convertir una venta o interactuar con un artículo o una campaña. La puntuación de tendencia ahora incluye estas visualizaciones para ver modelos y mostrar la correlación cambiante de las métricas seleccionadas.<ul><li>El visor de modelos examina un modelo de regresión logística generado con Puntuación de tendencia, que muestra los coeficientes de ponderación de cada variable de entrada (incluido el término constante) y su rango de error estadístico. </li><li>Los gráficos de alza y ganancia se utilizan para evaluar el aumento potencial de un modelo de datos puntuado.</li><li>La matriz de confusión ofrece cuatro recuentos por la combinación de Real Positive (AP), Real Negative (AN), Predicted Positive (PP) y Predicted Negative (PN).</li> <li>A partir de la versión 6.1, ahora tiene la opción Guardar para guardar las puntuaciones de tendencia en dos tipos: dimensiones o dimensiones y métricas.</li><li>Ahora puede hacer clic en Ctrl-Alt y arrastrar y soltar para agregar elementos en Puntuación de tendencia y en el Generador de clústeres. Antes de agregar elementos de tabla, tenía que arrastrarlos de la tabla al cuadro Elementos.</li></ul> |
| Área de trabajo de datos ahora en chino | El área de trabajo de datos ahora admite el chino simplificado para la aplicación cliente. El área de trabajo de datos también admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales. |
| Funciones matemáticas | Ahora puede agregar funciones matemáticas a métricas, transformaciones matemáticas y celdas de hojas de cálculo para calcular más adelante conjuntos de datos. |
| Llamadas estadísticas | Las tablas ahora ofrecen una llamada de resumen de estadísticas para las columnas de métricas. La llamada de salida puede mostrar la media, la desviación estándar, los valores mínimo y máximo, la varianza y el recuento total de la columna. Se puede incluir en cualquier selección y evaluación. |
| Filtro de matriz de correlación | La matriz de correlación se ha actualizado con un filtro binario para permitirle restringir los valores de una o ambas métricas correlacionadas, permitiéndole enfocar mejor la comparación. Además, ahora puede agregar elementos de dimensión desde una tabla de dimensiones haciendo clic en Ctrl + Alt y arrastrando elementos a la columna o fila de matriz que se va a evaluar. |
| Ocultar etiqueta de visitas en el orden previsto en la visualización de canales | Alternar entre mostrar y ocultar etiquetas de visitas en el orden previsto en una visualización de canal; para ello, haga clic con el botón secundario en el título y seleccione Ocultar visitas en el orden previsto. |

## Ordenar columnas de tabla{#sorting-table-columns}

Ordene las columnas de la tabla alfabéticamente o por ordinales.

Para seleccionar mejor los elementos de una tabla de dimensión, puede ordenar la primera columna alfabéticamente o mediante ordinales seleccionando la opción de **[!UICONTROL Sort]** menú.

El carácter # se mostrará cuando una columna se ordene por ordinales (valor predeterminado).

**Seleccionar opción de ordenación**

Para cambiar las opciones de ordenación entre ordinal y alfabeto, haga clic con el botón derecho y seleccione **[!UICONTROL Sort]**. Haga clic en la flecha para invertir el orden.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Puede ordenar otras columnas mediante ordinal haciendo clic en el nombre de la columna.

## Ocultar etiquetas de visitas en el orden previsto en el canal

Alternar para abrir etiquetas de visitas en el orden previsto en una visualización de canal.

La visualización de canal identifica dónde un cliente abandona una campaña de marketing o se desvía de una ruta de conversión definida mientras interactúa con su sitio web o campaña multicanal. El lado izquierdo de la visualización Canal muestra los resultados de una visita o de los visitantes, mientras que el lado derecho muestra las visitas en el orden previsto de aquellos que abandonan una ruta especificada.

![](assets/c_funnel_hide_fallout.png)

En una **[!UICONTROL Funnel]** visualización, puede hacer clic con el botón derecho en el título y seleccionar **[!UICONTROL Hide Fallout]** en el menú para ocultar las etiquetas de visitas en el orden previsto.

## Problemas conocidos {#section-ff2180c6871c413480e15fa915c253b9}

* Al importar un espacio de trabajo, se muestra un mensaje de error aunque la importación se haya realizado correctamente.

   Solución: Haga clic en Aceptar para ignorar el error. El espacio de trabajo se importa correctamente.

**Problemas de localización de chino simplificado**

* El título del cuadro de diálogo y el mensaje que se muestran después de hacer clic en &quot;Enviar&quot; al establecer el objetivo en la visualización Puntuación son ilegibles.

   Solución: Ninguno.
* Al utilizar el ajuste de palabras en la visualización de hoja de cálculo, las palabras localizadas no se ajustan correctamente. Se están agregando caracteres extra no deseados a la cadena.

   Solución: Ninguno
* No se puede iniciar [!DNL Insight.exe] si el directorio de instalación tiene caracteres que no sean en inglés.

   Solución: Mantenga los nombres predeterminados o cambie el nombre utilizando solo caracteres ingleses en la ruta de la carpeta para iniciar los ejecutables.
