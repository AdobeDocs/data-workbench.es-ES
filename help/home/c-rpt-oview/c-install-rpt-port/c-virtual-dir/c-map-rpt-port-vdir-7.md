---
description: Pasos para asignar el portal de informes a un directorio virtual (IIS 7.0 o superior).
title: Asignación del portal de informes a un directorio virtual (IIS 7.0 o superior)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 5%

---

# Asignación del portal de informes a un directorio virtual (IIS 7.0 o superior){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

{{eol}}

Pasos para asignar el portal de informes a un directorio virtual (IIS 7.0 o superior).

Actualmente, la mayoría de los clientes de Managed Service tienen servidores con el sistema operativo Windows Server 2008 y el servidor web IIS 7.0 o superior.

## Requisitos previos {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Asegúrese de que ASP y [!DNL ASP.Net] los componentes están instalados para IIS 7.0 o superior.
* Asegúrese de que el usuario web de IIS tenga [!DNL Modify] acceso al [!DNL E:\Portal\data\users.mdb] archivo. Puede cambiarlo haciendo clic con el botón derecho en la variable **[!UICONTROL users.mdb]** archivo y debajo [!DNL Properties], vaya a la [!DNL Security] pestaña . Si no ve el usuario web de IIS en la lista o no tiene la capacidad de agregar el usuario web de IIS a la lista, simplemente proporcione la [!DNL Users] agrupe [!DNL Modify] acceso.

* Asegúrese de que se esté utilizando la cuenta de usuario para ejecutar el [!DNL Application Pools] también tiene [!DNL Modify] acceso al [!DNL E:\Portal\data\users.mdb] y las carpetas [!DNL C:\Windows\Temp\].

## Pasos de instalación {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. En la máquina donde [!DNL Report Portal] esté instalado, inicie la [!DNL IIS Manager]:

   **[!UICONTROL Start]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Internet Information Services (IIS) Manager]**.

1. Seleccione **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Clic con el botón derecho **[!UICONTROL Default Web Site]** y seleccione **[!UICONTROL Add Virtual Directory]**.

1. Para un alias, introduzca Portal.
1. Para la ruta física, introduzca [!DNL E:\Portal\PortalASP].
1. Haga clic en **[!UICONTROL OK]**.

   El directorio virtual que ha creado aparece en la sección [!DNL Default Web Site].

1. Agregue los siguientes directorios virtuales bajo el directorio virtual que acaba de crear.

   | Crear este alias... | Para este recurso físico |
   |---|---|
   | Principal | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Imágenes | [!DNL E:\Portal\PortalFiles\Images] |
   | Output | Ubicación física del directorio en el que [!DNL Report Server] guarda el resultado de los conjuntos de informes. La carpeta de salida se puede ubicar en cualquier lugar y se le puede asignar cualquier nombre. Contiene una subcarpeta para cada conjunto de informes. Puede eliminar la variable [!DNL E:\Portal\PortalFiles\Output], pero mueva el [!DNL profiles.xml] a la ubicación física del archivo de salida. |

1. Cuando termine, compruebe que IIS muestre cuatro directorios virtuales nuevos. Asegúrese de que la estructura del directorio tiene una carpeta principal (con el mismo nombre que el portal) y cuatro subcarpetas.
1. Haga clic en **[!UICONTROL Application Pools]**, luego **[!UICONTROL DefaultAppPool]** (suponiendo que ese sea el que configuró con su portal).

1. Haga clic en **[!UICONTROL Advanced Settings]** y seleccione True para la opción Habilitar aplicaciones de 32 bits.
1. Para obtener la variable [!DNL Portal] para que funcione, debe convertirla en una aplicación. Después de configurar los directorios virtuales, haga clic con el botón derecho en el directorio virtual del portal y seleccione **[!UICONTROL Convert to Application]**.

## Sugerencias y trucos adicionales {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Puede descargar el [!DNL Portal] de Softdocs en **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Simplemente puede descargar el [!DNL ReportPortal-Release-1-0-0-7.zip].

* Ya no necesita el [!DNL ReportPortalSetup.xml], para que se pueda eliminar.
* En aras de la estandarización, coloque el contenido de este archivo zip en [!DNL E:\Portal].
* Para determinar el servidor SMTP Para los clientes de servicios administrados, puede ir aquí.
* Inserte una solicitud con NetOps para cambiar la entrada de nombre de dominio en IIS para el servidor de informes a algo más sencillo; por ejemplo, [!DNL reports.clientname.insight.omniture.com], de modo que la URL general del portal sea [!DNL https://reports.clientname.insight.omniture.com/Portal]. Configure las [!DNL email.asa] una vez realizado este cambio.
