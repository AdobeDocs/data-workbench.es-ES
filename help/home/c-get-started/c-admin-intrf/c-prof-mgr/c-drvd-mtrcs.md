---
description: Puede definir nuevas métricas (denominadas métricas derivadas) y editar las definiciones de métricas existentes mediante el Editor de métricas.
solution: Analytics
title: Trabajar con métricas derivadas
topic: Data workbench
uuid: 9767c170-e0cb-47b4-94f1-e9f6950b5926
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Trabajar con métricas derivadas{#work-with-derived-metrics}

Puede definir nuevas métricas (denominadas métricas derivadas) y editar las definiciones de métricas existentes mediante el Editor de métricas.

Para obtener más información sobre las métricas de la que se proporciona en esta sección y en Sintaxis [del idioma de](../../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)consulta, consulte la Guía *de* métricas, dimensiones y filtros.

## Crear una métrica derivada {#section-d57b98bf0a9940daba4920ff7efc808d}

Utilice un [!DNL Metric Editor] para definir una nueva métrica por nombre, fórmula y formato, que se guarda en la carpeta User\*profile_name*\Metrics para su uso posterior.

1. Abra un nuevo [!DNL Metric Editor] utilizando la opción de menú **[!UICONTROL Admin]** > **[!UICONTROL Profile]** o haciendo clic con el botón secundario en la **[!UICONTROL User]** columna de la carpeta en la que desea crear la métrica y haciendo clic en **[!UICONTROL Create]** > **[!UICONTROL New Metric]**.

   Se [!DNL Metric Editor] muestra una.

1. En el parámetro Name, escriba un nombre para la nueva métrica.

   Tenga en cuenta que se permiten espacios ( ) mientras que los caracteres de subrayado (_) no. Además, no puede utilizar los siguientes símbolos:

   `+ - * /`

   ![](assets/vis_MetricEditor_NewAndEditing.png)

1. En el parámetro Fórmula, escriba una expresión para la nueva métrica. Tenga en cuenta que los filtros deben definirse entre corchetes [ ] en la expresión.

   Para obtener más reglas de sintaxis de expresiones de métricas, consulte [Sintaxis para expresiones](../../../../home/c-get-started/c-qry-lang-syntx/c-syntx-mtrc-exp.md#concept-bbf440a0307549e088df491b51b51d66)de métricas.

   La siguiente tabla proporciona expresiones de ejemplo para métricas extendidas.

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
      <td colname="col1"> <p>Valor promedio por visitante </p> </td> 
      <td colname="col2"> <p><span class="filepath"> Valor/Visitantes</span> </p> </td> 
   </tr> 
   </tbody> 
   </table>

   >[!NOTE]
   >
   >Cuando se introduce una expresión adecuada, la línea de vista previa muestra el valor de la nueva métrica. Si hay un error en la expresión, la línea de vista previa muestra un mensaje de error.

1. Haga clic con el botón secundario **[!UICONTROL (New)]** y haga clic en **[!UICONTROL Save]**.

   Al guardar la métrica, se crea en el equipo un archivo que representa la nueva métrica en el directorio de instalación del área de trabajo de datos \User\*nombre de perfil*\Métricas.

   ![](assets/vis_MetricEditor_NewAndEditing.png)

Ahora puede usar la nueva métrica en todo el perfil actual seleccionándola como lo haría con cualquier métrica integrada. Para cambiar el orden en que aparecen las métricas en el menú de métricas, consulte [Personalización de menús con archivos](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

Si desea que todos los usuarios del perfil utilicen la métrica que ha creado, debe publicarla en el perfil de trabajo mediante el [!DNL Profile Manager]. Consulte [Publicación de archivos en el perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabajo.

## Editar una métrica derivada {#section-db6d924cf4e14bcc8d57cfe1059fc797}

1. En la columna [!DNL Profile Manager] o [!DNL Metrics Manager], en la columna *del nombre* del perfil, haga clic con el botón secundario en la marca de verificación del archivo de métrica que desee editar y, a continuación, haga clic en **[!UICONTROL Make Local]**.
1. Haga clic con el botón secundario en la marca de verificación del archivo de métrica en la [!DNL User] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**.

   >[!NOTE]
   >
   >También puede abrir una métrica [!DNL Metric Editor] haciendo clic con el botón secundario en cualquier área relacionada con la métrica dentro de una visualización para mostrar el menú de la métrica. Para obtener más información, consulte [Uso de los menús](../../../../home/c-get-started/c-vis/c-met-dim-menus.md#concept-50f07ae47c3e4f94ad7d3d7f8293ccac)Métrica y Dimensión.

1. En la sección [!DNL Metric Editor], edite y guarde la definición de la métrica según sea necesario mediante los pasos 2 a 4 de [Creación de nuevas métricas](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#section-d57b98bf0a9940daba4920ff7efc808d)derivadas.

   Si desea que todos los usuarios del perfil utilicen la métrica que ha editado, debe publicarla en el perfil de trabajo mediante el [!DNL Profile Manager]. Consulte [Publicación de archivos en el perfil](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)de trabajo.

