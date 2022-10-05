---
description: El primer paso es habilitar el rol IIS en el servidor de tableros.
title: Habilitación de IIS
uuid: fbd194db-3307-41ae-8ece-05eb261d74ad
exl-id: 0d431302-1e69-49b6-8757-9823fd70a3b4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 4%

---

# Habilitación de IIS{#enabling-iis}

{{eol}}

El primer paso es habilitar el rol IIS en el servidor de tableros.

1. En **[!UICONTROL Administrative Tools]**, abra el **[!UICONTROL Server Manager]**.
1. Haga clic con el botón derecho en el elemento de menú Funciones de la parte izquierda del **[!UICONTROL Server Manager]** ventana.
1. Seleccione **[!UICONTROL Add Roles]**.
1. Select **[!UICONTROL Web Server (IIS)]** y continúe con el **[!UICONTROL Add Roles Wizard]**. Asegúrese de que los siguientes Servicios de rol estén habilitados:

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
   | Seguimiento |
   | Registro personalizado |

   | Seguridad |
   |---|
   | Autenticación básica |
   | Autenticación de Windows |
   | Autenticación URL |
   | Filtrado de solicitudes |
   | Restricciones de IP y dominio |

   | Herramientas de administración |
   |---|
   | Consola de administración de IIS |
   | Herramientas y script de administración de IIS |
   | Servicio de administración |

1. Siga el asistente para completar la instalación.
