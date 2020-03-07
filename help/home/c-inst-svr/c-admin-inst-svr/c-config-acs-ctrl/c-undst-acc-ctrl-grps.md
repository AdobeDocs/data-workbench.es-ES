---
description: Hay disponibles cinco grupos de control de acceso pregenerados, pero puede crear y administrar grupos adicionales según sea necesario.
solution: Insight
title: Explicación de los grupos de control de acceso
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Explicación de los grupos de control de acceso{#understanding-access-control-groups}

Hay disponibles cinco grupos de control de acceso pregenerados, pero puede crear y administrar grupos adicionales según sea necesario.

Puede definir los miembros de cada grupo de control de acceso, así como los directorios a los que cada grupo tiene acceso de sólo lectura o de escritura de lectura.

Los grupos predefinidos se definen de la siguiente manera:

| Grupo | Descripción |
|---|---|
| Administradores | Permite el acceso a todos los directorios y archivos. La dirección IP predeterminada es 127.0.0.1 (host local). |
| Sensores | Permite el acceso sólo a los archivos utilizados por [!DNL Sensor] la transmisión de datos. |
| Usuarios | Permite el acceso de solo lectura a los elementos necesarios para que un [!DNL Insight] usuario realice tareas básicas de análisis. |
| Usuarios avanzados | Permite el acceso de solo lectura a los elementos necesarios para que un [!DNL Insight] usuario realice tareas básicas de análisis, además de acceso de lectura y escritura a la [!DNL Profiles] carpeta para modificar perfiles. |
| Servidores de clúster | Permite el acceso a [!DNL Insight Servers] los servidores de clúster designados. |
| Servidores de informes | Permite el acceso a [!DNL Report] los equipos que se conectan al [!DNL Insight Server]. |

Los miembros de un grupo de control de acceso se definen mediante sus direcciones IP o información de certificado SSL.

Si no hay un certificado SSL disponible, se puede utilizar una dirección IP para definir un miembro del grupo. La instalación típica de [!DNL Insight] incluye un certificado SSL, mientras que el uso de certificados para [!DNL Sensor(s)] es opcional. Por ejemplo, [!DNL Insight Server]los servidores de clúster se definen con direcciones IP en lugar de certificados SSL.

Se pueden utilizar los siguientes códigos para definir los miembros del grupo:

| Código de tipos de acceso | Definición |
|---|---|
| O | Organización |
| CN | Nombre común |
| L | Localidad |
| ST | Estado o provincia |
| C | País |
| OU | Unidad organizativa |
| Correo electrónico | La dirección de correo electrónico |

