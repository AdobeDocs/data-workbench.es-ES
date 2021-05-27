---
description: Integre la Data Workbench con Adobe Target. Exporte segmentos de datos y rellene automáticamente archivos de exportación.
title: Integración de Data Workbench con Adobe Target
exl-id: e7c41e7a-aae6-4b5c-8b14-7ae97b62d70b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '664'
ht-degree: 1%

---

# Integración de Data Workbench con Adobe Target

La integración de la Data Workbench de Adobes con Adobe Target se ha vuelto más sencilla con las funciones de Data Workbench para exportar segmentos de datos y rellenar automáticamente archivos de exportación.

La Data Workbench de Adobe proporciona integración de bucle cerrado con Adobe Target para compartir datos y generar informes. Dentro de la Data Workbench, puede analizar poblaciones para segmentos significativos usando todos los datos disponibles, incluidas las conversiones sin conexión a través de canales como teléfono, una tienda, etc.

Por ejemplo, un visitante busca zapatos en su sitio web pero no realiza ninguna conversión. Por el contrario, el visitante descarga un cupón del 20 por ciento de descuento en su siguiente compra y luego compra una camisa en su tienda. Con la Data Workbench, puede recopilar esos datos y, a continuación, enviar esos datos de perfil a Target para mostrar que el visitante compró una camisa sin conexión. A continuación, puede establecer como objetivo una campaña que ofrezca una corbata a ese visitante, cuando normalmente Target podría intentar volver a vender zapatos a ese visitante.

## Configuración de la Data Workbench con Adobe Target

1. Haga clic con el botón derecho en el encabezado de la ventana [!UICONTROL Detail Table].

   ![](assets/insight-to-tnt.png)

1. Seleccione **[!UICONTROL New Target Export]** e introduzca el nombre de un nuevo archivo de exportación en el comando **[!UICONTROL Save As]** del menú.

1. Haga clic en **[!UICONTROL Save Export File]**.

   Se abrirá una ventana de plantilla de exportación.

   Toda la información de Adobe Target se rellena automáticamente. Se crea la lista de parámetros en función de lo que se ponga en la exportación de segmentos. Cuando se complete, Data Workbench enviará los datos al servidor de Adobe Target.

   **Nota:** El archivo de plantilla debe configurarlo  [!UICONTROL Profile Architect]. Es necesario introducir [!UICONTROL Client Name], [!UICONTROL Domain Postfix], [!UICONTROL Mbox Host] y [!UICONTROL Mbox Name]. Si tiene varios sitios, rellene varias plantillas y guárdelas en el servidor. Las plantillas del Administrador de perfiles se encuentran en `Context\FileNew\Detail Table\Export\Copy`.

   ![](assets/insight-to-tnt1.png)

1. Especifique el parámetro de consulta [!UICONTROL mboxPC].

   Si el nombre del atributo de Data Workbench es algo distinto de [!UICONTROL mboxPC], debe editar el parámetro de consulta adecuado y cambiarle el nombre a _mboxPC_.

   ![](assets/insight-to-tnt2.png)

   Al guardar el archivo de exportación en el servidor, se iniciará la exportación. Cuando se complete, la aplicación [!UICONTROL TnTSend.exe] se iniciará y comenzará a enviar datos a la cuenta de Target.

## Configuración de la Data Workbench para Target

Complete las siguientes tareas en Adobe Target:

Data Workbench está pasando perfiles de usuario a Adobe Target. Para configurar la exportación a Target, debe configurar y habilitar su API y proporcionar los parámetros **[!UICONTROL clientname]** y **[!UICONTROL domain postfix]** para el archivo de configuración de exportación (`export.cfg`).

Se ha añadido una nueva opción booleana denominada **[!UICONTROL Oneshot]** a los archivos de exportación de segmentos. Esta opción se incluye en el archivo de plantilla distribuido con el nuevo perfil. Si [!UICONTROL Oneshot] se configura como _true_, se cambiará el nombre del archivo `.export` a `.export.done-TIMESTAMP` una vez finalizada la exportación, lo que garantiza que el segmento nunca se exporte más de una vez. Esto es importante al exportar a Adobe Target.

**Nota:** Una llamada de Data Workbench a Adobe Target se cuenta como una  [!UICONTROL mbox] llamada, lo que requiere una llamada por cada perfil enviado. Por lo tanto, los costes aumentan si se requieren varias llamadas entre las dos soluciones.

Una configuración incompleta genera el siguiente mensaje de error en el registro:

```
TNT-040615-133212-Adobe-Target-Product-Test.log:
TnT Configuration left out these empty fields:
ClientName,MboxHost,MboxName
```

## Configuración de Adobe Target para Data Workbench

En Adobe Target, no se necesita ninguna configuración especial para que un cliente envíe datos de perfil. La información de perfil de un usuario se suele pasar en la solicitud [!UICONTROL mbox] normal y los servidores harán que los parámetros de perfil estén disponibles para una configuración de campaña dirigida como funcionalidad estándar sin ninguna configuración adicional.

Adobe Target tiene incorporada la integración de Datas Workbench, que se puede habilitar desde la página Detalles del cliente del superusuario. Al habilitar la opción, aparecerán segmentos compartidos desde la Data Workbench dentro de Adobe Target que estarán disponibles para la segmentación.

## Establecer informes de registro HTTP en ExportIntegration.exe

Reduzca los informes largos a [!UICONTROL HTTP.log] al utilizar [!UICONTROL ExportIntegration.exe] para exportar archivos de integración de Adobe Target.

Un nuevo archivo de configuración [!UICONTROL httpLoggingEI.cfg] (ubicado en `server\Admin\Export\httpLoggingEI.cfg`) le permite reducir el registro detallado en el archivo [!UICONTROL HTTP.log] para al exportar datos mediante [!UICONTROL ExportIntegration.exe]. Esto le permite detener el registro detallado de solicitudes/respuestas.

El registro detallado ya se captura en los archivos [!UICONTROL TnTSend.log].

__ Confiere en el registro detallado y en el registro detallado de  __ Falsestops en el  [!UICONTROL HTTP.log] archivo.

En la configuración False, solo se enviará un mensaje de advertencia al archivo [!UICONTROL HTTP.log] (no se enviará el contenido de información).
