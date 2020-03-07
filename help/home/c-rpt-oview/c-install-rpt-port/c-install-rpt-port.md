---
description: Para utilizar el portal de informes, debe instalar y configurar un conjunto de páginas de servidor de aplicaciones (ASP) en IIS.
solution: Analytics
title: Instalación del portal de informes
topic: Data workbench
uuid: 6aeb6038-b0b0-48b9-a020-bc9dfd703c43
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación del portal de informes{#installing-the-report-portal}

Para utilizar el portal de informes, debe instalar y configurar un conjunto de páginas de servidor de aplicaciones (ASP) en IIS.

**Antes de empezar**

Los procedimientos de este capítulo describen cómo instalar y configurar [!DNL Report Portal]. Para completar estos procedimientos, debe:

* Tener instalado Microsoft IIS y conocer su versión.
* Conocer los nombres de los conjuntos de informes cuyos informes se muestran por [!DNL Report Portal].
* Conocer la ubicación del directorio en el que [!DNL Report Server] se guarda el resultado de estos conjuntos de informes. Asegúrese de que el servidor de aplicaciones IIS tiene acceso a este directorio.

>[!NOTE]
>
>* Para que se puedan ver con [!DNL Report Portal]ellos, los informes deben seguir convenciones de nombres específicas. Además, el directorio en el que se guardan los informes debe seguir una estructura prescrita. Para obtener una descripción de estos requisitos, consulte [Garantizar que los conjuntos de informes sean compatibles con el portal de informes...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706).
   >
   >
* Las contraseñas del portal de informes ahora son compatibles con AES-256 bits. Si actualiza a Report Portal 2.0, aumente el campo Tamaño de campo de la contraseña de 50 a 150 en la base de datos **users.mdb** . Se requiere aumentar el tamaño del campo para dar cabida a las contraseñas con cifrado actualizado.
>* Si está actualizando a Report Portal 2.0, aumente el tamaño de campo del campo **Contraseña** de 50 a 150 en la base de datos users.mdb. Se requiere aumentar el tamaño del campo para dar cabida a las contraseñas con cifrado actualizado.
>* El portal de informes ahora cuenta con algoritmos de hash más sólidos con compatibilidad con sales. Si está actualizando a **Report Portal 2.1**, agregue un nuevo campo de texto, *PasswordSalt* con un tamaño de campo de 20 caracteres en la [!DNL users.mdb]base de datos. Este campo es necesario para almacenar la contraseña.
>



