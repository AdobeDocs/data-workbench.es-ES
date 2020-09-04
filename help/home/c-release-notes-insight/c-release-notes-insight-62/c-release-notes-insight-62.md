---
description: Las notas de la versión de Data Workbench 6.2 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.
title: Notas de la versión Data Workbench 6.2
uuid: 8631c936-d53b-493d-9f58-72f541c3ddce
translation-type: tm+mt
source-git-commit: 8f5c69541bdd97aefbad3840f75f06846615f222
workflow-type: tm+mt
source-wordcount: '1250'
ht-degree: 5%

---


# Notas de la versión Data Workbench 6.2{#data-workbench-release-notes}

Las notas de la versión de Data Workbench 6.2 incluyen nuevas funciones, requisitos de actualización, correcciones de errores y problemas conocidos.

## Nuevas funciones {#section-1225066ea8f44cf68e42e019d0bca816}

La Data Workbench 6.2 incluye estas nuevas funciones:

| Funciones | Descripción |
|--- |--- |
| Árboles de decisión | Los árboles de decisiones son una visualización de análisis predictivo utilizada para evaluar las características y relaciones de los visitantes. El Generador de árboles de decisiones genera una visualización de árboles de decisiones en función de un caso positivo especificado y un grupo de entradas. |
| Actualizar al filtro binario en la matriz de correlación | El filtro binario se ha actualizado con nuevas funciones, lo que requiere que vuelva a crear cualquier matriz de correlación con un filtro binario creado en versiones anteriores. |
| Mapa de densidad | El mapa de densidad es una visualización que muestra elementos como rectángulos sombreados dentro de un mapa cuadrado. |
| Perfil de atribución | Para analizar rápidamente los valores de atribución (eventos para atribuir responsabilidad por una conversión o venta exitosa), Data Workbench proporciona un perfil de atribución basado en reglas con funciones para que el Arquitecto configure los informes de atribución y el Analista para ejecutar los informes. |
| Informes analíticos | Las plantillas de informes estandarizan los informes de Adobe Analytics para los usuarios del área de trabajo de datos que utilizan el perfil de Adobe SC. Estos informes son idénticos a los informes empleados en Informes y análisis de marketing (anteriormente SiteCatalyst). |
| Diagrama de puntos 3D | Un diagrama de puntos 3D grafica los elementos de una dimensión de datos (como Días o Sitio de referencia) en una cuadrícula tridimensional donde los ejes x, y y z representan varias métricas. |


## Actualizaciones de la interfaz de usuario del cliente de Data Workbench{#data-workbench-client-ui-updates}

La Data Workbench 6.2 incluye nuevas actualizaciones de la interfaz de usuario en el panel Marcadores, nuevos iconos en la barra de herramientas del espacio de trabajo, la capacidad de arrastrar el espacio de trabajo dentro de una pantalla, nuevas teclas rápidas y actualizaciones de la visualización del gráfico circular.

## Nuevas funciones de marcador {#section-e361b605441540ca8213c3fddb5e0718}

Ahora puede marcar espacios de trabajo significativos para moverse rápidamente entre visualizaciones e informes empleados en el flujo de trabajo.

**Uso de marcadores**

1. Marque un espacio de trabajo haciendo clic en el icono Marcador ![](assets/bookmark_icon.png) en la esquina superior derecha de la barra de herramientas.
1. Haga clic **[!UICONTROL Add]** > **[!UICONTROL Bookmarks Panel]** en el panel izquierdo para abrir una lista de marcadores.

   ![](assets/bookmarks_panel.png)

1. Para abrir un espacio de trabajo con marcador, haga clic en el nombre de un espacio de trabajo en la **[!UICONTROL Bookmark Panel]**.

   ![](assets/bookmarks_panel_left.png)

   Se abrirá el espacio de trabajo seleccionado. Al hacer clic en otro espacio de trabajo con marcador, se cerrará el espacio de trabajo anterior y se abrirá el área de trabajo recién seleccionada, lo que le permitirá navegar rápidamente por el flujo de trabajo.

**Para eliminar un marcador:**

* En el panel Marcador, haga clic con el botón derecho y seleccione **Eliminar`<bookmark title>`** para eliminar un marcador seleccionado o seleccione **[!UICONTROL Clear All Bookmarks]** eliminar todos los marcadores.

* También puede hacer clic con el botón derecho en el espacio de trabajo de la vista en miniatura dentro de la superficie de trabajo y seleccionar **[!UICONTROL Clear Bookmark]**.

>[!IMPORTANT]
>
>* Se pueden guardar 25 marcadores.
>* Si agrega un marcador y luego mueve la ubicación del área de trabajo, el marcador no será válido y debe eliminarse del panel Marcador y restablecerse.

>



## Nuevos iconos en Workspace {#section-c108bbd1661249e79c146727ff3d2470}

Data Workbench 6.2 ahora reemplaza el texto del espacio de trabajo con iconos. Aún puede pasar el ratón por encima y ver el mensaje de información del objeto que identifica el icono, incluidos **[!UICONTROL File]**, **[!UICONTROL Add]** y **[!UICONTROL Export]**.

![](assets/new_icons.png)

Se agrega un nuevo **[!UICONTROL Help]** icono para acceder a la documentación y a otros centros de conocimiento, incluidos los siguientes vínculos:

<table id="table_64BBC67B1BB44B1197FF7E5E7B067696"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Vínculos de documentación </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Reports &amp; Analytics de marketing  </td> 
   <td colname="col2">Abra la página de ayuda de Informes y análisis <span class="uicontrol"></span> de marketing de Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intercambio de ideas </td> 
   <td colname="col2">Abra el inicio de sesión <span class="uicontrol"> de Idea Exchange</span>. Este portal en línea permite a los usuarios proporcionar cambios de actualización e ideas de mejora al área de trabajo de datos. Estas ideas orientadas al cliente pueden ser votadas por todos los usuarios. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ayuda </td> 
   <td colname="col2">Abra la documentación <span class="uicontrol"> de la Data Workbench</span>. <p>También puede pulsar <span class="uicontrol"> &lt;F1&gt;</span> para abrir la ayuda dentro de un espacio de trabajo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Acerca de </td> 
   <td colname="col2">Abra para identificar la versión <span class="uicontrol"> cliente del área de trabajo de datos</span> . </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>También puede pulsar `<F1>` para abrir la documentación desde un espacio de trabajo.

## Arrastrar Vistas del espacio de trabajo {#section-9129c340c21d45a3864c923884cd4382}

Si un espacio de trabajo es más grande que la pantalla visible, puede mover la vista para ver todos los elementos dentro del espacio de trabajo. Puede hacer clic en el fondo (fuera de las visualizaciones y tablas) y arrastrar la pantalla para mover el área visible dentro del espacio de trabajo. El cursor cambiará a un icono de mano al arrastrar la vista dentro del marco del espacio de trabajo.

![](assets/drag_workspace.png)

## Teclas rápidas para cambiar las Vistas del espacio de trabajo {#section-d8322f72423f437aa2e34f2188b1341c}

Las nuevas teclas rápidas le permiten cambiar el tamaño y volver a configurar las áreas de trabajo entre las vistas de ventana y página completa.

<table id="table_A01C514C99F043338D183A6839E03DEA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Comandos </th> 
   <th colname="col2" class="entry"> Teclas rápidas </th> 
   <th colname="col3" class="entry"> Comandos de menú combinados </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Vista</b>a pantalla completa. Workspace rellena la pantalla y cambia al nuevo tamaño. </td> 
   <td colname="col2"><b>Ctrl más</b> <p>Ctrl + (en el teclado numérico) </p> <p><i>O bien</i> </p> <p>Ctrl Mayús + (en el teclado) </p> </td> 
   <td colname="col3"> 
    <ul id="ul_C7C731B894D946D9916F50806F015857"> 
     <li id="li_452B4C119B1A40038A408CFFC53653A9">Archivo &gt; Tamaño de página &gt; Pantalla de relleno <p><i>seguido por</i> </p> </li> 
     <li id="li_DE9B8B31B9F24A6AA68A1D0DB886B501">Archivo &gt; Reajustar espacio de trabajo </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Vista</b>de ventana. Workspace se muestra en una vista de ventana estándar y se ajusta al nuevo tamaño. </td> 
   <td colname="col2"><b>Ctrl menos</b> <p>Ctrl - </p> </td> 
   <td colname="col3"> 
    <ul id="ul_3474B9EFD69343C09BC84E485D896C28"> 
     <li id="li_820BAED76FF24A5785E6D89C5C692DD5">Archivo &gt; Tamaño de página &gt; Estándar <p><i>seguido por</i> </p> </li> 
     <li id="li_337789F282CE4C2C990C67B115782454">Archivo &gt; Reajustar espacio de trabajo </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Correcciones de errores {#section-8704a9ac358246cd81233dd0982d534f}

* Se ha actualizado el archivo de búsqueda de sitio visual para abordar los cambios del motor de búsqueda en el término de búsqueda de consulta.
* Se corrigió el mensaje de error inexacto &quot;Error al importar espacio de trabajo&quot; al importar un espacio de trabajo en la estación de trabajo cliente aunque la importación se haya realizado correctamente.
* El error de conexión de estación de trabajo que muestra el mensaje &quot;Conflicto de configuración 412&quot; ahora se reemplaza por un mensaje práctico que identifica la acción del sistema.
* El comando &quot;post&quot; ahora se puede ejecutar en el Servidor de informes.
* Se han corregido errores de interfaz de usuario en la interfaz de usuario del cliente para chino simplificado.
* Adobe Analytics ha actualizado la fuente de datos que alimenta la Data Workbench para aprovechar los Perfiles y Audiencias que se integran con Adobe Experience Cloud. Todos los usuarios de la Data Workbench debían preparar su entorno para esta transición para el 21 de abril de 2014.

   Se han introducido perfiles y Audiencias para proporcionar una vista completa de los clientes en todo Adobe Analytics. Este nuevo servicio está disponible en Adobe Experience Cloud para aumentar el valor entre las herramientas de análisis a fin de crear inicios sobre la base de estas funciones en Analytics. El nuevo identificador de visitante de Experience Cloud se agregará a la fuente de datos, junto con otras mejoras y mejoras para adaptarse a la nueva fuente de datos y al identificador de visitante global.
* Al importar un espacio de trabajo, se muestra un mensaje de error aunque la importación se haya realizado correctamente.

## Requisitos de actualización {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* El perfil de atribución está configurado para que los usuarios que han implementado el perfil de Adobe SC empleen la fuente de datos de Analytics (SC/Insight). De forma predeterminada, los eventos de marketing y conversión se emplean como interacciones predeterminadas evaluadas en los modelos basados en reglas.
* Para los usuarios del perfil Adobe SC que actualicen a la Data Workbench 6.2, si no utiliza las configuraciones predeterminadas, compruebe que el [!DNL x-bot_id] valor del [!DNL SC Fields.cfg] archivo se está descodificando correctamente y que el [!DNL x-bot_id] campo aparece correctamente en los archivos [!DNL Decoding Instructions.cfg] y [!DNL Exclude Hit.cfg] . Esto sólo será un problema si ha modificado el archivo de configuración desde la configuración predeterminada.

* Si ha eliminado los campos no utilizados en el archivo **[!UICONTROL Dataset]** > **[!UICONTROL Log Processing]** > **[!DNL SC Fields.cfg]** para el perfil de Adobe SC, deberá actualizar para dar cabida a los valores de campo actualizados utilizados para el perfil de atribución.

## Problemas conocidos {#section-dbb307639835493a83409f5f461932b8}

* Cuando la visualización de diagrama de puntos 3D incluye llamadas, el zoom puede mostrar trazos fuera del borde de la visualización.

   Solución: Haga zoom en el diagrama de puntos 3D primero y, a continuación, agregue las llamadas a la visualización.
* Si arrastra la métrica del panel Buscadores a Leyenda de métricas fuera de la columna de métricas, se eliminará la Leyenda de métricas del área de trabajo.

   Solución: Los usuarios que deseen arrastrar métricas a la Leyenda de métricas deben soltar en la primera columna (columna de métricas).
* Imprimir espacio de trabajo con barra lateral y ambas opciones no incluirán la información de copyright en la página impresa.
* El uso de Workstation en la sesión de escritorio remoto se bloqueará al cambiar el nombre de los espacios de trabajo.
* (En la versión en chino simplificado) Las salidas de informes reales son válidas en el servidor de informes, pero las líneas de asunto de correo electrónico y los nombres de archivo adjuntos son confusos.
* (En la versión en chino simplificado) Cuando se utiliza ajuste de palabras en la visualización de hoja de cálculo, las palabras localizadas no se ajustan correctamente, lo que provoca que se agreguen caracteres no deseados a la cadena.
* (En la versión en chino simplificado) No se puede iniciar Insight.exe si el directorio de instalación tiene un nombre que no sea inglés.

   Solución: Mantenga los nombres predeterminados o cambie el nombre utilizando solo caracteres ingleses en la ruta de la carpeta para iniciar los ejecutables.

