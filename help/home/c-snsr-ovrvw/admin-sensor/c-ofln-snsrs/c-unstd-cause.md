---
description: Información sobre la resolución de problemas del servidor web, como, por ejemplo, si el servidor web se elimina de la rotación o si falla el servidor web.
title: Explicación de las causas
uuid: a2801040-c859-4bf8-90d7-daf3d4f633f3
exl-id: 008116b0-7ef5-41ee-bd2e-a86d61acd634
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 2%

---

# Explicación de las causas{#understanding-the-causes}

Información sobre la resolución de problemas del servidor web, como, por ejemplo, si el servidor web se elimina de la rotación o si falla el servidor web.

## Cuando se elimina un servidor web de la rotación {#section-b9f709099cb44b4f9d1acb38ca5330e3}

Cuando un servidor web se quita de la rotación de un grupo de servidores, pero se conecta de otro modo con el transmisor que envía latidos periódicos, el valor Con tiempo se mantiene actualizado y no se requiere ninguna intervención por parte de nadie.

## Cuando un servidor web falla {#section-19280cf83ca44bd7b1ee11bfc74494d2}

Cuando un servidor web está completamente sin conexión debido a algún error catastrófico, o no está enviando datos o latidos, el valor Con respecto al tiempo en [!DNL data workbench server] se detiene para garantizar que representa la última vez que [!DNL data workbench server] recibió datos de TODAS las fuentes de datos de las que tiene conocimiento. El propio sistema sigue procesando los datos, que aún están disponibles para su análisis en Data Workbench, pero cualquier elemento del [!DNL data workbench server] que esté basado en el valor Con el tiempo no funciona. Por ejemplo, el informe Con el tiempo déclencheur y se utiliza para crear muchas dimensiones derivadas en el sistema. Cuando se detiene el valor Con el tiempo , los informes no se activan y estas dimensiones derivadas particulares no están disponibles.

Por ejemplo, si WEB2 se desconectara el 15 de junio y no enviara ningún dato durante cinco días, el valor Con fecha sería en algún momento el 15 de junio. La dimensión de Ayer, por ejemplo, sería el 14 de junio aunque la fecha de hoy sea el 20 de junio.
