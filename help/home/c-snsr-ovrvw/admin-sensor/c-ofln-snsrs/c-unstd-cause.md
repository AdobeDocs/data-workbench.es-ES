---
description: Información sobre la resolución de problemas del servidor web, como si el servidor web se elimina de la rotación o si falla.
solution: Insight
title: Explicación de las causas
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de las causas{#understanding-the-causes}

Información sobre la resolución de problemas del servidor web, como si el servidor web se elimina de la rotación o si falla.

## Cuando se elimina la rotación de un servidor Web {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Cuando un servidor web se elimina de rotación de un grupo de servidores, pero se conecta de otro modo con el transmisor que envía latidos periódicos, el valor Con el tiempo se mantiene actualizado y no se requiere ninguna intervención por parte de nadie.

## Cuando un servidor Web falla {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Cuando un servidor web está completamente sin conexión debido a algún fallo catastrófico, o no envía datos o latidos, el valor Con el tiempo del [!DNL data workbench server] se detiene para garantizar que representa la última vez que [!DNL data workbench server] recibió datos de TODAS las fuentes de datos de las que conoce. El propio sistema continúa procesando datos, que aún están disponibles para análisis en el área de trabajo de datos, pero cualquier elemento del área de trabajo [!DNL data workbench server] que se base en el valor Con el tiempo no funciona. Por ejemplo, el valor Con el tiempo activa los informes y se utiliza para crear muchas dimensiones derivadas en el sistema. Cuando el valor Con el tiempo se ha detenido, los informes no se activan y estas dimensiones derivadas particulares no están disponibles.

Por ejemplo: si WEB2 se desconectó el 15 de junio y no envió ningún dato durante cinco días, el valor Con el tiempo será el 15 de junio. La dimensión de Ayer, por ejemplo, sería el 14 de junio, aunque la fecha de hoy sea el 20 de junio.