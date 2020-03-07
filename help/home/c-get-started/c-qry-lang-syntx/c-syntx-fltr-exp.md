---
description: Un filtro es una expresión que define un subconjunto de los datos de un conjunto de datos.
solution: Analytics
title: Sintaxis para expresiones de filtro
topic: Data workbench
uuid: faeb6847-3295-48ab-9d1c-db00f57647ba
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Sintaxis para expresiones de filtro{#syntax-for-filter-expressions}

Un filtro es una expresión que define un subconjunto de los datos de un conjunto de datos.

Un filtro admite o rechaza cada elemento de cada dimensión según las relaciones entre dimensiones.

Los filtros se pueden editar mediante el [!DNL Filter Editor]. Consulte Editores [de filtros](../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).

En la tabla siguiente, cada descripción de sintaxis incluye un ejemplo de una expresión de métrica que utiliza ese filtro. Por ejemplo,[SessionsTrue] es una métrica definida con el filtro &quot;Verdadero&quot;. La métrica[SessionsTrue] es la misma que la métrica Sessions porque el filtro True admite todos los elementos de la dimensión Session.

<table id="table_5D66E6C11B384460BAAA7A6130214594"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p>True </p> </td> 
   <td colname="col2"> <p>Filtro constante. Admite todos los elementos de cada dimensión </p> <p>Ejemplo: Sessions[ True ] es lo mismo que Sessions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Falso </p> </td> 
   <td colname="col2"> <p>Filtro constante. Rechaza todos los elementos de cada dimensión. </p> <p>Ejemplo: Sessions[ False ] siempre es cero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>no filtrar </p> </td> 
   <td colname="col2"> <p>Admite elementos que el filtro rechaza. </p> <p>Ejemplo: Sesiones[ not Page="A" ] es el número de Sesiones que no visitaron la página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA y FilterB </p> </td> 
   <td colname="col2"> <p>Admite elementos que admiten FilterA y FilterB. </p> <p>Ejemplo: Sesiones[ Página="A" y Página="B" ] es el número de Sesiones que visitaron la página A y la página B. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>FilterA o FilterB </p> </td> 
   <td colname="col2"> <p>Admite elementos que admiten FilterA o FilterB. </p> <p>Ejemplo: Sesiones[ Página="A" o Página="B" ] es el número de Sesiones que visitaron la página A, la página B o ambas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Filtrar por atenuación </p> </td> 
   <td colname="col2"> <p>Admite el conjunto de elementos de la dimensión Dim admitidos por Filter. </p> <p>Ejemplo: Sesiones[ Página="/inicio" por visitante ] es el número de Sesiones que pertenecen a un visitante que vio la página "/inicio". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificador </p> </td> 
   <td colname="col2"> <p>Filtros de referencia definidos de otro modo en el perfil. </p> <p>Ejemplo: Sessions[ Broken_Session_Filter ] es el número de sesiones admitidas por el filtro de sesiones interrumpidas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim = "Valor" </p> </td> 
   <td colname="col2"> <p>Admite el elemento dado de la dimensión Dim. </p> <p>Ejemplo: Sesiones[ Página="A" ] es el número de Sesiones que visitaron la Página A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; "Value" </p> <p>¡Dim!= “Valor” </p> </td> 
   <td colname="col2"> <p>Admite todos los demás elementos de la dimensión Dim. </p> <p>Ejemplo: Sesiones[ Página&lt;&gt;"A" ] es el número de Sesiones que visitaron cualquier página que no sea A. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim = #Ordinal </td> 
   <td colname="col2"> <p>Admite el elemento de la dimensión Dim con el valor ordinal dado. </p> <p>Ejemplo: Sesiones[ Mes=#0 ] es el número de Sesiones en el primer mes del conjunto de datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;&gt; #Ordinal </p> <p>¡Dim!= #Ordinal </p> </td> 
   <td colname="col2"> <p>Admite todos los demás elementos de la dimensión Dim. </p> <p>Ejemplo: Sessions[ Session_Value &lt;&gt; #0 ] es el número de sesiones que tienen un valor de sesión distinto de cero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El atenuador coincide con "Expr" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim que coinciden con la expresión regular dada. La atenuación no debe ser una dimensión denormalizada o contable. </p> <p>Ejemplo: Sessions[ URI coincide con ".*/producto/.*" ] es el número de sesiones que visitaron cualquier página en un directorio de productos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El atenuador no coincide con "Expr" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim que no coinciden con la expresión regular dada. La atenuación no debe ser una dimensión denormalizada o contable. </p> <p>Ejemplo: Sessions[ URI no coincide con ".*\.jsp" ] es el número de sesiones que visitaron cualquier página que no fuera una página JSP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt; "Value" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales inferiores al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sesiones[ Mes &lt; "Jul ‘04" ] es el número de Sesiones que tuvieron lugar antes de julio de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &gt; "Valor" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales buenos que el valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sesiones[ Mes &gt; "Jul ‘04" ] es el número de Sesiones que se celebraron después de julio de 2004. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dim &lt;= "Value" </p> </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales inferiores o iguales al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sessions[ Session_Number &lt;= "2" ] es el número de sesiones que fueron la primera o la segunda sesión de un visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dim &gt;= "Valor" </td> 
   <td colname="col2"> <p>Admite los elementos de la dimensión Dim con valores ordinales buenos o iguales al valor ordinal del elemento "Value". Si "Valor" no es un elemento de dimensión, se supone que es mayor que cualquier elemento actual de la dimensión. </p> <p>Ejemplo: Sessions[ Session_Number &gt;= "5" ] es el número de sesiones que fueron la quinta o buena sesión de un visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>cualquier atenuación </p> </td> 
   <td colname="col2"> <p>Admite todos los elementos de la dimensión Dim. </p> <p>Ejemplo: Sesiones[ cualquier vista_de_página ] es el número de sesiones con al menos una vista de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>sin atenuación </p> </td> 
   <td colname="col2"> <p>Admite elementos que cualquier Dim rechaza. </p> <p>Ejemplo: Sesiones[ sin vista_de_página ] es el número de sesiones sin vista de página. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>(FILTRO) </p> </td> 
   <td colname="col2"> <p>Igual que FILTER; se utiliza para agrupar una parte de una expresión de filtro. </p> </td> 
  </tr> 
 </tbody> 
</table>

