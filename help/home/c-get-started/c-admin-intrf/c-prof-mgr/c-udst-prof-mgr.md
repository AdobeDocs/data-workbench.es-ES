---
description: Los nombres de carpeta y archivo incluidos en la implementación se muestran en la parte izquierda del Administrador de perfiles.
title: Administrador de perfiles
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Administrador de perfiles{#profile-manager}

Los nombres de carpeta y archivo incluidos en la implementación se muestran en la parte izquierda del Administrador de perfiles.

Los perfiles que conforman la aplicación se muestran como columnas individuales en el [!DNL Profile Manager]. Estos perfiles incluyen varios perfiles heredados y un solo perfil de trabajo.

>[!NOTE]
>
>Su perfil de trabajo (un perfil de conjunto de datos o un perfil específico de función) es el perfil que se carga al abrir la Data Workbench.

Las marcas de verificación (y sus colores) indican las carpetas de perfil en el servidor de Data Workbench y los equipos de Data Workbench en los que reside cada archivo, si existen varias copias de un archivo y si esas copias múltiples tienen la misma fecha y hora de modificación. Estos archivos se sincronizan entre el servidor de Data Workbench y los equipos de Data Workbench durante la descarga del perfil.

A continuación se muestra un ejemplo [!DNL Profile Manager] para una implementación HBX:

![](assets/client-prof.png)

Desde el menú [!DNL Profile Manager], puede abrir cualquiera de los otros administradores (por ejemplo, [!DNL Dimensions Manager] o [!DNL Reports Manager]), que solo muestran partes particulares de [!DNL Profile Manager]. También puede crear nuevos administradores de perfil. Consulte [Creación de nuevos administradores de perfil](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Una marca de verificación junto al nombre de un archivo en una columna en particular indica que un archivo con ese nombre reside en la carpeta denominada en esa columna (perfil). Al moverse a la derecha en [!DNL Profile Manager], los archivos tienen prioridad sobre los de la izquierda, es decir, cada perfil heredado se genera a partir de los perfiles de la izquierda en [!DNL Profile Manager]. Por ejemplo, si tiene un archivo con el mismo nombre y en la misma ubicación en el perfil [!DNL Base] (columna) y en el perfil [!DNL User] (columna), se utiliza el archivo en el perfil [!DNL User] en lugar del archivo en el perfil [!DNL Base].

## Buscar perfiles {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Con la Data Workbench 5.5, se ha agregado un campo de búsqueda para encontrar los perfiles necesarios en el [!DNL Profile Manager].

![](assets/client-prof2.png)

Los siguientes tipos de columnas aparecen en el [!DNL Profile Manager]:

* Las columnas *nombre de perfil heredado* contienen marcas de verificación para los archivos que residen en cada carpeta de perfil. Los perfiles heredados incluyen perfiles internos proporcionados por el Adobe, así como cualquier perfil específico de la empresa o de funciones específicas que cree y mantenga. En el ejemplo anterior, los perfiles internos incluyen Base, Tráfico, Valor, Marketing, etc. El perfil interno [!DNL Base], que contiene los componentes básicos y la información de configuración necesaria para ejecutar la aplicación de Adobe, se proporciona con cada implementación. Los demás perfiles internos contienen elementos (espacios de trabajo, métricas, dimensiones derivadas, etc.) relacionados con tipos concretos de información, como tráfico web o marketing. Adobe proporciona únicamente los perfiles adecuados para el tipo de datos que está analizando y para su sector.

   >[!NOTE]
   >
   >De forma predeterminada, los perfiles internos (los proporcionados por el Adobe) no se pueden cambiar. Toda la personalización debe producirse en el conjunto de datos o en los perfiles específicos de funciones u otros perfiles que cree. Si está creando una nueva aplicación y necesita cambiar un perfil interno, debe cambiar el parámetro Modificar perfiles internos en el archivo [!DNL Insight.cfg] . Consulte [Parámetros de configuración de Insight](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) para obtener más información. Antes de hacerlo, póngase en contacto con los servicios de consultoría de Adobe.

* La columna *nombre del perfil de trabajo*, que siempre es la columna siguiente a la última, contiene marcas de verificación para los archivos que residen en la carpeta del perfil de trabajo actual. En el ejemplo anterior, el perfil de trabajo es Dataset. Su perfil de trabajo es un perfil de conjunto de datos o un perfil específico de funciones. Los archivos de esta carpeta tienen prioridad sobre cualquier archivo con los mismos nombres en cualquier carpeta de perfil heredada.
* La columna [!DNL User], que siempre es la última columna, contiene marcas de verificación para los archivos y carpetas que residen como archivos locales en la carpeta User\*profile name*. La estructura de directorio de la carpeta Usuario imita la del perfil de trabajo, y cada carpeta User\*profile name* contiene copias locales de los espacios de trabajo, métricas, dimensiones y archivos de configuración para ese perfil en particular. Estas copias locales tienen prioridad sobre cualquier archivo con los mismos nombres en cualquier carpeta de perfil heredada o de trabajo. Los archivos de la columna [!DNL User] se crearon y guardaron solo en la carpeta User\*profile name*, o residen en un perfil interno o de trabajo, así como en la carpeta User\*profile name*. Los archivos de cada carpeta pueden ser o no idénticos y pueden tener o no la misma fecha y hora de modificación.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Para evitar cambiar el conjunto de datos solo localmente, el servidor de Data Workbench ignora las copias locales del archivo [!DNL profile.cfg] y los archivos de las carpetas Dataset o Export en la carpeta User\*profile name*. Los archivos ignorados se identifican con un fondo rojo en la columna [!DNL User] y una advertencia &quot;Ignored in User directory&quot; en el menú contextual. Para implementar los cambios realizados en las copias locales de estos archivos, debe guardarlos en el perfil de trabajo para que se puedan sincronizar con el servidor de Data Workbench. Para ver los pasos para guardar archivos en su perfil de trabajo, consulte [Publicación de archivos en su perfil de trabajo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
      >    
      >    
   * Un guión (-) en lugar de una marca de verificación de una columna identifica un archivo vacío (de byte cero). La Data Workbench trata los archivos de byte cero como inexistentes, lo que permite utilizarlos para ocultar archivos incluidos en un perfil a la izquierda. Consulte [Ocultar archivos usando archivos vacíos (byte cero)](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Determinar las versiones de los archivos {#section-225d732246b94cbe87acdfa9c881d6af}

Como se mencionó en la sección anterior, las marcas de verificación del [!DNL Profile Manager] están codificadas por colores, de modo que se pueda identificar fácilmente dónde reside un archivo y si las copias múltiples de un archivo se modificaron en diferentes momentos.

Si un archivo o un directorio contraído es exactamente el mismo que el archivo o directorio de la izquierda, tiene la misma marca de verificación de color que el archivo o directorio de esa columna (perfil). Si es diferente de cualquier archivo o directorio a su izquierda, o si el archivo o directorio existe solamente en la columna [!DNL User], la marca de verificación es blanca.

![](assets/vis_ProfMgr_LocalFiles.png)

El [!DNL Profile Manager] mostrado en el ejemplo anterior indica lo siguiente:

* Una marca de verificación blanca para el archivo [!DNL A New Metric.metric] solo aparece en la columna [!DNL User], lo que indica que solo tiene una copia local de ese archivo; no se ha publicado (ni cargado) en el servidor de Data Workbench para que otros usuarios de Data Workbench tengan acceso a él.

* Las marcas de verificación del nombre del archivo [!DNL Average Score.metric] aparecen en las columnas Películas y [!DNL User] . La marca de verificación de la columna [!DNL User] es del mismo color que la marca de verificación de la columna Películas, lo que indica que la copia local del archivo tiene la misma fecha y hora de modificación que el archivo de la carpeta Películas.

* Las marcas de verificación del nombre del archivo [!DNL Average Score Error.metric] aparecen en las columnas Películas y [!DNL User] . La marca de verificación de la columna [!DNL User] es blanca, lo que indica que la copia local del archivo tiene una fecha u hora de modificación diferente a la del archivo de la carpeta Películas.

