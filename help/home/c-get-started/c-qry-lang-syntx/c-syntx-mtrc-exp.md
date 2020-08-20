---
description: Las métricas se pueden editar con el Editor de métricas y guardar en el directorio Métricas de un perfil.
solution: Analytics
title: Sintaxis de las expresiones de métricas
topic: Data workbench
uuid: 801e265d-d7e4-4f0f-9698-d0b50dd00995
translation-type: tm+mt
source-git-commit: a276b16565634fea9b693206c8a55b528fada977
workflow-type: tm+mt
source-wordcount: '851'
ht-degree: 1%

---


# Sintaxis de las expresiones de métricas{#syntax-for-metric-expressions}

Las métricas se pueden editar con el Editor de métricas y guardar en el directorio Métricas de un perfil.

Para obtener más información, consulte [Creación y edición de métricas derivadas](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40). Las expresiones de métricas también se pueden utilizar en hojas de cálculo. For more information, see [Worksheets](../../../home/c-get-started/c-analysis-vis/c-wksts/c-wksts.md#concept-45b50aafc4d84709841f14aee8022581). La siguiente sintaxis se utiliza para definir expresiones de métricas.

Notas:

1. Las palabras subrayadas deben escribirse literalmente en el texto de la expresión.
1. El formulario `{TEXT}?` representa texto opcional.
1. El formulario `{TEXT}*` representa texto que puede aparecer cero o más veces.
1. El formulario `{A | B | C |...}` representa texto que consta exactamente de una de las opciones dadas, como A, B o C....
1. El formulario `[A,B)` representa un rango de números, desde A hasta B, pero no incluido.

<table id="table_A6CA9C9F396448209398AA2A369E63FA"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Un identificador hace referencia a una métrica con nombre. Para ver las reglas que rigen los identificadores legales, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-id.md#concept-735fa36fc49643269b3646aaaa8f2fa8"> Sintaxis para los identificadores </a>. </p> <p>Ejemplo: Ingresos = Precio_Total </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(Métrica) </p> </td> 
   <td colname="col2"> <p>El resultado de (Métrica) es el mismo que el resultado de Métrica. Los paréntesis especifican el orden de las operaciones en una expresión. </p> <p>Ejemplo: Promedio = (A + B) / 2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A + B </p> </td> 
   <td colname="col2"> <p>Suma de los resultados de las Métricas A y B. </p> <p>Ejemplo: Valor = Ingresos + Costo_Ahorros </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A - B </p> </td> 
   <td colname="col2"> <p>Diferencia de los resultados de las Métricas A y B. </p> <p>Ejemplo: Beneficio = Ingresos - Costo </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A * B </p> </td> 
   <td colname="col2"> <p>Producto de los resultados de las Métricas A y B. </p> <p>Ejemplo: Dólares = centavos * 0,01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Campaña A/B </p> </td> 
   <td colname="col2"> <p>Proporción de los resultados de las métricas A y B. </p> <p>Ejemplo: Revenue_per_Session = Ingresos / Sesiones </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>A ^ B </p> </td> 
   <td colname="col2"> <p>Resultado de la métrica A elevado a la potencia del resultado de la métrica B. </p> <p>Ejemplo: Área = anchura^2 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confianza(métrica) </p> </td> 
   <td colname="col2"> <p>Una estimación de la desviación estándar de la métrica. Esto se calcula utilizando una técnica de muestreo conocida como "chackking". </p> <p>Esta métrica utiliza mucha memoria y no debe utilizarse en tablas grandes. </p> <p>Para utilizar esta sintaxis, debe tener una dimensión de navaja (denominada "jackcuchillo") con las propiedades correspondientes. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe. </p> <p>Ejemplo: trust(average_Score) </p> <p> <p>Nota:  Los tipos de métricas de confianza, incluidas la confianza (métrica) y la confianza (métrica, jacknife), son especialmente útiles cuando se utiliza la funcionalidad de experimentación controlada de Adobe. Si una métrica subió del 12 % al 16 % durante un experimento controlado, puede utilizar una llamada de confianza para calcular las probabilidades de que el salto se deba a variaciones aleatorias. Esto puede ayudarle a evitar sacar conclusiones equivocadas de una evidencia limitada y, a la inversa, puede ofrecer garantías de que un cambio cuestionable es en realidad real. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>confianza(métrica, navaja) </p> </td> 
   <td colname="col2"> <p>Una estimación de la desviación estándar de la métrica. Esto se calcula utilizando una técnica de muestreo conocida como "chackking". Esta sintaxis le permite determinar la confianza de una métrica mediante una dimensión de navaja denominada "navaja". </p> <p>Esta métrica utiliza mucha memoria y no debe utilizarse en tablas grandes. </p> <p>Para utilizar esta sintaxis, debe tener una dimensión de navaja (denominada algo que no sea "jackcuchillo") con las propiedades correspondientes. Para obtener más información, póngase en contacto con los servicios de consultoría de Adobe. </p> <p>Ejemplo: trust(average_Score,SubSamples) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>eval(CellReference) </p> </td> 
   <td colname="col2"> <p>Trata el contenido de la celda a la que hace referencia como una expresión de métrica. Esta sintaxis solo se puede utilizar en una visualización de hoja de cálculo. </p> <p>Ejemplo: eval(B1) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>log (B, X) </p> </td> 
   <td colname="col2"> <p>La función logaritmo matemático: La métrica X es el parámetro y la métrica B es la base. </p> <p>Ejemplo: dB = 20*log(Amplitud,10) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métrica[Filtro] </p> </td> 
   <td colname="col2"> <p>"Métrica donde filtro": Una nueva métrica filtrada por el filtro dado. </p> <p>Ejemplo: Jan_Sessions = Sesiones[ Month="Jan" ] </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métrica por Dimension </p> </td> 
   <td colname="col2"> <p>Una métrica evaluada en el "nivel" de la dimensión. El resultado de (M por X)[F] (el resultado de la métrica "M por X" evaluada con el filtro "F") es el resultado de M[F por X] (el resultado de la métrica "M" evaluada con el filtro "F por X"). </p> <p>Ejemplo: AB_Visitantes = </p> <p>(Visitantes por sesión)[Página="A" y Página="B"] = </p> <p>Visitantes[(Página="A" y Página="B") por sesión] = </p> <p>El número de Visitantes que visitaron la página A y la página B en la misma sesión. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>entero </p> </td> 
   <td colname="col2"> <p>Una métrica con un valor fijo. </p> <p>Ejemplo: Pi = 3,1415 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(Métrica) </p> </td> 
   <td colname="col2"> <p>Omite cualquier dimensión sobre la cual se evalúe la métrica. La métrica tiene el mismo valor para cada elemento de esa dimensión. </p> <p>Ejemplo: Pct_of_Visitantes = Visitantes / total(Visitantes) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>all(Métrica) </p> </td> 
   <td colname="col2"> <p>Omite los filtros que se aplican a la métrica. Las selecciones y otros filtros no afectan a la métrica. </p> <p>Ejemplo: Benchmark_Sessions = all( Sesiones ) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>total(todas(métricas)) </p> </td> 
   <td colname="col2"> <p>Omite todos los filtros y dimensiones. Tiene el mismo valor a lo largo de un determinado perfil, independientemente de los filtros o dimensiones que se apliquen. </p> <p>Ejemplo: Dataset_Visitantes = total(todos(Visitantes)) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(One,Countable_Dimension) </p> </td> 
   <td colname="col2"> <p>Métrica que proporciona el recuento de una dimensión contable, como Visitante o Sesión. </p> <p>Ejemplo: Visitantes = sum(Uno,Visitante) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sum(Numeric_ Dimension, Countable_ Dimension) </p> </td> 
   <td colname="col2"> <p>Métrica que proporciona la suma de una dimensión numérica sobre una dimensión contable. Se utilizan los valores ordinales (a diferencia de los valores formateados) de los elementos de la dimensión numérica, por lo que a menudo se debe aplicar un factor de escala al resultado. </p> <p>Ejemplo: Valor = sum(Session_Value, Session)*0.01 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>min(A, B) </p> </td> 
   <td colname="col2"> <p>Resultados menores de las métricas A y B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>max(A, B) </p> </td> 
   <td colname="col2"> <p>Los buenos resultados de la métrica A y la métrica B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>format(A, B) </p> </td> 
   <td colname="col2"> <p>Una métrica que es idéntica a la métrica A, excepto que utiliza la función de formato de la métrica B. </p> </td> 
  </tr> 
 </tbody> 
</table>

