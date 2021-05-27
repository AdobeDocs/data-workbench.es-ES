---
description: El portal de informes está formado por un conjunto de páginas de servidor de aplicaciones (ASP) y archivos auxiliares.
title: Instalación de los archivos de la aplicación del portal de informes
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Instalación de los archivos de la aplicación del portal de informes{#install-the-report-portal-application-files}

El portal de informes está formado por un conjunto de páginas de servidor de aplicaciones (ASP) y archivos auxiliares.

Para instalar el [!DNL Report Portal], debe extraer estos archivos del archivo de distribución que recibió de Adobe e instalarlos en el equipo en el que se ejecuta Microsoft IIS.

**Para instalar los archivos de la  [!DNL Report Portal] aplicación**

1. Si aún no lo ha hecho, descargue el paquete de instalación (archivo .zip) para [!DNL Report Portal] del sitio FTP de Adobe.
1. En el equipo en el que se está ejecutando IIS, extraiga los archivos del paquete de instalación a cualquier ubicación. Este paso instala las siguientes subcarpetas y archivos en la carpeta VirtualPortalName.

   | Carpeta o archivo | Descripción |
   |---|---|
   | [!DNL \data\users.mdb] | Base de datos que contiene la lista de usuarios autorizados [!DNL Report Portal]. |
   | [!DNL \PortalASP\] | Carpeta que contiene los archivos ASP que conforman [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Carpeta que contiene cinco subcarpetas (Core, CSS, HTC, Images y Output) que contienen archivos de apoyo utilizados por [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Archivo de configuración que se utiliza para definir los directorios virtuales asociados con [!DNL Report Portal] (solo se usa con IIS 6.0). |

   El directorio tiene el siguiente aspecto:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >El nombre del directorio puede diferir del nombre mostrado en el ejemplo.

1. Cambie el nombre de la carpeta VSVirtualPortalName (u otro nombre) a lo que desee usar como directorio virtual raíz de su [!DNL Report Portal] (en lo sucesivo denominado *PortalName*). Para obtener más información sobre los directorios virtuales, consulte la siguiente sección.
