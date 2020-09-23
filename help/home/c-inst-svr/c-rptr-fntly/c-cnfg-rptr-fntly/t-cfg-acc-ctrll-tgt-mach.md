---
description: Los equipos destinatario Insight Server que ejecutan el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.
solution: Analytics
title: Configuración del control de acceso para equipos de destino
uuid: 35e032cf-6c1d-4348-88ce-4f4a6a30b16f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 6%

---


# Configuración del control de acceso para equipos de destino{#configuring-access-control-for-target-machines}

Los equipos destinatario Insight Server que ejecutan el servicio de replicación de Insight Server deben poder leer los archivos de registro en este servidor repetidor.

El acceso a los equipos de destinatario se concede mediante el [!DNL Access Control.cfg] archivo.

**Para configurar el Control de acceso de acceso mediante máquinas de destinatario[!DNL Insight Server]**

1. Vaya a la [!DNL Access Control] carpeta del directorio donde instaló la funcionalidad repetidor.

   Ejemplo: [!DNL D:\Adobe\Repeater\Access Control]

1. Abra [!DNL Access Control.cfg] en un editor de texto como Bloc de notas.
1. Cree un grupo de acceso para los [!DNL Insight Server] equipos que deben acceder a los archivos de registro de este servidor repetidor. Asigne a este grupo de acceso un nombre como &quot;Destinatarios de replicación&quot;.

   El siguiente fragmento de archivo muestra cómo debe verse el grupo de acceso.

   ```
   . . . 
     6 = AccessGroup: 
       Members = vector: N items 
         0 = string: IP:Machine0IPAddress 
         1 = string: IP:Machine1IPAddress 
   . . . 
         N = string: IP:MachineNIPAddress 
       Name = string: Replication Targets 
       Read-Only Access = vector: 1 items 
         0 = string: EventDataLocation 
       Read-Write Access = vector: 0 items 
   . . .
   ```

   1. En la sección Miembros, especifique la dirección IP de cada equipo.
   1. Actualice el recuento de elementos del vector Miembros para reflejar el número de direcciones IP de equipo que ha insertado.
   1. En la sección Acceso de sólo lectura, especifique la ubicación de los datos de evento a los que acceden los destinatarios de replicación. Utilice barras diagonales en la especificación de ruta (/). La ubicación predeterminada es la [!DNL Logs] carpeta del equipo Repetidor (/Logs/).
   1. Actualice el recuento de elementos para el vector de acceso de solo lectura para reflejar el número de ubicaciones insertadas.

1. Actualice el número de grupos de acceso en el vector Grupos de Controles de acceso en la parte superior del archivo para reflejar la adición del nuevo grupo de acceso.

   ```
   Access Control Groups = vector: n items
   ```

1. Guarde el archivo.
