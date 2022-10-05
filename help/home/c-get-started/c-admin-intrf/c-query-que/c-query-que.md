---
description: Normalmente, el servidor de Data Workbench responde a las consultas de usuario entrantes a medida que se reciben y continúa proporcionando resultados y actualizaciones en tiempo real hasta que el usuario ya no las solicita.
title: Cola de consultas
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
exl-id: 5d9b20bf-9396-4016-beed-cee8f533f3ea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 0%

---

# Cola de consultas{#query-queue}

{{eol}}

Normalmente, el servidor de Data Workbench responde a las consultas de usuario entrantes a medida que se reciben y continúa proporcionando resultados y actualizaciones en tiempo real hasta que el usuario ya no las solicita.

A veces, especialmente en sistemas con muchos usuarios de Data Workbench, el número de consultas activas requiere más recursos del sistema de los disponibles en el servidor. [!DNL Query Queue] permite al servidor poner algunas consultas temporalmente en espera hasta que los recursos necesarios para proporcionar respuestas estén disponibles. La variable [!DNL Query Queue] también proporciona funciones para priorizar consultas basadas en una variedad de parámetros, de modo que en caso de contención de recursos, las consultas de mayor prioridad se respondan primero.

Las consultas de un solo cliente o servidor de informes se colocan en un grupo y se programan como una unidad. Puede configurar los monitores de recursos para limitar la cantidad de ciertos recursos del sistema que utilizan las consultas. Cuando los recursos supervisados permiten programar otro grupo de consultas, se programa el grupo de mayor prioridad. Los usuarios cuyas consultas aún no están programadas, debido a limitaciones de recursos, no reciben un error pero se les notifica que sus consultas están en cola y que el usuario puede seguir trabajando en el ejemplo local.

La configuración predeterminada incluye una configuración simple para la variable [!DNL Query Queue], pero lo deja deshabilitado. Los administradores pueden habilitar o deshabilitar el [!DNL Query Queue], configure los monitores de recursos para determinar la cantidad de recursos que se utilizan para las consultas y configure políticas complejas de priorización para distintos usuarios.

**Para configurar el archivo Server.cfg para[!DNL Query Queuing]**

1. Apertura [!DNL Server.cfg] haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Clic con el botón derecho **[!UICONTROL Server.cfg]** y haga que sea local para la edición.
1. Expandir [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configure los siguientes parámetros:

   * **Grupos de usuarios:** Permite configurar políticas, usuarios y la prioridad de cola. Consulte [Grupos de usuarios de la cola de consulta](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) para las definiciones.

   * **Activo:** (Vector) Habilita o deshabilita el [!DNL Query Queue]. Los valores válidos son true o false. La configuración predeterminada es false.

   * **Grupo de usuarios predeterminado:** (Cadena) Escriba un nombre del grupo de usuarios al que se agregan los usuarios si no están incluidos en ningún grupo de usuarios.
   * **Monitores de recursos:** (Vector) Haga clic con el botón derecho para añadir un monitor de recursos. Puede especificar si la variable [!DNL Query Queue] supervisa la memoria o el número de consultas. Clic con el botón derecho **[!UICONTROL Resource Monitor]** para elegir Monitor de presupuesto de memoria o Monitor de número de consultas. Consulte [Monitores de recursos de cola de consulta](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) para obtener más información.

   * **Prioridad intocable:** (Int) Especifica que los paquetes con una prioridad buena o igual a este valor nunca tienen preferencia sobre la programación de paquetes de mayor prioridad. Se utiliza junto con la variable [!DNL Memory Budget Monitor] descritos en la sección [Tabla de parámetros de grupo de usuarios](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1).
