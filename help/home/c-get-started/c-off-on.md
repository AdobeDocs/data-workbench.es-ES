---
description: Información sobre cómo trabajar con el servidor de Data Workbench sin conexión o en línea.
title: Trabajar sin conexión y en línea
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Trabajar sin conexión y en línea{#working-offline-and-online}

Información sobre cómo trabajar con el servidor de Data Workbench sin conexión o en línea.

Data Workbench descarga automáticamente las actualizaciones del perfil y sus datos desde el servidor de Data Workbench si tiene una conexión de red con [!DNL server] y está trabajando en línea. Si no ha especificado que funcione en línea, la Data Workbench carga el perfil y sus datos desde la caché del equipo. En este caso, está viendo la versión del perfil y sus datos que se descargaron la última vez que trabajó en línea con el perfil.

Trabajar sin conexión ofrece una ventaja en la velocidad de procesamiento, ya que está trabajando desde la caché local y consultando los datos en su propio equipo. Al trabajar en línea, cada consulta debe volver al servidor de Data Workbench, que tarda más y le obliga a competir con otros usuarios en línea por los recursos del servidor. Siempre que tenga una conexión de red con el servidor de Data Workbench, trabajar sin conexión impide que el servidor de Data Workbench actualice los perfiles o datos de la Data Workbench, pero no le impide guardar elementos en el servidor de Data Workbench.

Debido a la capacidad de trabajar sin conexión, el servidor de Data Workbench se dimensiona para administrar cierta cantidad de entrada de tráfico en tiempo real y cierta cantidad de datos en el conjunto de datos, junto con un cierto número de usuarios de Data Workbench, pero no tiene que tener un tamaño que admita el número máximo de usuarios simultáneos (lo que en la práctica no ocurre con frecuencia). Debido a que los usuarios generalmente buscan tendencias y relaciones, explorar los datos a medida que avanza, en la mayoría de los casos no necesita recuentos exactos. Si es necesario consultar y resolver recuentos exactos usando los datos actuales, puede trabajar en línea y obtenerlo, pero las consultas tardan más en resolverse al 100 por ciento.

**Para trabajar en línea o sin conexión**

En la barra lateral, haga clic en la configuración **[!UICONTROL Connection]** y haga clic en **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Cuando trabaja en línea, la Data Workbench se conecta al servidor de Data Workbench y sincroniza la información de su equipo con el perfil y su información de conjunto de datos que reside en el servidor de Data Workbench.

La configuración predeterminada para la Data Workbench es trabajar sin conexión, pero como se describe en la siguiente sección, cada usuario puede cambiar su archivo [!DNL Insight.cfg] para que su instancia de Data Workbench funcione en línea de forma predeterminada.

**Para trabajar en línea de forma predeterminada**

1. Vaya al directorio de instalación de Insight .
1. Abra el archivo [!DNL Insight.cfg] en un editor de texto.
1. Agregue la línea resaltada al archivo como se muestra en el siguiente ejemplo:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La próxima vez que abra la Data Workbench, se conectará al servidor de Data Workbench y funcionará en línea de forma predeterminada.
