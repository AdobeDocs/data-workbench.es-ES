---
description: Ahora, Data Workbench admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales.
title: Instalación del Editor de métodos de entrada
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56,0bdc7d95-b49a-4ca5-9fde-9c1ce2cd14ec,e4e1c016-0544-434a-b82e-fdd2a4af316c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Instalación del Editor de métodos de entrada{#installing-the-input-method-editor}

Ahora, Data Workbench admite el Editor de métodos de entrada (IME) como proceso de entrada de texto secundario para idiomas internacionales.

Los IME le permiten introducir caracteres internacionales utilizando una variedad de métodos adecuados para su idioma local. Data Workbench proporciona un cuadro de diálogo de entrada que le permite abrir y utilizar el IME deseado para campos de texto.

>[!NOTE]
>
>Para la versión 6.1 de Data Workbench, solo se admitirá el teclado chino simplificado virtual. La introducción de otros idiomas a través del IME podría dar como resultado un comportamiento inesperado.

## Uso de un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Para utilizar la función de entrada de texto IME flotante:

1. Haga clic **[!UICONTROL Alt + Space]** para cualquier área de entrada de texto.
1. Introduzca valores utilizando el IME de su sistema.
1. Cierre el cuadro de diálogo de entrada seleccionando la tecla **[!UICONTROL Enter]** o haciendo clic en el botón **[!UICONTROL OK]**.

   El cuadro de diálogo desaparecerá y los caracteres aparecerán en el campo seleccionado.

**Actualización del archivo Insight.cfg**

Para emplear el IME, debe actualizar el archivo [!DNL Insight.cfg] con esta configuración:

```
Localized IME = bool: true
```

Si esta configuración no existe en el archivo de configuración, al pulsar **[!UICONTROL Alt + Space]** no se activará la función IME.

**Comenzando Insight en otro idioma:** para admitir mejor los recursos localizados como una pantalla de inicio y para admitir varios idiomas en el futuro, Data Workbench requiere argumentos de línea de comandos que identifiquen el idioma que se va a cargar. El idioma predeterminado es inglés.

Si inicia Data Workbench en chino, es necesario que invoque [!DNL Insight.exe] con el argumento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

(Estos argumentos de línea de comandos no distinguen entre mayúsculas y minúsculas).
