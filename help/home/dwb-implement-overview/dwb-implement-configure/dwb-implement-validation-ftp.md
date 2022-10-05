---
description: Esta es una guía rápida que le proporciona los pasos mínimos necesarios para validar la configuración de FTP interno y externo.
title: Validación de servidores FTP internos y externos
uuid: bc381c1d-df27-4009-920b-1a804b36c204
exl-id: 8eecfda7-ffa0-458c-a518-434758344bfe
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 9%

---

# Validación de servidores FTP internos y externos{#validation-of-internal-and-external-ftp-servers}

{{eol}}

Esta es una guía rápida que le proporciona los pasos mínimos necesarios para validar la configuración de FTP interno y externo.

Un FTP interno se utiliza cuando un consultor o arquitecto interno de un Adobe tiene que conectarse al sitio FTP para la carga o descarga de archivos, mientras que un FTP externo es principalmente para usted como usuario para cargar los archivos de datos necesarios.

Para obtener información adicional sobre la configuración de servidores FTP, consulte [Protocolo de transferencia de archivos](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/ftp-overview.html?lang=es).

## Pasos de validación: FTP externo {#section-24428111b5c542ce81a765cd63424b97}

1. Abra un símbolo del sistema. (Windows+R y tipo cmd)
1. Tipo ftp `<ftp server>`
1. Proporcione un nombre de usuario y una contraseña. ![](assets/dwb_impl_ftp1.png)

1. Cambie el directorio local desde donde se puede mover algún archivo. Utilice este comando:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

directorio local ahora [!DNL C:\Users\andixit\Desktop].

1. Copie el archivo de la ubicación local a remota. ![](assets/dwb_impl_ftp2.png)

1. Cierre la sesión desde el servidor remoto. (Utilice el comando siguiente)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Otra forma de validar FTP es usando Filezilla. Proporcione Nombre de host, Nombre de usuario, Contraseña y Puerto. El lado derecho del panel es un sitio remoto y el lado izquierdo es un sitio local. Para validar el FTP, arrastre y suelte archivos de sitio local a sitio remoto y v.v.

![](assets/dwb_impl_ftp3.png)

## Pasos de validación: FTP interno {#section-b1f7a789ad6848cf9027f7953d81066e}

Los pasos anteriores se pueden seguir para validar el ftp interno desde cualquier servidor de Adobe.
