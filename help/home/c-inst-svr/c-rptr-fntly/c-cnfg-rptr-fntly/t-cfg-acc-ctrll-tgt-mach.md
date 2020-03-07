---
description: Los equipos de Target Insight Server que ejecutan el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.
solution: Insight
title: Configuración del control de acceso para equipos de destino
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del control de acceso para equipos de destino{#configuring-access-control-for-target-machines}

Los equipos de Target Insight Server que ejecutan el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.

El acceso a los equipos de destino se concede mediante el [!DNL Access Control.cfg] archivo.

**Para configurar el control de acceso para el acceso por parte de los[!DNL Insight Server]equipos de destino**

1. Vaya a la [!DNL Access Control] carpeta del directorio donde instaló la funcionalidad repetidor.

   Ejemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] en un editor de texto como Bloc de notas.
1. Cree un grupo de acceso para los [!DNL Insight Server] equipos que deben acceder a los archivos de registro de este servidor repetidor. Asigne a este grupo de acceso un nombre similar a &quot;Objetivos de replicación&quot;.

       El siguiente fragmento de archivo muestra cómo debe verse el grupo de acceso.
       
       ```
       . . .
       6 = AccessGroup:
       Miembros = vector: N elementos
     0 = cadena: IP:Machine0IPAddress
     1 = cadena: IP:Machine1IPAddress
     . . .
       N = cadena: IP:MachineNIPAddress
     Name = cadena: Acceso de sólo
 lectura a los objetivos     de replicación = vector: 1 items
     0 = string: Acceso de escritura de
 lectura a EventDataLocation     = vector: 0 elementos
    . . .
       &quot;
   
   1. En la sección Miembros, especifique la dirección IP de cada equipo.
   1. Actualice el recuento de elementos del vector Miembros para reflejar el número de direcciones IP de equipo que ha insertado.
   1. En la sección Acceso de sólo lectura, especifique la ubicación de los datos del evento a los que tienen acceso los destinos de replicación. Utilice barras diagonales en la especificación de ruta (/). La ubicación predeterminada es la [!DNL Logs] carpeta del equipo Repetidor (/Logs/).
   1. Actualice el recuento de elementos para el vector de acceso de solo lectura para reflejar el número de ubicaciones insertadas.

1. Actualice el número de grupos de acceso en el vector Grupos de control de acceso en la parte superior del archivo para reflejar la adición del nuevo grupo de acceso.

   ```
   Access Control Groups = vector: n items
   ```

1. Guarde el archivo.
