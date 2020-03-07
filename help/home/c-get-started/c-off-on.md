---
description: Información sobre cómo trabajar con el servidor de Área de trabajo de datos sin conexión o en línea.
solution: Analytics
title: Trabajar sin conexión y en línea
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabajar sin conexión y en línea{#working-offline-and-online}

Información sobre cómo trabajar con el servidor de Área de trabajo de datos sin conexión o en línea.

Área de trabajo de datos descarga automáticamente las actualizaciones del perfil y sus datos desde el servidor de Área de trabajo de datos si tiene una conexión de red con el [!DNL server] y está trabajando en línea. Si no ha especificado que funcione en línea, Área de trabajo de datos carga el perfil y sus datos desde la caché del equipo. En este caso, está viendo la versión del perfil y sus datos que se descargaron la última vez que trabajó en línea con el perfil.

Trabajar sin conexión ofrece una ventaja de velocidad de procesamiento porque está trabajando desde la caché local y consultando los datos en su propio equipo. Al trabajar en línea, cada consulta debe volver al servidor de Área de trabajo de datos, que tarda más y le obliga a competir con otros usuarios en línea por los recursos del servidor. Mientras tenga una conexión de red con el servidor de Área de trabajo de datos, trabajar sin conexión impide que el servidor de Área de trabajo de datos actualice los perfiles o datos en el Área de trabajo de datos, pero no impide que guarde elementos en el servidor de Área de trabajo de datos.

Debido a la capacidad de trabajar sin conexión, el servidor de Área de trabajo de datos tiene el tamaño adecuado para administrar una cantidad de entrada de tráfico en tiempo real y cierta cantidad de datos en el conjunto de datos, junto con una cantidad determinada de usuarios de Área de trabajo de datos, pero no es necesario ajustar el tamaño para admitir el número máximo de usuarios simultáneos (lo que en la práctica no sucede con frecuencia). Debido a que los usuarios generalmente buscan tendencias y tasas, exploran los datos a medida que avanzan, en la mayoría de los casos no necesita recuentos exactos. Si es necesario consultar y resolver los recuentos exactos utilizando los datos actuales, puede trabajar en línea y obtenerlos, pero las consultas tardan más en resolverse al 100 por ciento.

**Para trabajar en línea o sin conexión**

En la barra lateral, haga clic en la **[!UICONTROL Connection]** configuración y en **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Cuando trabaja en línea, el Área de trabajo de datos se conecta al servidor del Área de trabajo de datos y sincroniza la información del equipo con el perfil y la información del conjunto de datos que reside en el servidor del Área de trabajo de datos.

La configuración predeterminada de Área de trabajo de datos es trabajar sin conexión, pero como se describe en la siguiente sección, cada usuario puede cambiar su [!DNL Insight.cfg] archivo para que su instancia de Área de trabajo de datos funcione en línea de forma predeterminada.

**Para trabajar en línea de forma predeterminada**

1. Vaya al directorio de instalación de Insight.
1. Abra el [!DNL Insight.cfg] archivo en un editor de texto.
1. Agregue la línea resaltada al archivo como se muestra en el siguiente ejemplo:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La próxima vez que abra Área de trabajo de datos, se conectará al servidor de Área de trabajo de datos y funcionará en línea de forma predeterminada.
