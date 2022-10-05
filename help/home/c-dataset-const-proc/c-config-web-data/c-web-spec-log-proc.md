---
description: Información sobre la configuración específica de la web que se definen en los archivos de inclusión de conjunto de datos de procesamiento de registros que se entregan con perfiles de Adobe para el sitio.
title: Configuración web específica para el procesamiento de registros
uuid: dea861a6-3f78-4cb9-8108-ecf397b37667
exl-id: abb6e6a7-011f-40d6-b778-16da2332af72
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '857'
ht-degree: 1%

---

# Configuración web específica para el procesamiento de registros{#web-specific-settings-for-log-processing}

{{eol}}

Información sobre la configuración específica de la web que se definen en los archivos de inclusión de conjunto de datos de procesamiento de registros que se entregan con perfiles de Adobe para el sitio.

El filtrado definido por esta configuración se produce después de que las entradas de registro abandonen los descodificadores y se aplican las transformaciones, pero antes de que la evaluación [!DNL Log Entry Condition].

* [Filtrado de estado HTTP](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-ac66acdcb6aa467d81c3721199e540fd)
* [Filtrado de robots](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-log-proc.md#section-7f43681dfbc64b969619cb88f97d5ad5)

## Filtrado de estado HTTP {#section-ac66acdcb6aa467d81c3721199e540fd}

Puede configurar la implementación de [!DNL Site] para eliminar las entradas de registro con códigos de estado sc de 400 o superior del conjunto de datos. Las solicitudes correctas tienen códigos de estado inferiores a 400. Su implementación predeterminada incluye un [!DNL Log Processing Dataset Include] archivo en el que está configurado el filtrado de estado HTTP.

**Para editar los ajustes de configuración del filtrado de estado HTTP**

1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos y abra el [!DNL Dataset\Log Processing\Traffic\HTTP Status Filter.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que existen estas opciones de configuración puede diferir de la ubicación descrita.

1. Revise o edite los valores de los parámetros del archivo como desee. Utilice el siguiente ejemplo como guía.

   ![](assets/cfg_WebParameters_HTTPStatusFilter.png)

   Para obtener información sobre la variable [!DNL Range] condición, consulte [Condiciones](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md).

1. Guarde el [!DNL HTTP Status Filter.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Filtrado de robots {#section-7f43681dfbc64b969619cb88f97d5ad5}

Puede configurar la implementación de [!DNL Site] para usar archivos de búsqueda y eliminar de su conjunto de datos las entradas de registro generadas por robots conocidos, scripts de prueba y direcciones IP para usuarios internos. Su implementación predeterminada incluye un [!DNL Log Processing Dataset Include] archivo en el que está configurado el filtrado de robots.

**Para editar los ajustes de configuración del filtrado de robots**

1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos y abra el [!DNL Dataset\Log Processing\Traffic\Robot Filter.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que existen estas opciones de configuración puede diferir de la ubicación descrita.

1. Revise o edite los parámetros del archivo utilizando el siguiente ejemplo e información como guías:

   ![](assets/cfg_WebParameters_RobotFilter.png)

   El archivo incluye un [!DNL NotRobotCondition] que se define mediante los tres parámetros siguientes:

   * **Filtrado de robots sin distinción de mayúsculas y minúsculas:** Verdadero o falso. Si es true, las mayúsculas y minúsculas (superior/inferior) no se tienen en cuenta en el filtrado de robots.
   * **Archivo de búsqueda de robots, línea de base:** Ruta y nombre de archivo del archivo de texto que contiene una lista de agentes de usuario del explorador que son robots conocidos y que se van a filtrar fuera del conjunto de datos. Adobe proporciona el archivo de búsqueda de robots de línea base. Si no especifica una ruta, el servidor de Data Workbench busca este archivo en el directorio Búsquedas del directorio de instalación del servidor de Data Workbench.
   * **Archivo de búsqueda de robots, ampliado:** Ruta y nombre de archivo de un archivo de texto opcional que contiene una lista de agentes de usuario del explorador o direcciones IP que definen robots específicos de su implementación. Esta lista puede incluir robots de monitorización internos, scripts de prueba y direcciones IP para usuarios internos que deben filtrarse fuera del conjunto de datos. Si no especifica una ruta, el servidor de Data Workbench busca este archivo en el directorio Búsquedas del directorio de instalación del servidor de Data Workbench.

   Si el agente de usuario del explorador de una entrada de registro no aparece en ninguno de los archivos de búsqueda, la entrada de registro se considera generada por un visitante real y no se filtra desde el conjunto de datos.

   >[!NOTE]
   >
   >La coincidencia en los archivos de búsqueda de robots utiliza subcadenas para compararlas con los campos de registro c-ip y cs(user-agent) . Si la cadena de búsqueda comienza por &quot;$&quot;, debe coincidir con la parte frontal de la cadena que se está probando y si termina por &quot;$&quot;, la cadena de búsqueda debe coincidir con el final de la cadena que se está probando. Si la cadena de búsqueda comienza con y termina con &quot;$&quot;, las cadenas deben coincidir exactamente para que la entrada de registro se filtre. Por ejemplo, para probar todas las direcciones IP de un bloque de clase C, debe utilizar una cadena como $231.78.123. para forzar una coincidencia al principio de la cadena. Esto coincidiría con las direcciones 231.78.123.0 a 231.78.123.255.

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

   >[!NOTE]
   >
   >Si es fundamental que las entradas de registro subyacentes utilizadas para construir un conjunto de datos no cambien (aunque cambien las transformaciones utilizadas para construir y actualizar el conjunto de datos y sus dimensiones), el archivo de búsqueda de robots, la línea de base y el archivo de búsqueda de robots, ampliado, deben estar controlados por la versión. Colocar un número de versión en estos archivos garantiza que las actualizaciones de los archivos de búsqueda de robots predeterminados no cambien de forma involuntaria los conjuntos de datos de informes creados anteriormente mediante la adición o eliminación de entradas en estos archivos.
