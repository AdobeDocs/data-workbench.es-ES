---
description: El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de evento o datos de búsqueda.
title: Acerca de las dimensiones extendidas
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Acerca de las dimensiones extendidas{#about-extended-dimensions}

El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de evento o datos de búsqueda.

Las dimensiones personalizadas que defina se denominarán dimensiones extendidas. Puede utilizarlos para crear visualizaciones, crear métricas extendidas o realizar análisis para comprender las operaciones y los problemas asociados con el canal empresarial. Puede definir varios tipos de dimensiones extendidas en el archivo [!DNL Transformation.cfg] o en los archivos [!DNL Transformation Dataset Include].

Una dimensión extendida representa una relación entre los valores de los campos de registro y una dimensión principal. Una dimensión principal puede ser cualquier dimensión contable definida por el usuario. Consulte [Dimension contables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Se especifica el elemento principal al definir la dimensión en el archivo [!DNL Transformation.cfg] o en un archivo [!DNL Transformation Dataset Include]. El elemento principal de una dimensión es el mismo que su nivel. Por ejemplo, si define una dimensión con una dimensión principal de Sesión, entonces esa dimensión es una dimensión de nivel de sesión.

>[!NOTE]
>
>Los valores de los campos de registro pueden proceder de los valores inherentes disponibles en los archivos de registro ( [!DNL .vsl]) u otras fuentes de datos de evento o de los campos de registro ampliados creados mediante transformaciones.

Para añadir una dimensión ampliada a una visualización, puede acceder a ella desde la lista Ampliada en el menú [!DNL Select Dimension] . Por ejemplo, para añadir una dimensión extendida a una visualización de gráfico, haga clic con el botón derecho en el espacio de trabajo y haga clic en **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Si desea organizar la lista de las dimensiones ampliadas dentro de la interfaz de Data Workbench, puede mover las dimensiones ampliadas a subcarpetas que cree. Consulte el capítulo Interfaces administrativas de la *Guía del usuario de Data Workbench*. Si lo hace, los nombres de las subcarpetas también aparecen en el menú, como en Añadir visualización > Gráfico > Extendido > &lt;*nombre de subcarpeta*> > &lt;*nombre de dimensión*>.

Para ver todas las dimensiones que se han definido para el perfil del conjunto de datos y el tamaño del búfer para cada una, abra la interfaz [!DNL Detailed Status] en Data Workbench y haga clic en **[!UICONTROL Performance]** y luego en **[!UICONTROL Dimensions]** para expandir los nodos. El tamaño del búfer, que controla los tiempos de consulta, se expresa en MB. Para obtener más información sobre la interfaz [!DNL Detailed Status], consulte la guía de administración e instalación del servidor.
