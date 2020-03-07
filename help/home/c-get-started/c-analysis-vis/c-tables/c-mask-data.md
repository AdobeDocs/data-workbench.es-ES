---
description: El enmascaramiento se refiere a seleccionar un subconjunto de los datos o un subconjunto de los elementos de una dimensión.
solution: Analytics
title: Datos de máscara
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Datos de máscara{#mask-data}

El enmascaramiento se refiere a seleccionar un subconjunto de los datos o un subconjunto de los elementos de una dimensión.

Puede enmascarar u ocultar los elementos que no desee incluir en el análisis.

Área de trabajo de datos proporciona dos métodos para enmascarar elementos de dimensión. El primer método emplea las opciones disponibles en el [!DNL Mask] menú. Con las opciones del [!DNL Mask] menú, puede utilizar el ratón para seleccionar los elementos que se van a mostrar o enmascarar, o bien mostrar los elementos de mayor clasificación cuando ordena los datos por métrica. El segundo método para enmascarar elementos de dimensión emplea una búsqueda.

**Para enmascarar datos**

1. Haga clic con el botón derecho en un elemento o en la etiqueta de la dimensión deseada y haga clic en **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Haga clic en una de las opciones siguientes:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** o **[!UICONTROL 500]** de los elementos mostrados ordenados por métrica
   * **[!UICONTROL Show top > All Positive]** para mostrar solo los valores buenos que no sean cero (0)
   * **[!UICONTROL Display “X more”]** para mostrar el número de elementos con máscara actualmente
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(disponible solo cuando se trabaja con una dimensión denormalizada)

      Al trabajar con una dimensión denormalizada, esta opción le permite enmascarar una dimensión mediante una dimensión contable. Cuando se selecciona, la tabla muestra solamente los elementos que tienen al menos un elemento de la dimensión contable que ha seleccionado. La tabla muestra hasta 1023 elementos.

>[!NOTE]
>
>Dado que Adobe [!DNL Platform] procesa los datos en orden aleatorio, cuando al menos una máscara resulta en más de 1023 elementos, los elementos más comunes y los más grandes tienen buenas posibilidades de incluirse en la tabla.

Cuando enmascara por Mostrar arriba o Por lo menos uno, de forma predeterminada el orden de la tabla corresponde a los valores afectados por la selección en ese momento. Si más adelante cambia la selección, el orden no cambia con respecto al orden original a menos que se reactive la tabla o se active la selección dinámica. Al hacer clic en **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, la tabla se reinicia cada vez que cambia la selección.

**Para enmascarar datos mediante una búsqueda**

* Puede enmascarar datos mediante cualquiera de las siguientes opciones de búsqueda:

   * Haga clic con el botón secundario en un elemento o en la etiqueta de la dimensión deseada, haga clic en **[!UICONTROL Mask]** y, a continuación, en el [!DNL Search] cuadro escriba la frase para la que desee buscar.

      ![](assets/mnu_Table_MaskSearch.png)

   * Haga clic con el botón secundario en un elemento o en la etiqueta de la dimensión deseada, haga clic en **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]** y, a continuación, en el cuadro de búsqueda que se muestra en la celda de la etiqueta de dimensión, escriba la frase para la que desee buscar.

      ![](assets/vis_Table_Mask_searchBar.png)

      A medida que escribe una frase de búsqueda, Área de trabajo de datos actualiza la dimensión para reflejar coincidencias.

Para restringir aún más la máscara durante una búsqueda, puede utilizar cualquiera de los siguientes métodos:

* Puede escribir &quot;re:&quot; en el [!DNL search] cuadro o en la barra para que la frase de búsqueda se interprete como una expresión regular. Puede utilizar cualquiera de las sintaxis asociadas con expresiones regulares en la frase de búsqueda. Para obtener más información sobre las expresiones regulares, consulte el apéndice Expresión regular en la Guía *de configuración de* Dataset.
* Puede escribir el símbolo $ como el primer carácter de la cadena de búsqueda para encontrar frases que comiencen con la cadena que ha introducido, o como el último carácter para encontrar frases que terminen con la cadena que ha introducido.
* Puede escribir un espacio como el primer carácter de la cadena de búsqueda para encontrar cualquier palabra dentro de una frase que comience con la cadena que ha introducido o como el último carácter para encontrar cualquier palabra dentro de una frase que termine con la cadena que ha introducido.

A continuación se muestran ejemplos de diferentes formas de enmascarar una tabla mediante la cadena &quot;on&quot; en una búsqueda:

* Al escribir &quot;on&quot; se muestran todas las frases que contienen la cadena &quot;on&quot; en cualquier parte de la frase: &quot;banca **** en línea&quot;, &quot;compradores de **** contacto&quot;, &quot;monedas de **billones** &quot;, &quot;bancos **** en línea&quot;, &quot;**** opciones de oro&quot; y &quot;**billones** de plata&quot;.
* Al escribir &quot;$on&quot; se muestran todas las frases que comienzan con la cadena &quot;on&quot;:

   &quot;banca **** en línea&quot; y &quot;pago **en línea**&quot;.

* Al escribir &quot;on$&quot; se muestran todas las frases que finalizan con la cadena &quot;on&quot;:

   &quot;**Billón** de plata&quot; y &quot;**opción** de oro&quot;.

* Al escribir &quot;on&quot; se muestran todas las frases que contienen una palabra que comienza con la cadena &quot;on&quot;:

   &quot;banca **** en línea&quot; y &quot;banco **** en línea&quot;.

* Al escribir &quot;on&quot; se muestran todas las frases que contienen una palabra que termina con la cadena &quot;on&quot;:

   &quot;**monedas de billón** &quot; y &quot;**lingotes** de plata&quot;.

* El uso de &quot;on&quot; muestra todas las frases que contienen la cadena &quot;on&quot; como una palabra:

   &quot;banca **en línea&quot; y &quot;banca** en línea **** &quot;.

