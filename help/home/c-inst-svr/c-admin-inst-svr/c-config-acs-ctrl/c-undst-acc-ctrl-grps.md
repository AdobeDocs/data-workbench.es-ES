---
description: Hay cinco grupos de control de acceso pregenerados disponibles, pero puede crear y administrar grupos adicionales según sea necesario.
title: Explicación de los grupos de controles de acceso
uuid: ff783078-6d2f-4a64-ab11-8083e35d765f
exl-id: 35353b0a-7f08-4215-8a2c-ee1e26d9f5db
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 8%

---

# Explicación de los grupos de controles de acceso{#understanding-access-control-groups}

{{eol}}

Hay cinco grupos de control de acceso pregenerados disponibles, pero puede crear y administrar grupos adicionales según sea necesario.

Puede definir los miembros de cada grupo de control de acceso, así como los directorios a los que cada grupo tiene acceso de sólo lectura o de escritura de lectura.

Los grupos predefinidos se definen de la siguiente manera:

| Grupo | Descripción |
|---|---|
| Administradores | Permite acceder a todos los directorios y archivos. La dirección IP predeterminada es 127.0.0.1 (host local). |
| Sensores | Permite acceder únicamente a los archivos utilizados por [!DNL Sensor] para transmitir datos. |
| Usuarios | Permite acceso de solo lectura a los elementos necesarios para un [!DNL Insight] para realizar tareas básicas de análisis. |
| Usuarios avanzados | Permite acceso de solo lectura a los elementos necesarios para un [!DNL Insight] para realizar tareas básicas de análisis, además de acceso de lectura y escritura al [!DNL Profiles] carpeta para modificar perfiles. |
| Servidores de clúster | Permite el acceso a [!DNL Insight Servers] que se designan como servidores de clúster. |
| Servidores de informes | Permite el acceso a [!DNL Report] máquinas que se conectan al [!DNL Insight Server]. |

Los miembros de un grupo de control de acceso se definen utilizando sus direcciones IP o la información de certificado SSL.

Si no hay un certificado SSL disponible, se puede utilizar una dirección IP para definir un miembro del grupo. La instalación típica de [!DNL Insight] incluye un certificado SSL, mientras que el uso de certificados para [!DNL Sensor(s)] es opcional. Para [!DNL Insight Server], los servidores de clúster se definen con direcciones IP en lugar de certificados SSL.

Se pueden utilizar los siguientes códigos para definir los miembros del grupo:

| Código de tipos de acceso | Definición |
|---|---|
| O | Organización |
| CN | Nombre común |
| L | Localidad |
| ST | Estado o provincia |
| C | País |
| OU | Unidad organizativa |
| Correo electrónico | Correo electrónico Dirección |
