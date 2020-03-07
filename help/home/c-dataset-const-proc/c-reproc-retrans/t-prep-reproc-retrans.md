---
description: Pasos para garantizar que el reprocesamiento o la retransformación se realicen sin problemas y finalice a tiempo para que los usuarios del área de trabajo de datos puedan volver a trabajar
solution: Analytics
title: Preparación para reprocesamiento o retransformación
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Preparación para reprocesamiento o retransformación{#preparing-for-reprocessing-or-retransformation}

Pasos para garantizar que el reprocesamiento o la retransformación se realicen sin problemas y finalice a tiempo para que los usuarios del área de trabajo de datos puedan volver a trabajar

1. Para determinar el tiempo transcurrido desde el procesamiento o la transformación anterior, compruebe el perfil del conjunto de datos [!DNL Processing Mode History] en la [!DNL Detailed Status] interfaz.

   1. Mientras trabaja en su perfil de conjunto de datos, abra la [!DNL Detailed Status] interfaz.
   1. Haga clic **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** para ver los tiempos transcurridos desde el procesamiento o la transformación anterior.

      * Fast Input es el tiempo total necesario para el procesamiento del registro.
      * Fusión rápida es el tiempo total necesario para la transformación.
      * La suma de las dos veces (Entrada rápida + Combinación rápida) es el tiempo total necesario para procesar el conjunto de datos.
      El ejemplo siguiente indica que el procesamiento del registro tardó aproximadamente 43 segundos, mientras que la transformación tardó menos de 2 minutos.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Para obtener más información sobre la [!DNL Detailed Status] interfaz, consulte la Guía *del usuario de*&#x200B;Área de trabajo de datos.


1. Programe y planifique el reprocesamiento. Debido a que los usuarios del área de trabajo de datos no tienen acceso a los datos durante la fase de procesamiento del registro, asegúrese de programar el reprocesamiento para que se produzca durante un tiempo adecuado, como durante el fin de semana.
1. Monitorear el progreso del reprocesamiento y la retransformación mediante los campos de la sección [!DNL Processing Legend.] Para obtener más información sobre el [!DNL Processing Legend], consulte la Guía del usuario *del área de trabajo de datos*.
