---
description: Puede definir nuevas métricas (denominadas métricas derivadas) y editar las definiciones de métricas existentes mediante el Editor de métricas.
title: Trabajo con métricas derivadas
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
exl-id: 83467c64-4b9a-44ab-91a2-202c76c89979
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Trabajo con métricas derivadas{#work-with-derived-metrics}

Puede definir nuevas métricas (denominadas métricas derivadas) y editar las definiciones de métricas existentes mediante el Editor de métricas.

Para obtener más información sobre las métricas de la que se proporciona en esta sección y en [Sintaxis del idioma de consulta](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f), consulte la *Guía de métricas, Dimension y filtros*.

## Crear una métrica derivada {#section-d57b98bf0a9940daba4920ff7efc808d}

Utilice [!DNL Metric Editor] para definir una nueva métrica por nombre, fórmula y formato, que se guarda en la carpeta User\*profile_name*\Metrics para su uso posterior.

1. Abra una nueva [!DNL Metric Editor] utilizando la opción de menú **[!UICONTROL Admin]** > **[!UICONTROL Profile]** o haciendo clic con el botón derecho en la columna **[!UICONTROL User]** de la carpeta en la que desea crear la métrica y haciendo clic en **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Aparece un [!DNL Metric Editor].

1. En el parámetro Nombre , escriba un nombre para la nueva métrica.

   Tenga en cuenta que los espacios ( ) están permitidos mientras que los guiones bajos (_) no lo están. Además, no puede utilizar los siguientes símbolos:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. En el parámetro Formula , escriba una expresión para la nueva métrica. Tenga en cuenta que los filtros deben definirse entre corchetes [ ] en la expresión.

   Para obtener más reglas de sintaxis de expresiones de métricas, consulte [Sintaxis para expresiones de métricas](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66).

   La tabla siguiente proporciona expresiones de ejemplo para métricas extendidas.

   <table id="table_ED77997FC08F492490DCAC3C4153781C"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Nombre de métrica extendido </th> 
      <th colname="col2" class="entry"> Expresión </th> 
   </tr>
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> <p>Porcentaje de primeras sesiones </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Sesiones [Session_Number="1"]/Sesiones</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Primeras sesiones de conversión </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Conversión [Session_Number="1"]</span> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> <p>Valor Promedio Por Visitante </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Valor/Visitantes</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Cuando se introduce una expresión adecuada, la línea de vista previa muestra el valor de la nueva métrica. Si hay un error en la expresión, la línea de vista previa muestra un mensaje de error.

1. Haga clic con el botón derecho en **[!UICONTROL (New)]** y haga clic en **[!UICONTROL Save]**.

   Al guardar la métrica, se crea en el equipo un archivo que representa la nueva métrica en el directorio de instalación de la Data Workbench \User\*nombre de perfil*\carpeta de métricas.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Ahora puede usar la nueva métrica en todo el perfil actual seleccionándola como lo haría con cualquier métrica integrada. Para cambiar el orden en que aparecen las métricas en el menú de métricas, consulte [Personalización de menús mediante archivos Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

Si desea que todos los usuarios del perfil utilicen la métrica que ha creado, debe publicarla en el perfil de trabajo mediante [!DNL Profile Manager]. Consulte [Publicación de archivos en su perfil de trabajo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).

## Editar métricas derivadas {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. En [!DNL Profile Manager] o [!DNL Metrics Manager], en la columna *nombre del perfil*, haga clic con el botón secundario en la marca de verificación del archivo de métrica que desea editar y, a continuación, haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón derecho en la marca de verificación del archivo de métrica en la columna [!DNL User] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >También puede abrir un [!DNL Metric Editor] haciendo clic con el botón derecho en cualquier área relacionada con métricas dentro de una visualización para mostrar el menú de métricas. Para obtener más información, consulte [Uso de menús de métricas y Dimension](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac).

1. En [!DNL Metric Editor], edite y guarde la definición de la métrica según sea necesario mediante los pasos 2 a 4 de [Creación de nuevas métricas derivadas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d).

   Si desea que todos los usuarios del perfil utilicen la métrica que ha editado, debe publicarla en el perfil de trabajo mediante [!DNL Profile Manager]. Consulte [Publicación de archivos en su perfil de trabajo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
