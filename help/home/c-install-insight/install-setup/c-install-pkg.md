---
description: Archivos incluidos en el paquete de instalación de la Data Workbench.
title: Archivos incluidos en el paquete de instalación
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 5%

---

# Archivos incluidos en el paquete de instalación{#files-included-in-the-installation-package}

{{eol}}

Archivos incluidos en el paquete de instalación de la Data Workbench.

Los siguientes directorios están incluidos en el paquete Insight .

## Archivos de programa {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

El ejecutable de Workstation (**[!DNL Insight.exe]**) y los archivos de soporte están instalados de forma predeterminada en esta carpeta.

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
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> El ejecutable del cliente de Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Defina el idioma y la ruta para la variable <span class="filepath"> Appdata </span> carpeta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Ahora, Data Workbench admite un Editor de métodos de entrada (IME) como proceso de entrada de texto secundario que le permite introducir caracteres internacionales desde el teclado mediante un cuadro de texto flotante. Data Workbench admitirá el inglés de forma predeterminada, pero también le permite cargar otros archivos para admitir idiomas internacionales, como un teclado chino virtual (Pinyin IME). </p> <p>Un nuevo archivo de diccionario <span class="filepath"> (Insight.zbin </span>) es necesario para que la aplicación cliente admita el IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Ejecutable para desinstalar la estación de trabajo y eliminar archivos. </td> 
  </tr> 
 </tbody> 
</table>

## Archivos AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

Archivos de datos (**[!DNL Insight.cfg]**, Perfiles, Certificados, registros de seguimiento y archivos de usuario) se guardan de forma predeterminada en:

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
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> El archivo de configuración de la Data Workbench. Define los parámetros dentro de los cuales funciona la Data Workbench. Consulte <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configuración de la conexión con el servidor de Insight </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Contiene los archivos de programa para su Data Workbench. </p> <p> <p>Nota: No debe quitar ni modificar ninguno de estos archivos. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificados </span> </b> </td> 
   <td colname="col2"> Contiene el archivo de certificado, <span class="filepath"> trust_ca_cert.pem </span>y el certificado digital del usuario con nombre para la Data Workbench. Consulte <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Descarga e instalación del certificado digital </a>. </td> 
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
   <td colname="col2"> Asistente de configuración para instalar equipos cliente adicionales en <b> <span class="filepath"> Software/Insight </span></b> carpeta. </td> 
  </tr> 
 </tbody> 
</table>
