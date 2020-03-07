---
description: Esta es una guía rápida que le proporciona los pasos mínimos necesarios para validar la configuración de FTP interno y externo.
title: Validación de servidores FTP internos y externos
uuid: bc381c1d-df27-4009-920b-1a804b36c204
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Validación de servidores FTP internos y externos{#validation-of-internal-and-external-ftp-servers}

Esta es una guía rápida que le proporciona los pasos mínimos necesarios para validar la configuración de FTP interno y externo.

Un FTP interno se utiliza cuando un consultor o arquitecto interno de Adobe tiene que conectarse al sitio FTP para la carga o descarga de archivos, mientras que un FTP externo es principalmente para que el usuario cargue los archivos de datos necesarios.

Para obtener información adicional sobre la configuración de servidores FTP, consulte Protocolo [de transferencia de archivos](https://docs.adobe.com/content/help/en/analytics/export/ftp-and-sftp/ftp-overview.html).

## Pasos de validación: FTP externo {#section-24428111b5c542ce81a765cd63424b97}

1. Abra un símbolo del sistema. (Windows+R y tipo cmd)
1. Type ftp `<ftp server>`
1. Proporcione el nombre de usuario y la contraseña. ![](assets/dwb_impl_ftp1.png)

1. Cambie el directorio local desde el que se puede mover algún archivo. Utilice este comando:

[!DNL ftp> lcd C:\Users\andixit\Desktop]

directorio local ahora [!DNL C:\Users\andixit\Desktop].

1. Copie el archivo de la ubicación local a la remota. ![](assets/dwb_impl_ftp2.png)

1. Cerrar sesión en el servidor remoto. (Utilice el comando siguiente)

[!DNL ftp> bye]

[!DNL 221 Goodbye]

>[!NOTE]
>
>Otra forma de validar FTP es mediante Filezilla. Proporcione nombre de host, nombre de usuario, contraseña y puerto. El lado derecho del panel es un sitio remoto y el lado izquierdo es un sitio local. Para validar archivos de arrastrar y soltar mediante FTP desde sitios locales a sitios remotos y v.v.

![](assets/dwb_impl_ftp3.png)

## Pasos de validación: FTP interno {#section-b1f7a789ad6848cf9027f7953d81066e}

Los pasos anteriores se pueden seguir para validar ftp interna desde cualquier servidor de Adobe.
