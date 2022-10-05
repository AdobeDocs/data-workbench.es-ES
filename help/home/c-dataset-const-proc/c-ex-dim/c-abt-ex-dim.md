---
description: El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de evento o datos de búsqueda.
title: Acerca de las dimensiones extendidas
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Acerca de las dimensiones extendidas{#about-extended-dimensions}

{{eol}}

El servidor de Insight (InsightServer64.exe) permite definir dimensiones personalizadas a partir de datos de evento o datos de búsqueda.

Las dimensiones personalizadas que defina se denominarán dimensiones extendidas. Puede utilizarlos para crear visualizaciones, crear métricas extendidas o realizar análisis para comprender las operaciones y los problemas asociados con el canal empresarial. Puede definir varios tipos de dimensiones extendidas en la variable [!DNL Transformation.cfg] archivo o en [!DNL Transformation Dataset Include] archivos.

Una dimensión extendida representa una relación entre los valores de los campos de registro y una dimensión principal. Una dimensión principal puede ser cualquier dimensión contable definida por el usuario. Consulte [Dimension contables](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Se especifica el elemento principal al definir la dimensión en la variable [!DNL Transformation.cfg] archivo o [!DNL Transformation Dataset Include] archivo. El elemento principal de una dimensión es el mismo que su nivel. Por ejemplo, si define una dimensión con una dimensión principal de Sesión, entonces esa dimensión es una dimensión de nivel de sesión.

>[!NOTE]
>
>Los valores de los campos de registro pueden proceder de los valores inherentes disponibles en el registro ( [!DNL .vsl]) archivos u otras fuentes de datos de evento o de campos de registro ampliados creados mediante transformaciones.

Para añadir una dimensión ampliada a una visualización, puede acceder a ella desde la lista Ampliada dentro del [!DNL Select Dimension] para abrir el Navegador. Por ejemplo, para añadir una dimensión extendida a una visualización de gráfico, haga clic con el botón derecho en el espacio de trabajo y haga clic en **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Si desea organizar la lista de las dimensiones ampliadas dentro de la interfaz de Data Workbench, puede mover las dimensiones ampliadas a subcarpetas que cree. Consulte el capítulo Interfaces administrativas de la sección *Guía del usuario de Data Workbench*. Si lo hace, los nombres de las subcarpetas también aparecen en el menú, como en Añadir visualización > Gráfico > Extendido > &lt;*nombre de subcarpeta*> > &lt;*nombre de dimensión*>.

Para ver todas las dimensiones que se han definido para el perfil del conjunto de datos y el tamaño del búfer para cada una, abra el [!DNL Detailed Status] interfaz en data workbench y haga clic en **[!UICONTROL Performance]**, luego **[!UICONTROL Dimensions]** para expandir los nodos. El tamaño del búfer, que controla los tiempos de consulta, se expresa en MB. Para obtener más información sobre la variable [!DNL Detailed Status] , consulte la guía Administración e instalación del servidor .
