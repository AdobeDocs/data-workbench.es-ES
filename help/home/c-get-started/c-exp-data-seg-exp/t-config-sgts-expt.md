---
description: Puede crear un segmento de los elementos de cualquier dimensión contable y, a continuación, generar datos para ese segmento por lotes o en tiempo real en un archivo delimitado por tabuladores.
title: Configurar segmentos para exportar
uuid: 651be834-ee41-4487-8c5a-30d94580f6a0
exl-id: 4f53e02c-3f00-44b3-9f6d-a2f23903b3fa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 6%

---

# Configurar segmentos para exportar{#configure-segments-for-export}

{{eol}}

Puede crear un segmento de los elementos de cualquier dimensión contable y, a continuación, generar datos para ese segmento por lotes o en tiempo real en un archivo delimitado por tabuladores.

Cada vez que se exporta un segmento, se generan datos de métricas o dimensiones para todos los elementos de dimensión incluidos en ese segmento. Puede controlar el formato de los datos generados para que otros sistemas puedan cargarlos fácilmente.

>[!NOTE]
>
>No es posible exportar dimensiones de informes, ya que utilizan un [!DNL report time.metric] para referencia. Como solución alternativa, si coloca un código no modificable [!DNL report time.metric] en el perfil, la exportación de segmentos puede utilizarlo como punto de referencia para las dimensiones de informes. Sin embargo, la variable [!DNL report time.metric] no se actualiza automáticamente en función del valor Con el tiempo del perfil, por lo que, si desea cambiar la referencia de la dimensión de informes, debe cambiar el código [!DNL report time.metric] archivo.

Para configurar un segmento para la exportación, debe abrir y editar un [!DNL .export] archivo.

1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Export]** en el [!DNL File] para mostrar su contenido.

       Si el directorio Export no existe, créelo de la siguiente manera:
   
   1. Vaya al directorio de instalación de la Data Workbench.
   1. Abra el directorio del perfil con el que está trabajando.
   1. Dentro del directorio Perfil, cree un nuevo directorio llamado &quot;Exportar&quot;.

1. En el [!DNL Profile Manager], haga clic con el botón derecho en la celda vacía de la variable [!DNL User] para el directorio Export , haga clic en **[!UICONTROL Create]** > **[!UICONTROL New Segment Export]**.

   Un archivo llamado [!DNL New Segment Export.export] aparece en la variable [!DNL File] para Exportar.

1. Cambie el nombre del nuevo archivo haciendo clic con el botón derecho en la [!DNL User] para el archivo y escriba el nuevo nombre en el parámetro File .
1. Abra el nuevo archivo haciendo clic con el botón derecho en el [!DNL User] para el archivo y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   La ventana de configuración de la variable [!DNL .export] aparece.

1. Haga clic en **[!UICONTROL Query]** y, a continuación, modifique los campos de la variable [!DNL .export] tal como se describe en la tabla siguiente:

<table id="table_C2EC8FCD3FA04DE78D2CADFA3F7FD8E3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Para este parámetro... </th> 
   <th colname="col2" class="entry"> Proporcione esta información... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Comando </td> 
   <td colname="col2"> <p>Opcional. Un programa que se ejecutará después de crear el archivo de salida. Este campo debe hacer referencia a un ejecutable (una <span class="filepath"> .exe </span> ), no un comando shell. </p> <p>Nota: La exportación del segmento fallará si hay un espacio en el parámetro de comando . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtro </td> 
   <td colname="col2"> <p>Opcional. Un filtro con nombre o una expresión de filtro. Puede crear un filtro con nombre mediante un editor de filtros y, a continuación, escribir el nombre de ese filtro aquí o puede escribir una expresión de filtro en sí. </p> <p>Para obtener más información sobre los editores de filtros, consulte <a href="../../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3"> Editores de filtros </a>. Para obtener más información sobre la sintaxis de expresión de filtro, consulte <a href="../../../home/c-get-started/c-qry-lang-syntx/c-syntx-fltr-exp.md#concept-72f2563f809747a2a3cff7ec72462a15"> Sintaxis para expresiones de filtro </a>. </p> <p>Se exportan los elementos de nivel que coinciden con el filtro, mientras que los demás elementos no. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nivel </td> 
   <td colname="col2"> <p>Dimensión contable cuyos elementos se van a exportar. </p> <p>Ejemplo: Un nivel de visitante exporta una fila de datos para cada visitante. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Archivo de salida </td> 
   <td colname="col2"> <p>Ruta y nombre de archivo de los datos exportados. Si el perfil se está ejecutando en un clúster de servidores de Data Workbench, cada servidor de Data Workbench escribe un archivo de salida que contiene una parte de los datos. </p> <p>El directorio de instalación del servidor de Data Workbench contiene un directorio de Exportaciones donde puede guardar el archivo de salida. Por ejemplo, puede introducir <span class="filepath"> Exportaciones\Segmento de visitante.txt </span>, donde <span class="filepath"> Visitor Segment.txt </span> es el nombre del archivo que contiene los datos exportados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Formato de salida </td> 
   <td colname="col2"> La métrica o los datos de dimensión que se exportarán para cada elemento Nivel. Si el resultado es un archivo delimitado por tabuladores, los campos deben separarse con caracteres de tabulación y el formato debe terminar con los caracteres de nueva línea adecuados. Para obtener más información, consulte <a href="../../../home/c-get-started/c-exp-data-seg-exp/c-abt-otpt-frmt.md#concept-ac7e24d1374a4b418365db7cc98c361e"> Acerca del formato de salida </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de finalización del programa </td> 
   <td colname="col2"> <p>Opcional. La fecha y hora de finalización de la programación, incluida la zona horaria. </p> <p>Formato: AAAA-MM-DD hh:mm zona horaria </p> <p>Ejemplo: 2013-08-01 12:01 EDT </p> <p>Las exportaciones programadas se detienen en este momento; sin embargo, el archivo de salida se vuelve a generar cada vez que se cambia su definición. Este campo no tiene sentido sin definir Programar cada. Para obtener más información sobre la configuración de la zona horaria, consulte la <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Programar cada </td> 
   <td colname="col2"> Opcional. Frecuencia con la que se regenera el archivo de salida. Los valores admitidos son hora, día, semana y mes. El archivo de salida se vuelve a generar cada vez que se cambia su definición. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Hora de inicio del programa </td> 
   <td colname="col2"> <p>Opcional. La fecha y hora de inicio de la programación, incluida la zona horaria. </p> <p>Formato: AAAA-MM-DD hh:mm zona horaria </p> <p>Ejemplo: 2013-08-01 12:01 EDT </p> <p>Las exportaciones programadas comienzan en este momento y la programación es relativa a esta hora. Este campo carece de sentido sin definir <span class="wintitle"> Programar cada </span>. Para obtener más información sobre la configuración de la zona horaria, consulte la <i>Guía de configuración de conjuntos de datos</i>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Límite de tiempo (s) </td> 
   <td colname="col2"> Opcional. El tiempo máximo permitido para que transcurra mientras se genera una exportación de segmento. Si se supera el intervalo especificado, la exportación se inicia de nuevo. Si establece este valor en 0 (cero), se elimina el límite. El valor predeterminado es 600 segundos. </td> 
  </tr> 
 </tbody> 
</table>

1. Clic con el botón derecho **[!UICONTROL (New)]** en la parte superior de la ventana, haga clic en **[!UICONTROL Save]**.
1. Para que este archivo esté disponible para todos los usuarios del perfil de trabajo, haga clic con el botón derecho en la marca de verificación de la [!DNL .export] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

   >[!NOTE]
   >
   >Guardar el [!DNL .export] al servidor de Data Workbench hace que la exportación se ejecute una vez inmediatamente, incluso si la hora de inicio del programa está establecida en una fecha y hora futuras.

   El siguiente es un ejemplo [!DNL .export] archivo.

   ![](assets/vis_Segment_Export_File.png)

   >[!NOTE]
   >
   >La variable [!DNL Visitor Segment.export] El archivo mostrado en el ejemplo hace referencia al filtro Segmento de visitante . Modificar la definición de este filtro cambia la definición de la exportación.
