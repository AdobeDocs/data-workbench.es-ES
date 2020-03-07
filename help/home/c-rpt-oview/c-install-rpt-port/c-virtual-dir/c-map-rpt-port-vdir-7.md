---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 7.0 o superior).
solution: Analytics
title: Asignación del portal de informes a un directorio virtual (IIS 7.0 o superior)
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Asignación del portal de informes a un directorio virtual (IIS 7.0 o superior){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Pasos para asignar el portal de informes a un directorio virtual (IIS 7.0 o superior).

Actualmente, la mayoría de los clientes de servicios administrados tienen servidores con el sistema operativo Windows Server 2008 y el servidor web IIS 7.0 o superior.

## Requisitos previos {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Asegúrese de que ASP y [!DNL ASP.Net] los componentes están instalados para IIS 7.0 o superior.
* Asegúrese de que el usuario web de IIS tiene [!DNL Modify] acceso al [!DNL E:\Portal\data\users.mdb] archivo. Puede cambiarlo haciendo clic con el botón derecho en el **[!UICONTROL users.mdb]** archivo y en [!DNL Properties], vaya a la [!DNL Security] ficha. Si no ve el usuario web de IIS en la lista o no tiene la capacidad de agregar el usuario web de IIS a la lista, simplemente conceda al [!DNL Users] grupo el [!DNL Modify] acceso.

* Asegúrese de que cualquier cuenta de usuario que se esté utilizando para ejecutar [!DNL Application Pools] también tenga [!DNL Modify] acceso a las carpetas [!DNL E:\Portal\data\users.mdb] y [!DNL C:\Windows\Temp\].

## Pasos de instalación {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. En el equipo en el que [!DNL Report Portal] está instalado, inicie la [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Select **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Haga clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL Add Virtual Directory]**.

1. Para un alias, introduzca Portal.
1. Para la ruta física, introduzca [!DNL E:\Portal\PortalASP].
1. Haga clic en **[!UICONTROL OK]**.

   El directorio virtual que ha creado aparece debajo de [!DNL Default Web Site].

1. Agregue los siguientes directorios virtuales en el directorio virtual que acaba de crear.

   | Crear este alias... | Para este recurso físico |
   |---|---|
   | Núcleo | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Imágenes | [!DNL E:\Portal\PortalFiles\Images] |
   | Salida | Ubicación física del directorio en el que [!DNL Report Server] se guarda el resultado de los conjuntos de informes. La carpeta de salida se puede ubicar en cualquier lugar y se le puede asignar cualquier nombre. Contiene una subcarpeta para cada conjunto de informes. Puede eliminar el [!DNL E:\Portal\PortalFiles\Output]archivo, pero moverlo [!DNL profiles.xml] a la ubicación física del archivo Output. |

1. Cuando termine, compruebe que IIS muestre cuatro directorios virtuales nuevos. Asegúrese de que la estructura de directorios tiene una carpeta principal (con el mismo nombre que el portal) y cuatro subcarpetas.
1. Haga clic en **[!UICONTROL Application Pools]**, luego **[!UICONTROL DefaultAppPool]** (suponiendo que sea el que configure con su portal).

1. Haga clic en **[!UICONTROL Advanced Settings]** y seleccione True para activar las aplicaciones de 32 bits.
1. Para que [!DNL Portal] funcione, debe convertirlo en una aplicación. Después de configurar los directorios virtuales, haga clic con el botón derecho en el directorio virtual Portal y seleccione **[!UICONTROL Convert to Application]**.

## Sugerencias y trucos adicionales {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Puede descargar el [!DNL Portal] desde Softdocs en **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Simplemente puede descargar el [!DNL ReportPortal-Release-1-0-0-7.zip].

* Ya no necesita el [!DNL ReportPortalSetup.xml], por lo que se puede eliminar.
* En aras de la estandarización, coloque el contenido de este archivo zip en [!DNL E:\Portal].
* Para determinar el servidor SMTP Para los clientes de servicios administrados, puede ir aquí.
* Coloque una solicitud con NetOps para cambiar la entrada del nombre de dominio en IIS para el servidor de informes a algo más sencillo; por ejemplo, [!DNL reports.clientname.insight.omniture.com]para que la dirección URL del portal sea [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configure el [!DNL email.asa] archivo una vez que se haya realizado este cambio.

