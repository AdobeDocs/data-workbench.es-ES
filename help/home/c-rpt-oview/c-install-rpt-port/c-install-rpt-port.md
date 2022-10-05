---
description: Para utilizar el portal de informes, debe instalar y configurar un conjunto de páginas del servidor de aplicaciones (ASP) en IIS.
title: Instalación del portal de informes
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
exl-id: c6f140d4-a4fe-48e2-bbcd-b43efb2387dd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 4%

---

# Instalación del portal de informes{#installing-the-report-portal}

{{eol}}

Para utilizar el portal de informes, debe instalar y configurar un conjunto de páginas del servidor de aplicaciones (ASP) en IIS.

**Antes de empezar**

Los procedimientos de este capítulo describen cómo instalar y configurar [!DNL Report Portal]. Para completar estos procedimientos, debe:

* Tener instalado Microsoft IIS y conocer su versión.
* Conocer los nombres de los conjuntos de informes cuyos informes muestra [!DNL Report Portal].
* Conocer la ubicación del directorio en el que [!DNL Report Server] guarda el resultado de estos conjuntos de informes. Asegúrese de que el servidor de aplicaciones IIS tenga acceso a este directorio.

>[!NOTE]
>
>* Para ver con [!DNL Report Portal], los informes deben seguir convenciones de nomenclatura específicas. Además, el directorio en el que se guardan los informes debe seguir una estructura prescrita. Para obtener una descripción de estos requisitos, consulte [Garantizar que los conjuntos de informes sean compatibles con el portal de informes...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
>
>* Las contraseñas del portal de informes ahora son compatibles con AES-256 bits. Si actualiza a Report Portal 2.0, aumente el campo Tamaño de campo de la contraseña de 50 a 150 en la variable **users.mdb** base de datos. Es necesario aumentar el tamaño del campo para dar cabida a las contraseñas con cifrado actualizado.
>* Si está actualizando a Report Portal 2.0, aumente el tamaño de campo para la variable **Contraseña** campo de 50 a 150 en la base de datos users.mdb. Es necesario aumentar el tamaño del campo para dar cabida a las contraseñas con cifrado actualizado.
>* El portal de informes ahora incluye algoritmos de hash más sólidos con compatibilidad con sales. Si está actualizando a **Portal de informes 2.1**, añada un nuevo campo de texto, *PasswordSalt* con un tamaño de campo de 20 caracteres en [!DNL users.mdb]base de datos. Este campo es necesario para almacenar la sal de contraseña.
>

