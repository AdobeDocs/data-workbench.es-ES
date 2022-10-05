---
description: Un filtro es una expresión que define un subconjunto de los datos de un conjunto de datos.
title: Sintaxis para expresiones de filtro
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
exl-id: 515c1645-69c8-4990-a913-d2d505c6fe51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# Sintaxis para expresiones de filtro{#syntax-for-filter-expressions}

{{eol}}

Un filtro es una expresión que define un subconjunto de los datos de un conjunto de datos.

Un filtro admite o rechaza cada elemento de cada dimensión según las relaciones entre dimensiones.

Los filtros se pueden editar con la variable [!DNL Filter Editor]. Consulte [Editores de filtros](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

En la tabla siguiente, cada descripción de sintaxis incluye un ejemplo de una expresión de métrica que utiliza ese filtro. Por ejemplo, Sesiones[True] es una métrica definida con el filtro &quot;Verdadero&quot;. Las sesiones[True] es la misma que la métrica Sesiones porque el filtro Verdadero admite todos los elementos de la dimensión Sesión .

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtro constante. Admite todos los elementos de cada dimensión </p> <p>Ejemplo: Sessions[ True ] es lo mismo que Sessions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>False </p> </td> 
   <td colname="col2"> <p>Filtro constante. Rechaza todos los elementos de cada dimensión. </p> <p>Ejemplo: Sessions[ False ] siempre es cero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no filtrar </p> </td> 
   <td colname="col2"> <p>Admite los elementos que Filter rechaza. </p> <p>Ejemplo: Sessions[ not Page="A" ] es el número de sesiones que no visitaron la página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA y FilterB </p> </td> 
   <td colname="col2"> <p>Admite los elementos que admiten FilterA y FilterB. </p> <p>Ejemplo: Sessions[ Page="A" y Page="B" ] es el número de sesiones que visitaron la página A y la página B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FiltroA o FiltroB </p> </td> 
   <td colname="col2"> <p>Admite los elementos que admiten FilterA o FilterB. </p> <p>Ejemplo: Sessions[ Page="A" o Page="B" ] es el número de sesiones que visitaron la página A, la página B o ambas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrar por atenuación </p> </td> 
   <td colname="col2"> <p>Admite el conjunto de elementos de la dimensión Dim admitidos por Filter. </p> <p>Ejemplo: Sessions[ Page="/home" by Visitor ] es el número de sesiones que pertenecen a un visitante que vio la página "/home". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Filtros de referencia definidos de otro modo en el perfil. </p> <p>Ejemplo: Sessions[ Broken_Session_Filter ] es el número de sesiones admitidas por el filtro de sesión interrumpida. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Valor" </p> </td> 
   <td colname="col2"> <p>Admite el elemento dado de la dimensión Dim. </p> <p>Ejemplo: Sessions[ Page="A" ] es el número de sesiones que visitaron la página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>¡Dim!= “Valor” </p> </td> 
   <td colname="col2"> <p>Admite todos los demás elementos de la dimensión Dim. </p> <p>Ejemplo: Sessions[ Page&lt;&gt;"A" ] es el número de sesiones que visitaron una página distinta de A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admite el elemento de la dimensión Dim con el valor ordinal dado. </p> <p>Ejemplo: Sessions[ Month=#0 ] es el número de sesiones del primer mes del conjunto de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>¡Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Admite todos los demás elementos de la dimensión Dim. </p> <p>Ejemplo: Sessions[ Session_Value &lt;&gt; #0 ] es el número de sesiones que tienen un valor de sesión distinto de cero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La atenuación coincide con "Expr" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim que coinciden con la expresión regular dada. La atenuación no debe ser una dimensión denormalizada o contable. </p> <p>Ejemplo: Sessions[ URI coincide con ".*/producto/.*" ] es el número de sesiones que visitaron cualquier página en un directorio de productos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim no coincide con "Expr" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim que no coinciden con la expresión regular dada. La atenuación no debe ser una dimensión denormalizada o contable. </p> <p>Ejemplo: Sessions[ URI no coincide con ".*\.jsp" ] es el número de sesiones que visitaron cualquier página que no fuera una página JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales inferiores al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sesiones[ Mes &lt; "Jul ‘04" ] es el número de Sesiones que tuvieron lugar antes de julio de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Value" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales buenos que el valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sesiones[ Mes &gt; "Jul ‘04" ] es el número de Sesiones que se celebraron después de julio de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales inferiores o iguales al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sessions[ Session_Number &lt;= "2" ] es el número de sesiones que fueron la primera o la segunda sesión de un visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Value" </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales buenos o iguales al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sessions[ Session_Number &gt;= "5" ] es el número de sesiones que fueron la quinta o buena sesión de un visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cualquier Dim </p> </td> 
   <td colname="col2"> <p>Admite todos los elementos de la dimensión Dim. </p> <p>Ejemplo: Sessions[ any Page_View ] es el número de sesiones con al menos una vista de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no Dim </p> </td> 
   <td colname="col2"> <p>Admite elementos que cualquier atenuación rechaza. </p> <p>Ejemplo: Sesiones[ sin vista de página ] es el número de sesiones sin vista de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>Igual que FILTER; se utiliza para agrupar una parte de una expresión de filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>
