---
description: Información sobre la configuración específica de la web que se definen en Conjuntos de datos de transformación Incluir archivos que se entregan con perfiles de Adobe para el sitio.
title: Configuración específica de web para la transformación
uuid: 282f0f4d-43d7-41cf-bae8-5cac6b4d81a0
exl-id: 737f5e7a-7ab3-4ff7-8d92-7ccd87c28743
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2035'
ht-degree: 1%

---

# Configuración específica de web para la transformación{#web-specific-settings-for-transformation}

{{eol}}

Información sobre la configuración específica de la web que se definen en Conjuntos de datos de transformación Incluir archivos que se entregan con perfiles de Adobe para el sitio.

Las condiciones, dimensiones y parámetros definidos por esta configuración se crean durante la fase de transformación de la construcción del conjunto de datos.

* [Condición de vista de página](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-cc2807a12a88492f8b64a43234a1f835)
* [Dimension URI](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-348f7e9099d049d197a7cdcbc8a6c234)
* [Dimension del referente](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-8a97ec34d18b4814b5f95495ac4f8638)
* [Parámetros de sesión](../../../home/c-dataset-const-proc/c-config-web-data/c-web-spec-transf.md#section-0a209b0c504041a5801f7f71a963c8b1)

## Condición de vista de página {#section-cc2807a12a88492f8b64a43234a1f835}

La variable [!DNL Page View Condition] es una operación de condición que determina si una entrada de registro determinada (es decir, una solicitud de página) debe incluirse en los datos recopilados sobre el historial de vistas de página de un visitante. Cuando la entrada de registro cumple la función [!DNL Page View Condition], se convierte en un elemento de la dimensión contable Vista de página . Si una entrada de registro no cumple la función [!DNL Page View Condition], otras dimensiones siguen pudiendo acceder a sus campos de datos. Además de la dimensión Vista de página , los resultados del [!DNL Page View Condition]:

* **[!DNL URI]y [!DNL Page]:** Estas dimensiones se ven directamente afectadas por el [!DNL Page View Condition]. Si la página dada no pasa la variable [!DNL Page View Condition,] no se incluye en las dimensiones URI o de página.

* **[!DNL Visitor Page Views]y [!DNL Session Page Views]:** Las dimensiones Vistas de página del visitante y Vistas de página de sesión son un recuento del número de páginas que un visitante ve en una sesión determinada o en una sesión determinada, respectivamente. Las páginas filtradas por la variable [!DNL Page View Condition] no forman parte de este recuento.

* **Número de sesión:** La variable [!DNL Page View Condition] tiene un efecto indirecto en la dimensión Número de sesión . La dimensión Número de sesión se crea antes de que [!DNL Page View Condition]; por lo tanto, al considerar [!DNL Session Number] en relación con el [!DNL Page Views], es posible tener sesiones sin vistas de página.

Su implementación predeterminada de [!DNL Site] incluye un [!DNL Transformation Dataset Include] archivo en el que la dimensión contable Vista de página y el elemento relacionado [!DNL Page View Condition] están definidas.

Para obtener información sobre dimensiones contables, consulte [Dimension extendidos](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar los ajustes de configuración de la condición de vista de página**

1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\Page View.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que existen estas opciones de configuración puede diferir de la ubicación descrita.

1. Revise o edite los valores de los parámetros de la variable [!DNL Page View Condition] según sea necesario. Utilice el siguiente ejemplo como guía. En este archivo, la variable [!DNL Page View Condition] se define mediante una [!DNL Copy] transformación. Tenga en cuenta que este archivo también contiene la definición de la dimensión contable Vista de página .

   ![](assets/cfg_WebParameters_PageView.png)

   >[!NOTE]
   >
   >Para obtener información sobre dimensiones contables, consulte [Dimension extendidos](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md). Para obtener información sobre la variable [!DNL Copy] transformación, consulte [Transformaciones de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

1. Guarde el archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana, haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Dimension URI {#section-348f7e9099d049d197a7cdcbc8a6c234}

Si está trabajando con [!DNL Site], debe definir la dimensión URI cuyos elementos son los raíces URI de las páginas del sitio web visitadas. Su implementación predeterminada incluye un [!DNL Transformation Dataset Include] archivo en el que se define la dimensión simple URI.

Para obtener información sobre dimensiones simples, consulte [Dimension extendidos](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar los ajustes de configuración de la dimensión URI**

1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\URI.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que existen estas opciones de configuración puede diferir de la ubicación descrita.

1. Revise o edite los valores de los parámetros del archivo como desee. Utilice el siguiente ejemplo e información como guías.

![](assets/cfg_WebParameters_URI.png)

Los ajustes de configuración de la dimensión URI incluyen los dos parámetros siguientes:

* **Distinción entre mayúsculas y minúsculas:** Verdadero o falso. Si es verdadero, se tiene en cuenta el caso de la letra (superior/inferior) al identificar páginas únicas. El valor predeterminado es true.
* **Máximo de elementos:** El número máximo de elementos (es decir, URI) para la dimensión URI. El valor predeterminado es 32768.

   >[!NOTE]
   >
   >Cambiar este valor puede causar problemas graves de rendimiento. No cambie este valor sin consultar el Adobe.

* Guarde el [!DNL URI.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana, haga clic en **[!UICONTROL Save]**.

* Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Dimension del referente {#section-8a97ec34d18b4814b5f95495ac4f8638}

Si está trabajando con [!DNL Site], debe definir la dimensión Remitente del reenvío cuyos elementos consten de los dominios de segundo nivel de los referentes de las primeras entradas de registro en todas las sesiones. Su implementación predeterminada incluye un [!DNL Transformation Dataset Include] archivo en el que se define la dimensión simple Remitente del reenvío.

Para obtener información sobre dimensiones simples, consulte [Dimension extendidos](../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md).

**Para editar los ajustes de configuración de la dimensión Referente**

1. Abra el [!DNL Profile Manager] dentro del perfil del conjunto de datos y abra el [!DNL Dataset\Transformation\Traffic\Referrer.cfg] archivo.

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que existen estas opciones de configuración puede diferir de la ubicación descrita.

1. Revise o edite los valores de los parámetros del archivo como desee. Utilice el siguiente ejemplo e información como guías.

   ![](assets/cfg_WebParameters_Referrer.png)

   Los ajustes de configuración de la dimensión Referente incluyen el parámetro Maximum Elements , que especifica el número máximo de elementos (es decir, referentes) para la dimensión Referente. El valor predeterminado es 32768.

   >[!NOTE]
   >
   >En el ejemplo anterior, la variable [!DNL Maximum Elements] está establecido en 0. Cuando este parámetro se establece en 0, el servidor de Data Workbench utiliza su valor predeterminado interno de 32768.

1. Guarde el [!DNL Referrer.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana, haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

## Parámetros de sesión {#section-0a209b0c504041a5801f7f71a963c8b1}

Si está trabajando con [!DNL Site], puede especificar parámetros que definan los límites de la sesión de un visitante en un sitio web. Estos parámetros solo son válidos cuando se definen en una [!DNL Transformation Dataset Include] en el [!DNL Site] implementación.

Los siguientes parámetros son únicos, ya que pueden ser miembros de [!DNL Transformation Dataset Include] del archivo [!DNL Parameters] o pueden enumerarse como parámetros individuales en la variable [!DNL Transformation.cfg]archivo. Un parámetro se puede definir exactamente una vez, por lo que estos parámetros se definen en la variable [!DNL Transformation.cfg]o en el [!DNL Parameters] vector del conjunto de datos incluye archivo, no en ambos archivos.
**Duración máxima de sesión y tiempo de espera de sesión**

La duración máxima de sesión y el tiempo de espera de sesión son parámetros de cadena que definen la duración de la sesión de un visitante. Estos parámetros funcionan con el parámetro Dominios internos para determinar la duración de la sesión.

Duración máxima de sesión especifica la duración más larga de la sesión antes de que se inicie una nueva sesión. Esto evita que las páginas web con contenido automático se actualicen desde la creación de sesiones que son arbitrariamente largas. Si el referente de un clic se establece en una de las entradas del parámetro Dominios internos , este tiempo de espera se utiliza para definir el final de una sesión. Ninguna sesión puede ser superior a la duración máxima de sesión especificada independientemente de la cantidad de clics que contenga. El valor recomendado es de 48 horas.

Tiempo de espera de sesión especifica el tiempo que debe transcurrir entre las entradas de registro de un visitante determinado para determinar el final de una sesión y el inicio de una nueva (es decir, el tiempo de espera habitual que se utiliza para definir una sesión de usuario). El valor recomendado de este parámetro es de 30 minutos. Si el referente de un clic no está establecido en uno de los referentes del parámetro Dominios internos , se utiliza este tiempo de espera para definir la sesión. Si cs(referrer-domain) para una entrada de registro está en la lista de dominios internos, la duración máxima de la sesión determina si la entrada de registro actual es parte de una sesión existente o el inicio de una nueva sesión.

Considere una situación en la que se llama a un visitante desde su equipo durante un período de tiempo superior al tiempo de espera de sesión mientras navega por el sitio. Al regresar, continúa explorando donde lo dejó. Dado que el visitante nunca abandona el sitio o cierra su explorador, el cs(dominio del referente) de su siguiente clic es el mismo que el dominio interno y su sesión original permanece activa mientras no se alcance la configuración Duración máxima de sesión . Si el dominio del sitio aparece como un dominio interno y no se alcanza el tiempo de espera máximo, la interacción del visitante aparece como una sola sesión y no como dos sesiones independientes. Sin embargo, si el visitante regresa a su equipo y el siguiente clic tiene un referente externo (o en blanco), se inicia una nueva sesión.

>[!NOTE]
>
>La variable [!DNL Sessionize] transformación [!DNL Timeout Condition] también influye en la determinación de la duración de la sesión de un visitante. Si no se aplica el tiempo de espera de sesión y la duración máxima de sesión, se usa la variable [!DNL Timeout Condition] se comprueba para determinar si una entrada de registro debe considerarse el inicio de una nueva sesión. Para obtener más información, consulte [Transformaciones de datos](../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

**Para editar los parámetros de Duración máxima de sesión y Tiempo de espera de sesión**

Si está trabajando con [!DNL Site], es probable que su implementación predeterminada incluya un [!DNL Transformation Dataset Include] en el que se especifican los nombres y los valores recomendados de estos parámetros.

1. Abra el [!DNL Profile Manager] dentro de su perfil de conjunto de datos y vaya a [!DNL Dataset\Transformation\Traffic\Session Parameters.cfg].

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que se definen estos parámetros puede diferir de la ubicación descrita.

1. Edite los valores de los parámetros como desee. Asegúrese de especificar las unidades deseadas (minutos, horas, etc.).

   ![](assets/cfg_WebParameters_SessionParameters.png)

1. Guarde el [!DNL Session Parameters.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** >  **[!UICONTROL profile name]**, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.

**[!DNL Internal Domains]**

[!DNL Internal Domains] es un parámetro vectorial que enumera los hosts de nivel de dominio (referentes internos) que deben tratarse como parte de un sitio web en particular. Estos hosts se eliminan de la dimensión del referente (que es una lista de la información del referente externo). Cuando cs(referrer-domain) coincide con cualquiera de las cadenas enumeradas en el conjunto de dominios internos, se ignora el tiempo de espera de sesión y se utiliza la duración máxima de sesión para determinar la duración de la sesión.

El parámetro Dominios internos también se puede usar para evitar el inicio de una nueva sesión cuando los visitantes se desplazan entre los múltiples dominios de una empresa asociados de una manera que supera el tiempo de espera de sesión. Por ejemplo, considere una empresa que tiene partes de su sitio divididas en dos dominios: se registra uno ( [!DNL xyz.com]) y el otro no se registra ( [!DNL xyz-unlogged.com]). Si estos sitios están integrados de una manera que facilite el movimiento fluido del tráfico entre los dos dominios, no es deseable generar una sesión diferente cada vez que el visitante se desplace desde [!DNL xyz-unlogged.com] volver al dominio [!DNL xyz.com] dominio. Listing [!DNL xyz-unlogged.com] como dominio interno evita que las sesiones se dividan en varias sesiones como resultado del tráfico en estos dos dominios siempre y cuando no se alcance la configuración de duración máxima de sesión .

**Para agregar un dominio interno**

Si está trabajando con [!DNL Site], su implementación predeterminada incluye un [!DNL Transformation Dataset Include] para definir el parámetro Dominios internos. En este archivo, el parámetro se denomina ; solo debe introducir los dominios internos que desea incluir y guardar el archivo actualizado.

1. Abra el [!DNL Profile Manager] dentro de su perfil de conjunto de datos y vaya a [!DNL Dataset\Transformation\Traffic\Internal Domains.cfg.]

   >[!NOTE]
   >
   >Si ha personalizado la implementación de [!DNL Site], el archivo en el que se define el parámetro Dominios internos puede diferir de la ubicación descrita.

1. Clic con el botón derecho **[!UICONTROL Value]** para el parámetro vectorial Dominios internos y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Value]**.

1. Edite los valores como desee.

   ![](assets/cfg_WebParameters_InternalDomains.png)

1. Guarde el [!DNL Internal Domains.cfg] archivo haciendo clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

1. Para que los cambios realizados localmente tengan efecto, en la variable [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, donde nombre de perfil es el nombre del perfil del conjunto de datos o el perfil heredado al que pertenece el archivo de inclusión del conjunto de datos.

   >[!NOTE]
   >
   >No guarde el archivo de configuración modificado en ninguno de los perfiles internos proporcionados por Adobe, ya que los cambios se sobrescriben al instalar actualizaciones en estos perfiles.
