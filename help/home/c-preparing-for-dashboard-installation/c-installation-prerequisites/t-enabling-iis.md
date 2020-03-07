---
description: El primer paso es habilitar la función IIS en el servidor de tableros.
solution: Analytics
title: Habilitación de IIS
topic: Data workbench
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Habilitación de IIS{#enabling-iis}

El primer paso es habilitar la función IIS en el servidor de tableros.

1. Debajo **[!UICONTROL Administrative Tools]**, abra el **[!UICONTROL Server Manager]**.
1. Haga clic con el botón derecho en el elemento de menú Funciones en la parte izquierda de la **[!UICONTROL Server Manager]** ventana.
1. Select **[!UICONTROL Add Roles]**.
1. Seleccione **[!UICONTROL Web Server (IIS)]** y continúe con el **[!UICONTROL Add Roles Wizard]**. Asegúrese de que los siguientes servicios de rol están activados:

   | Funciones HTTP comunes |
   |---|
   | Contenido estático |
   | Documento predeterminado |
   | Exploración de directorios |
   | Errores HTTP |
   | Redirección HTTP |

   | Desarrollo de aplicaciones |
   |---|
   | ASP.NET |
   | Extensibilidad de .NET |
   | Extensiones ISAPI |
   | Filtros ISAPI |

   | Salud y diagnóstico |
   |---|
   | Registro HTTP |
   | Herramientas de registro |
   | Monitor de solicitud |
   | Rastreo |
   | Registro personalizado |

   | Seguridad |
   |---|
   | Autenticación básica |
   | Autenticación de Windows |
   | Autenticación de URL |
   | Filtrado de solicitudes |
   | Restricciones de IP y dominio |

   | Herramientas de administración |
   |---|
   | Consola de administración de IIS |
   | Herramientas y script de administración de IIS |
   | Servicio de administración |

1. Siga el asistente para completar la instalación.
