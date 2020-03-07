---
description: El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de eventos o datos de búsqueda.
solution: Analytics
title: Acerca de las dimensiones extendidas
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Acerca de las dimensiones extendidas{#about-extended-dimensions}

El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de eventos o datos de búsqueda.

Las dimensiones personalizadas que defina se denominarán dimensiones extendidas. Puede utilizarlos para crear visualizaciones, generar métricas ampliadas o realizar análisis para comprender las operaciones y los problemas asociados con el canal de su negocio. Puede definir varios tipos de dimensiones extendidas en el [!DNL Transformation.cfg] archivo o en [!DNL Transformation Dataset Include] los archivos.

Una dimensión extendida representa una relación entre los valores de los campos de registro y una dimensión principal. Una dimensión principal puede ser cualquier dimensión contable definida por el usuario. Consulte [Dimensiones](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)contables. Especifique el elemento principal al definir la dimensión en el [!DNL Transformation.cfg] archivo o en un [!DNL Transformation Dataset Include] archivo. El elemento principal de una dimensión es el mismo que su nivel. Por ejemplo, si define una dimensión con un elemento principal de Session, esa dimensión es una dimensión de nivel de sesión.

>[!NOTE]
>
>Los valores de los campos de registro pueden provenir de los valores inherentes disponibles en los archivos de registro ( [!DNL .vsl]) u otras fuentes de datos de eventos o de los campos de registro ampliados creados mediante transformaciones.

Para agregar una dimensión ampliada a una visualización, puede acceder a ella desde la lista Ampliada del [!DNL Select Dimension] menú. Por ejemplo, para agregar una dimensión extendida a una visualización de gráfico, haga clic con el botón derecho en el espacio de trabajo y haga clic en **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Si desea organizar la lista de dimensiones extendidas dentro de la interfaz del área de trabajo de datos, puede mover las dimensiones extendidas a las subcarpetas que cree. Consulte el capítulo Interfaces administrativas de la Guía *del usuario de Área de trabajo de* datos. Si lo hace, los nombres de las subcarpetas también aparecerán en el menú, como en Agregar visualización > Gráfico > Extendido > &lt;nombre *de* subcarpeta> > &lt;nombre *de* dimensión>.

Para ver todas las dimensiones que se han definido para el perfil del conjunto de datos y el tamaño del búfer de cada una, abra la [!DNL Detailed Status] interfaz en el área de trabajo de datos y haga clic en **[!UICONTROL Performance]**, luego **[!UICONTROL Dimensions]** para expandir los nodos. El tamaño del búfer, que controla los tiempos de consulta, se expresa en MB. Para obtener más información sobre la [!DNL Detailed Status] interfaz, consulte la Guía de administración e instalación del servidor.
