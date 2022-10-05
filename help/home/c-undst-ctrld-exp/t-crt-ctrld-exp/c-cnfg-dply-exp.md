---
description: Después de definir el objetivo, la hipótesis y los detalles del experimento, así como de crear el contenido de la prueba, debe configurar el sensor para implementar el experimento controlado.
solution: Analytics
title: Configuración e implementación del experimento
uuid: 460d3ea4-a6c8-4ac4-9a3f-eab71f65b096
exl-id: 957c2ea2-72a5-4bb2-af1d-65187613c26d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 1%

---

# Configuración e implementación del experimento{#configuring-and-deploying-the-experiment}

{{eol}}

Después de definir el objetivo, la hipótesis y los detalles del experimento, así como de crear el contenido de la prueba, debe configurar el sensor para implementar el experimento controlado.

## Configuración del archivo de configuración del experimento {#section-037fe7dea9c94aee9cdc354dafdb7c03}

Para configurar el experimento, debe completar la hoja de cálculo de configuración del experimento proporcionada por Adobe (denominada [!DNL TestExperiment.xls] de forma predeterminada). Este archivo configura [!DNL Sensor] para realizar el experimento y es la versión de Excel del archivo de texto especificado en [Modificación del parámetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

Este archivo puede contener información sobre varios experimentos, que pueden ejecutarse al mismo tiempo o en diferentes momentos y utilizar diferentes grupos y porcentajes, pero estos experimentos no están correlacionados de ninguna manera.

Los usuarios se colocan en un grupo para cada experimento enumerado en el archivo configurado para ejecutarse en este momento.

>[!NOTE]
>
>Cada experimento es independiente de todos los demás experimentos. Los cambios que realice en un experimento no afectan a ningún otro experimento y, aunque los visitantes puedan estar en varios experimentos, los resultados no se relacionan entre sí. Si cree que existe una correlación entre los cambios en varios experimentos, debe crear un nuevo experimento que pruebe estos cambios juntos.

**Para configurar el experimento**

Debe completar este archivo antes de que comience el experimento y no modificar la información mientras se ejecuta el experimento.

>[!NOTE]
>
>Cualquier experimento no es válido de inmediato si la definición del experimento cambia después de iniciarse.

1. Si tiene acceso de administrador a sus servidores web o de aplicaciones, vaya a la [!DNL Sensor] carpeta de instalación en cualquier [!DNL Sensor] equipo en el clúster web para acceder a [!DNL TestExperiment.xls] archivo. Si no tiene acceso de administrador, póngase en contacto con el administrador de cuentas de Adobe para solicitar la [!DNL TestExperiment.xls] archivo.

1. Abra el [!DNL TestExperiment.xls] (puede cambiar el nombre de este archivo si lo desea) y completar los campos siguientes:

<table id="table_FDD6AE631C614F97AD7AE8829E53CCAC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Experimento </td> 
   <td colname="col2"> <p>Un nombre descriptivo para el experimento. Cada nombre de experimento debe ser único y no puede contener espacios. </p> <p>Los nombres de experimento se utilizan al mostrar los resultados de los experimentos en <span class="keyword"> Insight </span>. Los nombres aparecen como la primera mitad de los nombres de elementos en la dimensión del experimento controlado. La segunda mitad del nombre del elemento es el nombre del grupo del campo Grupo de este archivo. Cada grupo recibe un nombre en el siguiente formato con el nombre del experimento seguido del nombre del grupo: </p> <p><i>Nombre del grupo del experimento</i> </p> <p>Por ejemplo: <span class="filepath"> New_Homepage.Control </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Inicio </td> 
   <td colname="col2"> <p>La fecha y la hora en que desea que comience el experimento. Si no introduce valores, el experimento comienza inmediatamente después de implementar el archivo. </p> <p>Formato: MM/DD/AAAA H:MM </p> 
    <ul id="ul_FB8B50C688584683AC2226FCBED40AF9"> 
     <li id="li_223EF962CFC64454965444E66284F670">Si deja los tiempos de inicio y parada vacíos, el experimento se ejecuta indefinidamente. </li> 
     <li id="li_0544C9A98635418CAECD85B67F345772">Puede predefinir los tiempos de inicio y de parada con mucha antelación; por lo tanto, puede configurar todos los experimentos del año siguiente a la vez si lo desea. </li> 
     <li id="li_BDFBB74B1D134E57B37DC5C3457AA1A9">Los tiempos de inicio y detención se basan en la hora del sistema del servidor web. Si ese reloj cambia por cualquier razón, su experimento puede iniciarse o detenerse inesperadamente. </li> 
     <li id="li_3295FE5B2AC64B6CA90CC7F31B808EB9">Si desea añadir un experimento como entrada de archivo de configuración pero no desea que el experimento se ejecute en un futuro próximo, puede comentar la información del experimento utilizando el signo de número "#" o definir los tiempos de inicio y parada en el pasado. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stop </td> 
   <td colname="col2"> <p>La fecha y la hora a las que desea que finalice el experimento. Cuando se produce la fecha y la hora de parada, <span class="wintitle"> Sensor </span> dejará de enviar los valores de cookies identificados como un grupo de prueba a los URI de prueba y enviará todas las cookies a los URI del grupo de control. </p> <p>Formato: MM/DD/AAAA H:MM </p> <p>Consulte las notas para la <span class="wintitle"> Inicio </span> campo . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Grupo </td> 
   <td colname="col2"> <p>Un nombre descriptivo para cada grupo de visitantes en el experimento. Los nombres de grupo no pueden contener espacios. </p> <p>Los nombres de grupo se utilizan al mostrar los resultados de los experimentos en <span class="keyword"> Insight </span>. Para obtener más información, consulte la descripción del campo Experimento . </p> <p>Un grupo de control se puede definir implícita o explícitamente en función del valor introducido en el campo Percentage . </p> <p> <p>Nota: Para satisfacer la cantidad de visitantes necesaria durante el período de tiempo definido para que el experimento sea estadísticamente válido, es posible que tenga que reducir el nivel de confianza o aumentar el período de tiempo. Por ejemplo, si el intervalo de tiempo es de cinco días, el nivel de confianza es del 98 % y el número de visitantes necesarios supera el número esperado para ese período de tiempo, debe aumentar el período de tiempo o disminuir el nivel de confianza hasta que el número de visitantes esperado supere el número necesario para ejecutar un experimento estadísticamente válido. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porcentaje </td> 
   <td colname="col2"> <p>El porcentaje de visitantes del sitio web que se incluirá en cada grupo definido. Estos valores se pueden expresar como porcentajes o como valores decimales. Además, ambos valores deben ser buenos o inferiores a uno. </p> <p>Por ejemplo: </p> <p>33,3% y 66,7% </p> <p>.99 y .01 </p> <p>Si la suma de todos los grupos es inferior a 100, el exceso no definido se establece de forma predeterminada en un grupo de control. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL original </td> 
   <td colname="col2"> <p>El URI del contenido que se va a reasignar, seguido de $. Este valor distingue entre mayúsculas y minúsculas. </p> <p>Formato: index.asp$ </p> <p>Los URI originales se pueden especificar utilizando un signo de dólar ($) al final del URI para indicar que se requiere una coincidencia exacta del nombre del archivo. Por ejemplo, la expresión <span class="filepath"> /product/product_view.asp$ </span> coincide únicamente con esa página exacta, mientras que <span class="filepath"> /product </span> coincide con cualquier página de <span class="filepath"> /product </span> y se puede usar para reasignar todo el subárbol. El experimento ignora las entradas de URL originales que no especifican el carácter $ al final del nombre del archivo a menos que el parámetro ExpPartialMatch se haya establecido en "on". Para obtener más información sobre este parámetro, consulte <a href="../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expplmth-prm.md#concept-9c817c4c49b74287b0f70d6a1a37655e"> Modificación del parámetro ExpPartialMatch (opcional) </a>. </p> <p>La funcionalidad del experimento controlado ignora cualquier cadena de consulta anexada al tronco de URI. Por ejemplo, la página </p> <p> <span class="filepath"> /product/product_view.asp?productid=53982 </span> no es un URI válido, pero la página <span class="filepath"> /product/product_view.asp </span> es un URI válido. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URL reasignada </td> 
   <td colname="col2"> <p>El URI del contenido alternativo. </p> <p>Formato: index2.asp </p> <p>Consulte las notas del campo URL original . </p> </td> 
  </tr> 
 </tbody> 
</table>

A continuación se muestra un ejemplo de una [!DNL TextExperiment.xls] hoja de cálculo:

![](assets/TestExperimentSpreadsheet.png)

>[!NOTE]
>
>No modifique las posiciones de columna en la hoja de cálculo.

Este ejemplo indica que el experimento &quot;New_Homepage&quot; comienza el 1 de junio de 2006, finaliza el 30 de junio de 2006 y contiene un grupo de control con el 50 % de los visitantes y un grupo de prueba con el 50 % de los visitantes, que ven contenido diferente para un URI.

>[!NOTE]
>
>Aunque el archivo de muestra anterior tiene un grupo de control explícito definido, no es necesario definir explícitamente un grupo de control; el experimento crea automáticamente el grupo de control. Si la suma de los porcentajes para todos los grupos en un experimento es inferior al 100 %, se asigna un grupo de control implícito a los usuarios que no pertenecen a uno de los grupos explícitos.

1. Para insertar comentarios y proporcionar información adicional sobre experimentos específicos, empiece la celda con un signo de número (#) y siga sus comentarios. Los comentarios se pueden insertar en cualquier parte del archivo.
1. Después de completar las variables en la hoja de cálculo de configuración del experimento, guarde los cambios y guarde el archivo en formato de texto delimitado por tabuladores ( [!DNL *.txt]) utilizando el nombre especificado en el parámetro ExpFile de la variable [!DNL Sensor] archivo de configuración. Consulte [Modificación del parámetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

   A continuación se muestra un ejemplo de un archivo de texto de configuración de experimento:

   ![](assets/testexperiment.png)

   >[!NOTE]
   >
   >Debido a las pestañas requeridas en este archivo, no edite el archivo de texto de configuración del experimento a mano. Si necesita realizar cambios en el archivo, realice los cambios en la configuración del archivo de Excel y vuelva a guardar el archivo como archivo de texto delimitado por tabuladores.

Si ha definido los tiempos de inicio y parada, no hay razón para eliminar un experimento del archivo de configuración del experimento. Mantener todos los experimentos enumerados en el archivo de configuración del experimento es en realidad una buena manera de mantener un registro de cómo definió cada uno de sus experimentos.

## Implementación del archivo de configuración y del contenido de prueba {#section-34ff29649f584b93bc6129b75084b37c}

Debe implementar el archivo de configuración del experimento en cada equipo del clúster web que ejecute un [!DNL Sensor] y servir las páginas involucradas en el experimento. Puede hacerlo mediante un procedimiento manual o mediante el sistema de administración de contenido existente.

**Para implementar el contenido de prueba**

* En cada aplicación o servidor web que ejecute un [!DNL Sensor] que sirve páginas involucradas en el experimento, utilice el proceso de publicación existente para implementar el contenido de prueba en la ubicación adecuada.

   Por ejemplo, si desea publicar la página del grupo de prueba [!DNL index2.asp] a la carpeta de prueba del sitio web ( [!DNL mysite.com]), publicaría el archivo en [!DNL www.mysite.com/test].

   >[!NOTE]
   >
   >No vincule a ninguno de los archivos de prueba directamente desde una página del sitio web. Al hacerlo, se invalidan los resultados de la prueba y las puntuaciones del índice.

**Para implementar el experimento**

* En cada aplicación o servidor web que ejecute un [!DNL Sensor] que sirve páginas involucradas en el experimento, coloque el archivo de texto de configuración del experimento en el directorio especificado en el parámetro ExpFile en la variable [!DNL Sensor] archivo de configuración. Consulte [Modificación del parámetro ExpFile](../../../home/c-undst-ctrld-exp/t-en-ctrld-exp/c-mod-expfile-prm.md#concept-25232b386a654870becc789d4f1fcc28).

[!DNL Sensor] selecciona de forma aleatoria a los visitantes del sitio web para cada grupo en función de los porcentajes definidos en el archivo y les proporciona el contenido de grupo de control o prueba según corresponda.
