---
description: Archivos incluidos en el paquete de instalación de Área de trabajo de datos.
title: Archivos incluidos en el paquete de instalación
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Archivos incluidos en el paquete de instalación{#files-included-in-the-installation-package}

Archivos incluidos en el paquete de instalación de Área de trabajo de datos.

Los siguientes directorios se incluyen en el paquete de Insight.

## Archivos de programa {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

El ejecutable (**[!DNL Insight.exe]**) de Workstation y los archivos de soporte se instalan de forma predeterminada en esta carpeta.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directorio </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span></b> </td> 
   <td colname="col2"> El ejecutable del cliente de Área de trabajo de datos. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span></b> </td> 
   <td colname="col2"> Defina el idioma y la ruta de la <span class="filepath"> carpeta Appdata </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span></b> </td> 
   <td colname="col2"> <p>El área de trabajo de datos ahora admite un Editor de métodos de entrada (IME) como proceso de entrada de texto secundario que permite introducir caracteres internacionales desde el teclado mediante un cuadro de texto flotante. El área de trabajo de datos admitirá el inglés de forma predeterminada, pero también le permite cargar otros archivos para admitir idiomas internacionales, como un teclado chino virtual (Pinyin IME). </p> <p>La aplicación cliente necesita un nuevo archivo de diccionario <span class="filepath"> (Insight.zbin </span>) para admitir el IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Ejecutable para desinstalar Workstation y eliminar archivos. </td> 
  </tr> 
 </tbody> 
</table>

## Archivos AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Los archivos de datos (**[!DNL Insight.cfg]**, perfiles, certificados, registros de seguimiento y archivos de usuario) se guardan de forma predeterminada en:

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directorio </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span></b> </td> 
   <td colname="col2"> El archivo de configuración de Área de trabajo de datos. Define los parámetros dentro de los cuales funciona el área de trabajo de datos. Consulte <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuración de la conexión con Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span></b> </td> 
   <td colname="col2"> <p>Contiene los archivos de programa para Área de trabajo de datos. </p> <p> <p>Nota:  No debe eliminar ni alterar ninguno de estos archivos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificados </span></b> </td> 
   <td colname="col2"> Contiene el archivo de certificado, <span class="filepath"> trust_ca_cert.pem </span>, y el certificado digital de usuario con nombre para Área de trabajo de datos. Consulte <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Descarga e instalación del certificado digital </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Configuración </span> </b> </td> 
   <td colname="col2"> Contiene los archivos que se utilizan para la configuración de Workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Geografía </span></b> </td> 
   <td colname="col2"> Archivos para la representación gráfica de visualizaciones geográficas. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Seguimiento </span></b> </td> 
   <td colname="col2"> Archivos de registro generados desde la estación de trabajo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Perfiles </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Predictive Analytics</i> y otros archivos de configuración de perfil. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Asistente de configuración para instalar equipos cliente adicionales en la <b> carpeta Software/ <span class="filepath"> Insight </span></b> . </td> 
  </tr> 
 </tbody> 
</table>

