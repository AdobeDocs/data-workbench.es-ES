---
description: Los nombres de carpeta y archivo incluidos en la implementación se muestran en la parte izquierda del Administrador de perfiles.
solution: Analytics
title: Administrador de perfiles
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Administrador de perfiles{#profile-manager}

Los nombres de carpeta y archivo incluidos en la implementación se muestran en la parte izquierda del Administrador de perfiles.

Los perfiles que componen la aplicación se muestran como columnas individuales en la [!DNL Profile Manager]. Estos perfiles incluyen varios perfiles heredados y un solo perfil de trabajo.

>[!NOTE]
>
>El perfil de trabajo (ya sea un perfil de conjunto de datos o un perfil específico de función) es el perfil que se carga al abrir Área de trabajo de datos.

Las marcas de verificación (y sus colores) indican las carpetas de perfil en el servidor de Área de trabajo de datos y en los equipos de Área de trabajo de datos en los que reside cada archivo, si existen varias copias de un archivo y si esas copias múltiples tienen la misma fecha y hora de modificación. Estos archivos se sincronizan entre el servidor de Área de trabajo de datos y los equipos de Área de trabajo de datos durante la descarga del perfil.

A continuación se muestra un ejemplo [!DNL Profile Manager] de implementación de HBX:

![](assets/client-prof.png)

Desde el [!DNL Profile Manager] menú, puede abrir cualquiera de los otros administradores (por ejemplo, el [!DNL Dimensions Manager] o [!DNL Reports Manager]), que solo muestran partes particulares de [!DNL Profile Manager]. También puede crear nuevos administradores de perfiles. Consulte [Creación de nuevos administradores](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)de perfiles.

Una marca de verificación junto al nombre de un archivo en una columna en particular indica que un archivo con ese nombre reside en la carpeta con el nombre en esa columna (perfil). A medida que se desplaza a la derecha en la [!DNL Profile Manager], los archivos tienen prioridad sobre los de la izquierda, es decir, cada perfil heredado se genera a partir de los perfiles de la izquierda en la [!DNL Profile Manager]. Por ejemplo, si tiene un archivo con el mismo nombre y en la misma ubicación en el perfil (columna) y en la [!DNL Base] columna (perfil), se utiliza el archivo del [!DNL User] perfil en lugar del archivo del [!DNL User] [!DNL Base] perfil.

## Buscar perfiles {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Con Área de trabajo de datos 5.5, se ha agregado un campo de búsqueda para encontrar los perfiles necesarios en la [!DNL Profile Manager].

![](assets/client-prof2.png)

Los siguientes tipos de columnas aparecen en la [!DNL Profile Manager]:

* Las columnas *heredadas del nombre* del perfil contienen marcas de verificación para los archivos que residen en cada carpeta de perfil. Los perfiles heredados incluyen perfiles internos proporcionados por Adobe, así como cualquier perfil específico de la empresa o función que cree y mantenga. En el ejemplo anterior, los perfiles internos incluyen Base, Tráfico, Valor, Marketing, etc. El [!DNL Base] perfil interno, que contiene los componentes básicos y la información de configuración necesaria para ejecutar la aplicación de Adobe, se proporciona con cada implementación. Los demás perfiles internos contienen elementos (espacios de trabajo, métricas, dimensiones derivadas, etc.) relacionados con determinados tipos de información, como tráfico web o marketing. Adobe proporciona solo los perfiles adecuados para el tipo de datos que está analizando y para su sector.

   >[!NOTE]
   >
   >De forma predeterminada, los perfiles internos (los proporcionados por Adobe) no se pueden cambiar. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree. Si está creando una nueva aplicación y necesita cambiar un perfil interno, debe cambiar el parámetro Modificar perfiles internos en el [!DNL Insight.cfg] archivo. Consulte Parámetros [de configuración de](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) Insight para obtener más información. Antes de hacerlo, póngase en contacto con los servicios de consultoría de Adobe.

* La columna del nombre *del perfil de* trabajo, que siempre es la columna siguiente a la última, contiene marcas de verificación para los archivos que residen en la carpeta del perfil de trabajo actual. En el ejemplo anterior, el perfil de trabajo es Conjunto de datos. Su perfil de trabajo es un perfil de conjunto de datos o un perfil específico de función. Los archivos de esta carpeta tienen prioridad sobre cualquier archivo con los mismos nombres en cualquier carpeta de perfil heredada.
* La [!DNL User] columna, que siempre es la última, contiene marcas de verificación para los archivos y carpetas que residen como archivos locales en la carpeta User\*profile name*. La estructura de directorio de la carpeta Usuario es similar a la del perfil de trabajo y cada carpeta User\*profile name* contiene copias locales de los espacios de trabajo, las métricas, las dimensiones y los archivos de configuración de ese perfil en particular. Estas copias locales tienen prioridad sobre cualquier archivo con los mismos nombres en cualquier carpeta de perfil heredada o de trabajo. Los archivos de la [!DNL User] columna se crearon y guardaron únicamente en la carpeta User\*profile name* o residen en un perfil interno o de trabajo, así como en la carpeta User\*profile name*. Los archivos de cada carpeta pueden ser idénticos o no y pueden tener o no la misma fecha y hora de modificación.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Para evitar cambiar el conjunto de datos solo localmente, el servidor de Área de trabajo de datos omite las copias locales del [!DNL profile.cfg] archivo y los archivos de las carpetas Dataset o Export de la carpeta User\*profile name*. Los archivos omitidos se identifican con un fondo rojo en la [!DNL User] columna y una advertencia &quot;Ignorado en el directorio del usuario&quot; en el menú contextual. Para implementar los cambios realizados en las copias locales de estos archivos, debe guardarlos en el perfil de trabajo para que se puedan sincronizar con el servidor de Área de trabajo de datos. Para ver los pasos para guardar archivos en el perfil de trabajo, consulte [Publicación de archivos en el perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabajo.
      >    
      >    
   * Un guión (-) en lugar de una marca de verificación en una columna identifica un archivo vacío (de byte cero). El Área de trabajo de datos considera que los archivos de byte cero no existen, lo que le permite utilizarlos para ocultar los archivos incluidos en un perfil a la izquierda. Consulte [Ocultar archivos usando archivos](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)vacíos (byte cero).


## Determinar las versiones de los archivos {#section-225d732246b94cbe87acdfa9c881d6af}

Como se mencionó en la sección anterior, las marcas de verificación del [!DNL Profile Manager] archivo tienen un código de color que permite identificar fácilmente dónde reside un archivo y si las copias múltiples de un archivo se modificaron en momentos diferentes.

Si un archivo o un directorio contraído es exactamente el mismo que el archivo o directorio a su izquierda, tiene la misma marca de verificación de color que el archivo o directorio de esa columna (perfil). Si es diferente de cualquier archivo o directorio a su izquierda, o si el archivo o directorio existe solamente en la [!DNL User] columna, la marca de verificación es blanca.

![](assets/vis_ProfMgr_LocalFiles.png)

El ejemplo [!DNL Profile Manager] que se muestra arriba indica lo siguiente:

* Una marca de verificación blanca para el [!DNL A New Metric.metric] archivo aparece solamente en la [!DNL User] columna, lo que indica que sólo tiene una copia local de ese archivo; no se ha publicado (ni cargado) en el servidor de Área de trabajo de datos para que otros usuarios de Área de trabajo de datos tengan acceso a él.

* Las marcas de verificación del nombre del [!DNL Average Score.metric] archivo aparecen en las [!DNL User] columnas Películas y Películas. La marca de verificación de la columna [!DNL User] tiene el mismo color que la marca de verificación de la columna Películas, lo que indica que la copia local del archivo tiene la misma fecha y hora de modificación que el archivo de la carpeta Películas.

* Las marcas de verificación del nombre del [!DNL Average Score Error.metric] archivo aparecen en las [!DNL User] columnas Películas y Películas. La marca de verificación de la [!DNL User] columna es blanca, lo que indica que la copia local del archivo tiene una fecha u hora de modificación diferente a la del archivo de la carpeta Películas.

