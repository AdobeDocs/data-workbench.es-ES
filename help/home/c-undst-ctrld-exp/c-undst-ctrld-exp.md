---
description: Los experimentos controlados son pruebas que permiten comparar los resultados obtenidos de un grupo de muestra experimental con los de un grupo de control estándar.
solution: Analytics
title: Experimentos controlados por Data Workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
exl-id: 40bcf6a4-c722-427c-81ac-45dec1eae0b5
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 0%

---

# Experimentos controlados por Data Workbench{#data-workbench-controlled-experiments}

Los experimentos controlados son pruebas que permiten comparar los resultados obtenidos de un grupo de muestra experimental con los de un grupo de control estándar.

El sitio permite implementar, medir y analizar experimentos controlados y sus resultados en relación con distintos aspectos del sitio web. Al hacerlo, puede probar hipótesis relativas a la mejora del rendimiento del sitio web antes de dedicar un tiempo o un dinero considerable a la implementación completa de los cambios propuestos.

>[!NOTE]
>
>Los experimentos del sitio solo se pueden analizar en conjuntos de datos en los que el único método de identificación de visitantes que se utiliza es la variable [!DNL Sensor] establezca el método de cookie persistente. Los sensores que se ejecutan en servidores J2EE (JBoss, Tomcat, WebLogic y WebSphere) no admiten experimentación controlada. Para obtener más información, consulte la siguiente sección.

Mediante el uso de Site, puede implementar experimentos A/B, A/B/A y multivariados controlados con el fin de recopilar suficientes datos de prueba para proporcionar datos estadísticamente precisos que permitan realizar una evaluación detallada de la hipótesis, sin afectar el rendimiento actual del sitio web.
