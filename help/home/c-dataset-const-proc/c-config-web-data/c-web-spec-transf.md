---
description: Información sobre la configuración específica de la web que se define en Conjunto de datos de transformación Incluya archivos que se entregan con perfiles de Adobe para el sitio.
solution: Analytics
title: Configuración específica de Web para la transformación
topic: Data workbench
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Configuración específica de Web para la transformación{#web-specific-settings-for-transformation}

Información sobre la configuración específica de la web que se define en Conjunto de datos de transformación Incluya archivos que se entregan con perfiles de Adobe para el sitio.

Las condiciones, dimensiones y parámetros definidos por estas configuraciones se crean durante la fase de transformación de la construcción de conjuntos de datos.

* [Condición de vista de página](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimensión URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimensión Referente](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parámetros de sesión](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condición de vista de página {#section-cc2807a12a88492f8b64a43234a1f835}

La [!DNL Page View Condition] es una operación de condición que determina si una entrada de registro en particular (es decir, una solicitud de página) debe incluirse en los datos recopilados sobre el historial de vistas de página de un visitante. Cuando la entrada de registro satisface el [!DNL Page View Condition], se convierte en un elemento de la dimensión contable Vista de página. Si una entrada de registro no satisface el [!DNL Page View Condition], otras dimensiones siguen teniendo acceso a sus campos de datos. Además de la dimensión Vista de página, los resultados de la [!DNL Page View Condition]:

* **[!DNL URI]y[!DNL Page]:**Estas dimensiones se ven directamente afectadas por el[!DNL Page View Condition]. Si la página dada no pasa la página[!DNL Page View Condition,]no se incluirá en las dimensiones URI o de página.

* **[!DNL Visitor Page Views]y[!DNL Session Page Views]:**Las dimensiones Vistas de página del visitante y Vistas de página de sesión son un recuento del número de páginas vistas por un visitante en una sesión determinada o en una sesión determinada, respectivamente. Las páginas filtradas por el[!DNL Page View Condition]no forman parte de este recuento.

* **Número de sesión:** El [!DNL Page View Condition] tiene un efecto indirecto en la dimensión Número de sesión. La dimensión Número de sesión se crea antes de la [!DNL Page View Condition]; por lo tanto, al considerar [!DNL Session Number] en relación con el [!DNL Page Views], es posible tener sesiones sin vistas de página.

La implementación predeterminada de [!DNL Site] incluye un [!DNL Transformation Dataset Include] archivo en el que se definen la dimensión contable Vista de página y los elementos relacionados [!DNL Page View Condition] .

Para obtener información sobre las dimensiones contables, consulte Dimensiones [extendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar la configuración de la condición de vista de página**

1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\Page View.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], es posible que el archivo en el que existen estas opciones de configuración difiera de la ubicación descrita.

1. Revise o edite los valores de los parámetros del [!DNL Page View Condition] parámetro según sea necesario. Utilice el siguiente ejemplo como guía. En este archivo, el [!DNL Page View Condition] se define mediante una [!DNL Copy] transformación. Tenga en cuenta que este archivo también contiene la definición de la dimensión contable Vista de página.

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Para obtener información sobre las dimensiones contables, consulte Dimensiones [extendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Para obtener información sobre la [!DNL Copy] transformación, consulte Transformaciones [de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Guarde el archivo haciendo clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Dimensión URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Si está trabajando con [!DNL Site], debe definir la dimensión URI cuyos elementos son los orígenes URI de las páginas del sitio web vistas. La implementación predeterminada incluye un [!DNL Transformation Dataset Include] archivo en el que se define la dimensión simple de URI.

Para obtener información sobre dimensiones simples, consulte Dimensiones [extendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar la configuración de la dimensión URI**

1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\URI.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], es posible que el archivo en el que existen estas opciones de configuración difiera de la ubicación descrita.

1. Revise o edite los valores de los parámetros del archivo como desee. Utilice el siguiente ejemplo e información como guías.

![](assets/cfg_WebParameters_URI.png)

Las opciones de configuración de la dimensión URI incluyen los dos parámetros siguientes:

* **Distinción entre mayúsculas y minúsculas:** True o false. Si el valor es true, se tiene en cuenta el uso de mayúsculas y minúsculas en la identificación de páginas únicas. El valor predeterminado es true.
* **Elementos máximos:** El número máximo de elementos (es decir, URI) para la dimensión URI. El valor predeterminado es 32768.

   >[!NOTE]
   >
   >Cambiar este valor puede causar problemas graves de rendimiento. No cambie este valor sin consultar con Adobe.

* Guarde el [!DNL URI.cfg] archivo haciendo clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.

* Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Dimensión Referente {#section-8a97ec34d18b4814b5f95495ac4f8638}

Si está trabajando con [!DNL Site], debe definir la dimensión Referente cuyos elementos constan de los dominios de segundo nivel de los referentes de las primeras entradas de registro en todas las sesiones. La implementación predeterminada incluye un [!DNL Transformation Dataset Include] archivo en el que se define la dimensión simple Referente.

Para obtener información sobre dimensiones simples, consulte Dimensiones [extendidas](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar la configuración de la dimensión Referente**

1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\Referrer.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], es posible que el archivo en el que existen estas opciones de configuración difiera de la ubicación descrita.

1. Revise o edite los valores de los parámetros del archivo como desee. Utilice el siguiente ejemplo e información como guías.

   ![](assets/cfg_WebParameters_Referrer.png)

   La configuración de la dimensión Referente incluye el parámetro Elementos máximos, que especifica el número máximo de elementos (es decir, referentes) para la dimensión Referente. El valor predeterminado es 32768.

   >[!NOTE]
   >
   >En el ejemplo anterior, el parámetro [!DNL Maximum Elements] se establece en 0. Cuando este parámetro se establece en 0, el servidor del área de trabajo de datos utiliza su valor predeterminado interno 32768.

1. Guarde el [!DNL Referrer.cfg] archivo haciendo clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y, a continuación, haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Parámetros de sesión {#section-0a209b0c504041a5801f7f71a963c8b1}

Si está trabajando con [!DNL Site], puede especificar parámetros que definan los límites de la sesión de un visitante en un sitio web. Estos parámetros solo son válidos cuando se definen en un [!DNL Transformation Dataset Include] archivo de la [!DNL Site] implementación.

Los siguientes parámetros son únicos en cuanto a que pueden ser miembros del [!DNL Transformation Dataset Include] vector del archivo, o bien pueden aparecer como parámetros individuales en el [!DNL Parameters] [!DNL Transformation.cfg]archivo. Un parámetro se puede definir exactamente una vez, por lo que estos parámetros se definen en el [!DNL Transformation.cfg]archivo o en el [!DNL Parameters] vector del archivo de inclusión del conjunto de datos, no en ambos archivos.
**Duración máxima de sesión y tiempo de espera de sesión**

Duración máxima de sesión y Tiempo de espera de sesión son parámetros de cadena que definen la duración de la sesión de un visitante. Estos parámetros funcionan con el parámetro Dominios internos para determinar la duración de la sesión.

Duración máxima de sesión especifica la duración más larga de la sesión antes de que se inicie una nueva sesión. Esto evita que las páginas web con contenido automático se actualicen a partir de la creación de sesiones que son arbitrariamente largas. Si el referente de un clic se establece en una de las entradas del parámetro Dominios internos, este tiempo de espera se utiliza para definir el final de una sesión. Ninguna sesión puede ser mayor que la duración máxima de sesión especificada, independientemente de cuántos clics contenga. El valor recomendado es de 48 horas.

Tiempo de espera de sesión especifica la cantidad de tiempo que debe transcurrir entre las entradas de registro de un visitante determinado para determinar el final de una sesión y el inicio de una nueva (es decir, el tiempo de espera habitual utilizado para definir una sesión de usuario). El valor recomendado de este parámetro es de 30 minutos. Si el referente de un clic no está establecido en uno de los referentes del parámetro Dominios internos, este tiempo de espera se utiliza para definir la sesión. Si cs(dominio-referente) para una entrada de registro está en la lista de dominios internos, la duración máxima de sesión determina si la entrada de registro actual es parte de una sesión existente o el inicio de una nueva sesión.

Considere una situación en la que se llama a un visitante fuera de su equipo durante un período de tiempo superior al tiempo de espera de sesión mientras está explorando el sitio. A su regreso, sigue explorando donde se fue. Dado que el visitante nunca abandona el sitio ni cierra su explorador, el cs(dominio-referente) de su siguiente clic es el mismo que el dominio interno y su sesión original permanece activa mientras no se alcance la configuración de duración máxima de sesión. Si el dominio del sitio aparece como un dominio interno y no se alcanza el tiempo de espera máximo, la interacción del visitante aparece como una sola sesión y no como dos sesiones independientes. Sin embargo, si el visitante regresa a su equipo y el siguiente clic tiene un referente externo (o en blanco), se iniciará una nueva sesión.

>[!NOTE]
>
>La [!DNL Sessionize] transformación [!DNL Timeout Condition] también influye en la determinación de la duración de la sesión de un visitante. Si el tiempo de espera de sesión y la duración máxima de sesión no se aplican, [!DNL Timeout Condition] se comprueba para determinar si una entrada de registro debe considerarse el inicio de una nueva sesión. For more information, see [Data Transformations](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Para editar los parámetros de duración máxima de sesión y tiempo de espera de sesión**

Si está trabajando con [!DNL Site], es probable que la implementación predeterminada incluya un [!DNL Transformation Dataset Include] archivo en el que se especifiquen los nombres y los valores recomendados de estos parámetros.

1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y vaya a [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que se definen estos parámetros puede diferir de la ubicación descrita.

1. Edite los valores de los parámetros como desee. Asegúrese de especificar las unidades deseadas (minutos, horas, etc.).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Guarde el [!DNL Session Parameters.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haciendo clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, donde nombre del perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

**[!DNL Internal Domains]**

[!DNL Internal Domains] es un parámetro vectorial que enumera los hosts de nivel de dominio (referentes internos) que deben tratarse como parte de un sitio web en particular. Estos hosts se eliminan de la dimensión del referente (que es una lista de la información del referente externo). Cuando cs(referrer-domain) coincide con cualquiera de las cadenas enumeradas en el conjunto de dominios internos, se ignora el tiempo de espera de sesión y se utiliza la duración máxima de sesión para determinar la duración de la sesión.

El parámetro Dominios internos también se puede utilizar para evitar el inicio de una nueva sesión cuando los visitantes se mueven entre los múltiples dominios de una empresa asociados de una manera que supera el tiempo de espera de sesión. Por ejemplo: considere una empresa que tiene partes del sitio divididas en dos dominios: uno se registra ( [!DNL xyz.com]) y el otro no se registra ( [!DNL xyz-unlogged.com]). Si estos sitios están integrados de manera que faciliten el movimiento sin fisuras del tráfico en los dos dominios, no es deseable generar una sesión diferente cada vez que el visitante se mueve de [!DNL xyz-unlogged.com] un dominio al [!DNL xyz.com] dominio. La lista [!DNL xyz-unlogged.com] como dominio interno evita que las sesiones se dividan en varias sesiones como resultado del tráfico en estos dos dominios siempre y cuando no se alcance la configuración de duración máxima de sesión.

**Para agregar un dominio interno**

Si está trabajando con [!DNL Site], la implementación predeterminada incluye un [!DNL Transformation Dataset Include] archivo para definir el parámetro Dominios internos. En este archivo, el parámetro se denomina; sólo debe introducir los dominios internos que desea incluir y guardar el archivo actualizado.

1. Abra el [!DNL Profile Manager] perfil del conjunto de datos y vaya a [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que se define el parámetro Dominios internos puede diferir de la ubicación descrita.

1. Haga clic con el botón derecho **[!UICONTROL Value]** para el parámetro vectorial Dominios internos y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Edite los valores como desee.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Guarde el [!DNL Internal Domains.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haciendo clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente surtan efecto, en la columna [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación del archivo en la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

