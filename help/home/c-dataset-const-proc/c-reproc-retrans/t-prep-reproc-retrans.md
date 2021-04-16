---
description: Pasos para garantizar que el reprocesamiento o la retransformación se realicen sin problemas y terminen a tiempo para que los usuarios de Data Workbench vuelvan al trabajo
title: Preparación para reprocesamiento o retransformación
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Preparación para reprocesamiento o retransformación{#preparing-for-reprocessing-or-retransformation}

Pasos para garantizar que el reprocesamiento o la retransformación se realicen sin problemas y terminen a tiempo para que los usuarios de Data Workbench vuelvan al trabajo

1. Determine el tiempo transcurrido del procesamiento o transformación anterior comprobando el [!DNL Processing Mode History] del perfil del conjunto de datos en la interfaz [!DNL Detailed Status].

   1. Mientras trabaja en el perfil del conjunto de datos, abra la interfaz [!DNL Detailed Status] .
   1. Haga clic en **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]*** > **[!UICONTROL Processing Mode History]** para ver los tiempos transcurridos desde el procesamiento o transformación anterior.

      * Entrada rápida es el tiempo total necesario para el procesamiento de registros.
      * Fusión rápida es el tiempo total necesario para la transformación.
      * La suma de las dos veces (Entrada rápida + Fusión rápida) es el tiempo total necesario para procesar el conjunto de datos.

      El ejemplo siguiente indica que el procesamiento del registro tardó aproximadamente 43 segundos, mientras que la transformación tardó menos de 2 minutos.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Para obtener más información sobre la interfaz [!DNL Detailed Status], consulte la *Guía del usuario de Data Workbench*.


1. Programe y planifique el reprocesamiento. Debido a que los usuarios de Data Workbench no tienen acceso a los datos durante la fase de procesamiento del registro, asegúrese de programar el reprocesamiento para que se produzca durante un tiempo adecuado, como durante el fin de semana.
1. Monitorice el progreso del reprocesamiento y retransformación utilizando los campos en [!DNL Processing Legend.] Para obtener más información acerca de [!DNL Processing Legend], consulte la *Guía del usuario de la Data Workbench*.
