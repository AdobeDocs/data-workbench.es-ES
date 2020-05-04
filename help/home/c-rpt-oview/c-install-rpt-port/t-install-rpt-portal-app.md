---
description: El portal de informes está formado por un conjunto de páginas de servidor de aplicaciones (ASP) y archivos auxiliares.
solution: Analytics
title: Instalación de los archivos de la aplicación de Report Portal
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: 7521fe7f5fabe8e1be26e140ffff577a42fce88b

---


# Instalación de los archivos de la aplicación de Report Portal{#install-the-report-portal-application-files}

El portal de informes está formado por un conjunto de páginas de servidor de aplicaciones (ASP) y archivos auxiliares.

Para instalar el [!DNL Report Portal], debe extraer estos archivos del archivo de distribución que ha recibido de Adobe e instalarlos en el equipo en el que se está ejecutando Microsoft IIS.

**Instalación de los archivos de la[!DNL Report Portal]aplicación**

1. Si aún no lo ha hecho, descargue el paquete de instalación (archivo .zip) del [!DNL Report Portal] sitio FTP de Adobe.
1. En el equipo en el que se está ejecutando IIS, extraiga los archivos del paquete de instalación en cualquier ubicación. Este paso instala las siguientes subcarpetas y archivos en la carpeta VirtualPortalName.

   | Carpeta o archivo | Descripción |
   |---|---|
   | [!DNL \data\users.mdb] | Base de datos que contiene la lista de [!DNL Report Portal] usuarios autorizados. |
   | [!DNL \PortalASP\] | Carpeta que contiene los archivos ASP que conforman [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Carpeta que contiene cinco subcarpetas (Core, CSS, HTC, Images y Output) que contienen archivos de soporte utilizados por [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | Archivo de configuración que se utiliza para definir los directorios virtuales asociados con [!DNL Report Portal] (solo se utiliza con IIS 6.0). |

   El directorio tiene el siguiente ejemplo:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >El nombre del directorio puede diferir del nombre mostrado en el ejemplo.

1. Cambie el nombre de la carpeta VSVirtualPortalName (u otro nombre) a lo que desee utilizar como directorio virtual raíz de su [!DNL Report Portal] (en lo sucesivo denominado *PortalName*). Para obtener más información sobre los directorios virtuales, consulte la siguiente sección.
