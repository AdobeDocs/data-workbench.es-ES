---
description: Los conjuntos de informes deben configurarse de una manera específica para producir informes que se muestren correctamente a través del portal de informes.
title: Personalización de la interfaz de usuario del portal de informes
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Personalización de la interfaz de usuario del portal de informes{#customize-the-report-portal-user-interface}

Los conjuntos de informes deben configurarse de una manera específica para producir informes que se muestren correctamente a través del portal de informes.

La interfaz de usuario de [!DNL Report Portal] está diseñada para mostrar una pestaña para cada carpeta del conjunto de informes que aparece en el directorio de salida y se muestra en el archivo [!DNL profiles.xml], así como la pestaña [!DNL Admin] integrada, que debe agregarse al archivo [!DNL TopNavigation.xml] que se desea mostrar. Para obtener más información sobre cómo mostrar la ficha [!DNL Admin] integrada, consulte [Vinculación de una carpeta de salida a una ficha en el usuario...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Garantizar que los conjuntos de informes sean compatibles con el portal de informes...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Vincular una carpeta de salida a una ficha en el usuario...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Garantizar que los conjuntos de informes sean compatibles con el portal de informes {#section-2b141e5d198a4bbea455699126c24706}

Un conjunto de informes define un trabajo programado para [!DNL Report]. Consta de dos elementos:

* Carpeta que define la colección de espacios de trabajo que desea que [!DNL Report] genere como informes.
* Un archivo de configuración ( [!DNL Report.cfg]).

Entre otras cosas, el archivo [!DNL Report.cfg] indica a [!DNL Report] cuándo generar los informes y dónde guardar los archivos de salida. Los conjuntos de informes residen en la carpeta Informes del servidor de Data Workbench. Un perfil puede mostrar cualquier número de conjuntos de informes.

Para garantizar la compatibilidad con [!DNL Report Portal], los conjuntos de informes deben cumplir los siguientes requisitos:

* El directorio de salida de los conjuntos de informes debe contener un archivo [!DNL profiles.xml] configurado.
* Cada conjunto de informes debe incluir un informe de nivel superior llamado &quot;*Resumen de ReportSetName*&quot;, donde *ReportSetName* coincide con el nombre del conjunto de informes. Por ejemplo, el siguiente [!DNL Profile Manager] muestra dos conjuntos de informes, &quot;Inicio&quot; y &quot;Tráfico&quot;. Tenga en cuenta que cada conjunto de informes define un informe de resumen ( [!DNL Home Summary.vw] y [!DNL Traffic Summary.vw], respectivamente).

![](assets/rptPort_scrn_RptSets.png)

En [!DNL Report Portal], el informe de resumen aparece en la pestaña del conjunto de informes. El informe de resumen puede contener cualquier espacio de trabajo, ventana o visualización que desee.

* El informe de resumen debe ser el único informe de la carpeta de nivel superior de un conjunto de informes. Todos los demás informes deben colocarse en subcarpetas. Si coloca otros informes en la carpeta de nivel superior, no podrá verlos a través del portal.

## Vinculación de una carpeta de salida a una ficha en la interfaz de usuario {#section-3f6bc47d37ed448e871f4f685f46acee}

Para especificar las pestañas que desea que [!DNL Report Portal] se muestre, debe configurar un archivo [!DNL TopNavigation.xml] para cada perfil. Este archivo determina qué conjuntos de informes aparecen como fichas en la interfaz de usuario para un perfil en particular, así como el orden de esas pestañas. El archivo [!DNL TopNavigation.xml] reside en la carpeta \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Para editar el archivo TopNavigation.xml**

1. En el equipo en el que se está ejecutando IIS, abra el archivo [!DNL TopNavigation.xml] en un editor de texto como el Bloc de notas.
1. Edite la lista de `<TopNav>` elementos para que defina los nombres y el orden de los conjuntos de informes cuya salida desea que se muestre, como en el siguiente ejemplo:[!DNL Report Portal]

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >La pestaña [!DNL Admin] es una pestaña integrada que proporciona funcionalidad adicional. Si no lo incluye en el archivo [!DNL TopNavigation.xml], esta pestaña no se muestra y su funcionalidad no está disponible.

1. En \*PortalName*\PortalFiles\Core\TopNav\ folder, cree una carpeta para el siguiente perfil.
1. Copie el archivo [!DNL TopNavigation.xml] de la primera carpeta de perfiles y péguelo en la nueva carpeta.
1. Edite el [!DNL TopNavigation.xml] según sea necesario y guarde el archivo.
1. Repita los pasos del 3 al 5 para todos los demás perfiles disponibles en el portal.
