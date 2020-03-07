---
description: El área de trabajo de datos ahora admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales.
solution: Analytics
title: Instalación del Editor de métodos de entrada
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación del Editor de métodos de entrada{#installing-the-input-method-editor}

El área de trabajo de datos ahora admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales.

Los IME le permiten introducir caracteres internacionales utilizando una variedad de métodos adecuados para su idioma local. Área de trabajo de datos proporciona un cuadro de diálogo de entrada que le permite abrir y utilizar el IME deseado para los campos de texto.

>[!NOTE]
>
>Para la versión 6.1 del área de trabajo de datos, solo se admitirá el teclado virtual chino simplificado. La introducción de otros idiomas a través del IME podría provocar un comportamiento inesperado.

## Uso de un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Para utilizar la función de entrada de texto IME flotante:

1. Haga clic **[!UICONTROL Alt + Space]** para buscar cualquier área de entrada de texto.
1. Introduzca valores utilizando el IME del sistema.
1. Para cerrar el cuadro de diálogo de entrada, seleccione la **[!UICONTROL Enter]** tecla o haga clic en el **[!UICONTROL OK]** botón.

   El cuadro de diálogo desaparecerá y los caracteres aparecerán en el campo seleccionado.

**Actualización del archivo Insight.cfg**

Para utilizar el IME, debe actualizar el [!DNL Insight.cfg] archivo con esta configuración:

```
Localized IME = bool: true
```

Si esta configuración no existe en el archivo de configuración, al pulsar **[!UICONTROL Alt + Space]** no se activará la función IME.

**Inicio de Insight en otro idioma:** Para admitir mejor los recursos localizados como una pantalla de bienvenida y para admitir varios idiomas en el futuro, el área de trabajo de datos requiere argumentos de línea de comandos que identifiquen el idioma que se va a cargar. El idioma predeterminado es el inglés.

Para iniciar el área de trabajo de datos en chino es necesario invocar [!DNL Insight.exe] con el argumento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Estos argumentos de la línea de comandos no distinguen entre mayúsculas y minúsculas).
