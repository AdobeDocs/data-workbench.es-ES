---
description: Nuevas funciones introducidas en Área de trabajo de datos 6.0.4, incluidas correcciones de errores y problemas conocidos.
solution: Analytics
title: Notas de la versión de Área de trabajo de datos 6.0
topic: Data workbench
uuid: b348425e-3304-4db7-a280-479a34452bdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Notas de la versión de Área de trabajo de datos 6.0

Nuevas funciones introducidas en Área de trabajo de datos 6.0.4, incluidas correcciones de errores y problemas conocidos.

## Nuevas funciones {#section-1225066ea8f44cf68e42e019d0bca816}

El área de trabajo de datos (Insight 6.0) incluye estas nuevas funciones y visualizaciones para agregar capacidades de informes y herramientas de análisis predictivo.

| Funciones de Área de trabajo de datos | Descripción |
|---|---|
| [Visualización de canales](../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-funnel-visualization.md#concept-79a0854325324bb9a60906cf79ef66da) | La visualización de canal permite definir el flujo de proceso secuencial de los clientes y proporciona visibilidad de las visitas en el orden previsto de los visitantes en cada paso del proceso. |
| [Clúster de visitantes](../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d) | La agrupación en clústeres permite aprovechar las características del cliente para categorizar de forma dinámica a los visitantes y generar conjuntos de clústeres basados en entradas de datos seleccionadas para el análisis y la determinación de objetivos del cliente. |
| [Análisis de correlación](../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-analysis.md#concept-a7c8766b40be43aaa4084612689b630c) | El análisis de correlación permite identificar rápidamente las relaciones de datos relevantes para ampliar y mejorar el análisis. |
| [Distribución de DeviceAtlas actualizada](../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-6-0-to-6-1-upgrade/c-deviceatlas-update.md#concept-28b7bd5c0d854e73834261c431bed1e0) | El archivo JSON de DeviceAtlas ahora se distribuirá en un archivo .bundle (un archivo .tar.gz renombrado) junto con DeviceAtlas.dll y DeviceAtlas64.dll. |

## Requisitos de actualización del cliente {#section-f316103b48374b6eac77e8feb5c47ecf}

Complete estas tareas de actualización para las funciones del cliente del área de trabajo de datos (Insight 6.0):

**Actualización del archivo .zbin para el cliente**

El área de trabajo de datos ahora admite un Editor de métodos de entrada (IME) como proceso de entrada de texto secundario que permite introducir caracteres internacionales desde el teclado mediante un cuadro de texto flotante. El área de trabajo de datos admitirá el inglés de forma predeterminada, pero también le permite cargar otros archivos para admitir idiomas internacionales, como un teclado chino virtual (Pinyin IME).

La aplicación cliente requiere un nuevo archivo de diccionario (un archivo .zbin) antes de actualizar a la versión 6.0. Puede obtener el archivo .zbin necesario del perfil Software y Docs (Softdocs).

Requisitos previos:

* Antes de realizar la actualización al cliente de Insight 6.0 y al servidor de informes 6.0, el administrador de Insight debe actualizar primero a Insight Server 6.0.
* El administrador de Insight tendrá que elegir un archivo zbin basado en el idioma (en-us.zbin, zh-cn.zbin), copiar el archivo de idioma, luego cambiarle el nombre a insight.zbin y colocar el archivo renombrado en el directorio raíz del servidor de informes donde se encuentra el archivo ejecutable. A continuación, reinicie el servidor de informes de Insight.

Consulte los requisitos [de actualización del](../../../home/c-release-notes-insight/release-notes.md) servidor para obtener información adicional sobre la actualización del lado del servidor.

**Para actualizar el archivo zbin para el cliente (de la versión 5.x a la 6.0)**

1. Para asegurarse de que el cliente no se actualiza desde Insight Server durante esta actualización, establezca el argumento Insight.cfg en false.

   ```
   Update Software = bool: false
   ```

1. Reinicie el cliente de Insight.
1. Vaya al perfil Software y Docs (perfil SoftDocs) y descargue el **[!UICONTROL Insight.zbin]** archivo requerido: [!DNL Software\Insight Client\v6.00\Insight_6.00.zip]

1. Copie el archivo Insight.zbin en la misma carpeta que el archivo Insight.exe.
1. Para asegurarse de que el cliente de Insight se actualiza ahora desde el servidor de Insight, cambie el argumento de archivo Insight.cfg a true:

   ```
   Update Software = bool: true
   ```

1. Reinicie el cliente.

   Su cliente se sincronizará con el servidor y verá un mensaje que indica que su cliente se está descargando. Al finalizar la descarga, recibirá un mensaje preguntándole si desea reiniciar su cliente de Insight.
1. Haga clic en **Aceptar** para reiniciar el cliente.

   El cliente comenzará y actualizará a la versión 6.0.

1. Reinicie el cliente de nuevo para que la sincronización del cliente Insight.zbin tenga efecto.

   Si recibe el siguiente mensaje, significa que el zbin no se colocó en la ubicación de carpeta correcta junto al archivo Insight.exe.

   ```
   Insight Terminated: The backup dictionary file insight.zbin 
   is missing.
   ```

   Para corregir el problema, elimine Insight.exe, cambie la versión más reciente de Insight.exe.old por Insight.exe y vuelva a comenzar con el paso 1 anterior.

## Requisitos de actualización del servidor {#section-d6edba8b36234957ba8d06b555667a5a}

Complete estas tareas de actualización para las funciones del servidor de Insight 6.0:

**Actualice todos los paquetes** de Insight Server 6.0. Insight 6.0 incluye paquetes de servidor que deben actualizarse, incluido el nuevo perfil de Predictive Analytics.

>[!IMPORTANT]
>
>Se recomienda que los usuarios actualicen los clústeres de servidores con instalaciones nuevas de Insight Server 6.0 al actualizar.

También se recomienda que el cliente actualice los clústeres de servidores con la nueva instalación de Insight Server 6.0.

## Clúster del servidor de actualización

**Prepare el archivo de idioma (archivo .zbin).** El administrador de Insight selecciona el `<language>.zbin` archivo para el idioma requerido (por ejemplo: en-us.zbin , zh-cn.zbin) ubicado en la `/localization/<language>.zbin` carpeta. A continuación, el administrador copia el archivo de idioma y lo cambia a &quot;insight.zbin&quot;.

Después de preparar el archivo de idioma (.zbin), es necesario actualizar tanto el cliente de Insight como el servidor de informes. El cliente de Insight se actualiza durante el proceso [de actualización del](../../../home/c-release-notes-insight/release-notes.md)cliente, pero en la mayoría de los casos el administrador de Insight actualizará el servidor de informes.

**Actualizar el servidor de informes con un archivo de idioma (archivo .zbin)**.

Para todos los idiomas, el servidor de informes 6.0 requiere que el archivo &quot;insight.zbin&quot; se copie en la carpeta raíz del servidor de informes.

Actualice los archivos de idioma del servidor de informes:

1. Agregue el archivo renombrado &quot;insight.zbin&quot; al directorio raíz de ReportServer.
1. El archivo de configuración del servidor de informes (reportserver.cfg) requiere la configuración de fuentes para los idiomas de doble byte. Por ejemplo, el chino requiere la adición de fuentes mediante SimSun:

   ```
   Report Server.cfg - Add Fonts 
   
   Fonts = vector: 2 items 
     0 = string: SimSun 
     1 = string: Arial
   ```

1. Se debe pasar un parámetro para Report Server 6.0 en la línea de comandos para la localización, por ejemplo:

   ```
   ReportServer.exe -Locale -zh-cn 
   ReportServer.exe -Locale -en-us
   ```

   >[!NOTE]
   >
   >Si no se especifica una configuración regional, el servidor de informes elige de forma predeterminada el idioma seleccionado en el archivo insight.zbin.

   Siga los pasos para iniciar ReportServer como un servicio con los parámetros de configuración regional:

   1. Inicie un símbolo del sistema como administrador.
   1. Vaya a la carpeta de instalación de ReportServer.
   1. Escriba el siguiente comando para iniciar el servicio:

      * En inglés: [!DNL ReportServer.exe -RegServer -Locale -en-us]
      * Para chino: [!DNL ReportServer.exe -RegServer -Locale -zh-cn]

1. Para verificar si ReportServer se está ejecutando con los parámetros correctos:

   1. Abra el Administrador de servicios de Windows.
   1. Haga clic con el botón secundario [!DNL Adobe Insight Report Server - Properties].
   La ruta de acceso al archivo ejecutable contendrá los parámetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Modificar el archivo de configuración de perfil para Predictive Analytics**. El administrador de Insight deberá modificar el archivo profile.cfg personalizado para incluir el perfil de Predictive Analytics que estará disponible en Insight.

Ejemplo de la entrada profile.cfg:

```
Example ("profile.cfg"): 
Profile = profileInfo:  
  Active = bool: true 
  Directories = vector: 5 items 
    0 = string: Base\\  
    1 = string: Predictive Analytics\\ 
    2 = string: Geography\\ 
    3 = string: Adobe SC\\ 
    4 = string: Custom Profile\\ 
```

**Actualice el archivo** PAServer.cfg. Si desea enviar trabajos de clúster de Predictive Analytics a los servidores de Insight, deberá configurar el archivo PAServer.cfg para gestionar los envíos de clúster del lado del servidor.

El perfil personalizado debe heredar PAServer.cfg del perfil de Predictive Analytics (Server\Profiles\Predictive Analytics\Dataset). Configure y guarde el archivo PAServer.cfg en el sitio de implementación.

>[!NOTE]
>
>Una vez configurado PAServer.cfg y guardado en un perfil personalizado, se requiere un reinicio de Insight Server en todo el sitio.

**Actualizar el servidor de informes.** Deberá actualizar las fuentes y los parámetros de inicio para el servidor de informes.

Requisitos previos:

* Antes de actualizar el servidor de informes 6.0, el administrador de Insight debe actualizar primero a Insight Server 6.0.
* Para todos los idiomas, el servidor de informes 6.0 requiere la adición de Insight.zbin a la carpeta raíz del servidor de informes. Asegúrese de que `base/localization/<language>.zbin` se copie y se cambie el nombre a &quot;insight.zbin&quot;. Cópielo en la raíz del directorio del servidor de informes.

Actualice los parámetros de fuentes e inicio:

1. El servidor de informes requiere la configuración de fuente para byte doble a fin de generar datos en distintos idiomas,

   por ejemplo:

   Servidor de informes.cfg - Agregar fuentes

   ```
   Fonts = vector: 2 items 
   0 = string: SimSun 
   1 = string: Arial
   ```

1. El parámetro para el servidor de informes 6.0 debe pasarse en la línea de comandos para la localización.

   Para iniciar el servidor de informes como un servicio con los parámetros de configuración regional:

   1. Detenga el servicio del servidor de informes.
   1. Inicie un símbolo del sistema como administrador.
   1. Vaya a la carpeta de instalación del servidor de informes.
   1. Escriba el siguiente comando para iniciar el servicio:

      ```
      ReportServer.exe -RegServer -Locale -en-us
      ```

Para verificar si el servidor de informes se está ejecutando con los parámetros correctos:

1. Abrir el Administrador de servicios de Windows
1. Haga clic con el botón secundario [!DNL Adobe Insight Report Server - Properties].
1. La ruta de acceso al archivo ejecutable contendrá los parámetros:

   ```
   ReportServer.exe -Service ReportServer -Locale -en-us
   ```

**Actualice la fuente de datos de SiteCatalyst para Insight 6.0**. El formato de nombre de archivo de la fuente de datos de SiteCatalyst para Insight 6.0 ha cambiado.

Formato de nombre de archivo actual:

```
 RSID_YYYYMMDD_HH0000.tsv.gz
```

Nuevo formato de nombre de archivo:

```
YYYYMMDD-RSID_HH0000.tsv.gz
```

>[!NOTE]
>
>Este cambio no afecta a los usuarios implementados actualmente con la versión *wbench/ecom* de la fuente de datos de SiteCatalyst.

El cambio en el formato del nombre de archivo permitirá el uso completo de las declaraciones de hora de inicio y finalización de Insight durante el procesamiento del registro. Esto permite que el proceso evalúe si se debe leer el contenido del archivo, en lugar de filtrar todos los archivos de origen mediante una búsqueda fila por fila.

En la mayoría de los casos, se implementó un proceso de cambio de nombre al recibir el archivo para proporcionar el uso completo de esta capacidad. Esta modificación proporciona la convención de nombre requerida de forma predeterminada sin necesidad ni sobrecarga de un proceso secundario.

Para utilizar la nueva fuente de datos de SiteCatalyst:

1. Determine cómo el proceso de recepción gestionará el nuevo formato de nombre de archivo.

   Las secuencias de comandos estándar de cambio y cambio de nombre implementadas durante la implementación mueven los archivos con la extensión &quot;.gz&quot; y solo realizan un cambio de nombre si el nombre de archivo coincide con el formato de nombre de archivo con el RSID anterior.

   El nuevo formato de nombre de archivo:

   ```
    YYYYMMDD-RSID_HH0000.tsv.gz
   ```

1. Evalúe las rutas de origen de registro definidas para confirmar que se leerán todos los archivos.

   Si ya tiene implementada una secuencia de comandos de cambio de nombre, ya está definiendo los orígenes de registro para leer este nuevo formato de nombre de archivo.

## Correcciones {#section-203f917dd6224114a1f801309c4c2cee}

* Ahora, la combinación de teclas para dejar un espacio de trabajo sin guardar los cambios se ha actualizado a **[!UICONTROL `<Ctrl>`+`<Backspace>`]**. Anteriormente, se anulaban los cambios y se cerraba un espacio de trabajo pulsando`<Ctrl>`+`<Delete>`.

## Data Workbench 6.0.4 Release Notes{#data-workbench-release-notes}

Nuevas funciones introducidas en Área de trabajo de datos 6.0.4, incluidas correcciones de errores y problemas conocidos.

Para ver las funciones y correcciones anteriores basadas en cada versión anterior, consulte los archivos [de notas de](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html)revisión.

## Nuevas funciones {#section-2-1225066ea8f44cf68e42e019d0bca816}

Área de trabajo de datos 6.0.4 incluye estas nuevas funciones y visualizaciones para agregar capacidades de informes y herramientas de análisis predictivo.

**Visualización** de Puntuación de tendencia. El área de trabajo de datos calcula las puntuaciones de cada visitante como una probabilidad estimada de que se produzca un evento específico. La visualización Puntuación del visitante permite crear una dimensión de puntuación que proporciona una probabilidad de un evento específico para cada visitante de interés según las variables de entrada.

![](assets/visitor_scoring_visual.png)

Consulte Puntuación [de tendencia](../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-visitor-propensity.md#concept-2958f4640dd44b9d86ad51c4f6165f40) para obtener información adicional sobre esta función.

## Requisitos de actualización {#section-08bd6fe3da8740fcb19688e8cac6f223}

**Se debe definir** la ID de la fuente de registro. A partir de la versión 6.04, si no se define el ID de origen de registro, obtendrá el siguiente error:

```
Missing Log Souce ID in log processing.cfg. Log Source ID must be  
defined for all log sources.
```

El registro de filas por origen de registro se agregó en Área de trabajo de datos 6.0 y se puede definir en el perfil personalizado Log Processing.cfg agregando un identificador de origen de registro con un nombre único. Si tiene un ID de origen de registro en blanco, podría ver problemas de procesamiento de registro como la lectura incompleta de los datos de origen de registro y otras discrepancias.

```
Log Processing.cfg 
Log Sources = vector: 2 items 
  0 = VisualSensor: 
    Compressed = bool: false 
    Log Paths = vector: 1 items 
      0 = Path: \some path\ 
    Log Server = serverInfo:  
      Address = string:  
      Name = string:  
      Port = int: 80 
      Proxy Address = string:  
      Proxy Password = string:  
      Proxy Port = int: 8080 
      Proxy User Name = string:  
      SSL Client Certificate = string: Certificates\\server_cert.pem 
      SSL Server Common Name = string:  
      Use SSL = bool: false 
     
Log Source ID = string: <Name your ID Here>
    Name = string:  
    Recursive = bool: false
```

**Capacidad para delegar recursos de FSU**

En [!DNL Profiles/`<profilename>`/dataset/Cluster.cfg], ahora puede especificar unidades de servidor de archivos (FSU) independientes para los servidores Normalizar y Lista de fuentes. Estos servicios ya no están ligados al FSU maestro.

>[!NOTE]
>
>Si no se especifica el servidor de lista, éste heredará la configuración del servidor de normalización.

Example in the [!DNL cluster.cfg] file.

```
Cluster = ClusterConfig: 
  Normalize Server = serverInfo: 
    Address = string: normalizeserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false 
  List Server = serverInfo: 
    Address = string: sourcelistserver.domain.com 
    Port = int: 80 
    Use SSL = bool: false
```

## Problemas corregidos {#section-3b4b85a35f534288adf8a5246ef028cc}

* En Área de trabajo de datos 6.0, la matriz de correlación y el generador de clústeres no admitían Calcular en segundo plano. Esto se ha corregido en la versión 6.0.4.
* Anteriormente, si tenía una selección en el canal y eliminaba un paso, podría producirse una infracción de acceso. Esto se ha resuelto.
* Se corrigió una condición de bloqueo potencial en la exportación de segmentos que podría causar problemas en condiciones de carga pesada.
