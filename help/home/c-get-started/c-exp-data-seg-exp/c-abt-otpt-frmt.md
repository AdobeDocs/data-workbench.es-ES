---
description: Directrices para especificar el formato de salida.
solution: Analytics
title: Formato de salida
topic: Data workbench
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato de salida{#output-format}

Directrices para especificar el formato de salida.

* Cada métrica o nombre de dimensión debe comenzar y finalizar con un signo de porcentaje (%).

   * %XYZ% especifica el elemento de dimensión XYZ correspondiente al elemento de Nivel. Se genera un error si la dimensión XYZ no es uno a uno o uno a varios con Level.
   * %=XYZ% especifica el valor de la métrica o la fórmula de métrica XYZ para el elemento determinado de Nivel.

* Los nombres de dimensión que sean dos palabras o más no requieren guiones bajos.
* Los nombres de métricas que sean dos palabras o más requieren guiones bajos.

>[!NOTE]
>
>Si mantiene pulsada la tecla Ctrl y hace clic con el botón secundario en el [!DNL Output Format] campo, [!DNL Insert menu] aparecerá un mensaje. Este menú contiene una lista de caracteres especiales (por ejemplo, el tabulador) que a menudo se utilizan como delimitadores.

Si desea exportar los datos de duración de la sesión para su segmento, debe crear una nueva métrica basada en la métrica Duración de la sesión. La nueva métrica, que se utiliza solamente con el [!DNL Output Format] campo de exportación de segmentos, permite a Microsoft Excel interpretar correctamente las sesiones que duran menos de una hora. Para crear una nueva métrica de duración de sesión, abra el [!DNL Session Duration.metric] archivo (desde el [!DNL Profile Manager]) e inserte un signo de almohadilla (#) en la cadena de hora: [!DNL ftime = string: %#H:%M:%S]

El signo de almohadilla hace que un &quot;0&quot; inicial se anexe a duraciones de sesión inferiores a 1 hora. Como resultado, Excel interpreta 0:53:21 como 53 minutos y 21 segundos. Guarde la nueva métrica con un nombre diferente y cárguela en el perfil adecuado para que otros la utilicen. Para ello, haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL User] columna y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
