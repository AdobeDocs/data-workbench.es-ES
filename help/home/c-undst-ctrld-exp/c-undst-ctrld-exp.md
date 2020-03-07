---
description: Los experimentos controlados son pruebas que permiten comparar los resultados obtenidos de un grupo de muestra experimental con los de un grupo de control estándar.
solution: Insight,Analytics
title: Experimentos controlados por el área de trabajo de datos
topic: Data workbench
uuid: 5fce2d9e-4975-44e4-a7c0-11064d8d28b4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Experimentos controlados por el área de trabajo de datos{#data-workbench-controlled-experiments}

Los experimentos controlados son pruebas que permiten comparar los resultados obtenidos de un grupo de muestra experimental con los de un grupo de control estándar.

El sitio permite implementar, medir y analizar los experimentos controlados y sus resultados en relación con diferentes aspectos del sitio web. De este modo, puede probar las hipótesis relativas a la mejora del rendimiento del sitio web antes de dedicar un tiempo o dinero considerable a implementar los cambios propuestos.

>[!NOTE]
>
>Los experimentos del sitio solo se pueden analizar en conjuntos de datos donde el único método de identificación del visitante que se utiliza es el [!DNL Sensor] método de cookie persistente establecido. Los sensores que se ejecutan en servidores J2EE (JBoss, Tomcat, WebLogic y WebSphere) no admiten la experimentación controlada. Para obtener más información, consulte la siguiente sección.

Con el uso del sitio, puede implementar experimentos A/B, A/B/A y multivariados controlados para recopilar datos de prueba suficientes y proporcionar datos estadísticamente precisos para una evaluación detallada de la hipótesis, sin afectar el rendimiento actual del sitio web.
