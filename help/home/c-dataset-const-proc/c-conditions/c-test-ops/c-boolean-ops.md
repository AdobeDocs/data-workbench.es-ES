---
description: Las operaciones booleanas combinan los resultados de las operaciones de prueba, que funcionan como elementos secundarios de las operaciones booleanas.
solution: Analytics
title: Operaciones booleanas
topic: Data workbench
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Operaciones booleanas{#boolean-operations}

Las operaciones booleanas combinan los resultados de las operaciones de prueba, que funcionan como elementos secundarios de las operaciones booleanas.

Para obtener información sobre las operaciones de prueba, consulte Operaciones [de prueba](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Cuando define una [!DNL boolean] operación, puede definir cero o más elementos secundarios para la operación.

**Adición de una condición secundaria a una operación booleana**

1. Haga clic con el botón secundario en el nombre o el número correspondiente a la [!DNL Boolean] operación.
1. Haga clic en **[!UICONTROL Add new child]** y elija uno de los tipos de condición disponibles para agregar.
1. Repita los pasos 1 y 2 hasta que haya agregado todas las condiciones secundarias deseadas para la [!DNL Boolean] operación.

   >[!NOTE]
   >
   >Al hacer clic con el botón derecho en el nombre o el número correspondiente a una [!DNL Boolean] operación, se muestra la opción de [!DNL Add new sibling] menú. Un elemento secundario es otra condición en la misma posición relativa en la jerarquía de condiciones que la operación en la que se hizo clic con el botón secundario del mouse (ratón) [!DNL Boolean] . Agregar un nuevo elemento secundario para una operación [!DNL Boolean] es lo mismo que agregar una nueva condición haciendo clic con el botón derecho en el parámetro [!DNL Condition] o [!DNL Log Entry Condition] .

**Para quitar una condición secundaria de una operación booleana:**

1. Haga clic con el botón secundario en el nombre de la condición secundaria o en el número correspondiente a la condición secundaria que desea quitar de la [!DNL Boolean] operación.
1. Haga clic en **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, donde número es el número correspondiente a la condición secundaria que desea eliminar.

Esta sección analiza las siguientes condiciones:

* [Y](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Ni](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [O](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## Y {#section-a14dba4b07cc4ab9aeb20868f773db7c}

La [!DNL And] condición puede tener cero o más condiciones secundarias y devuelve true cuando ninguno de sus nodos secundarios devuelve false.

La [!DNL And] condición forma la operación raíz de todas las pruebas de condición dentro del servidor del área de trabajo de datos. Si la [!DNL And] condición no contiene elementos secundarios, la condición se evalúa como verdadera y la operación asociada continúa. Por este motivo, las acciones que solo tienen la condición [!DNL And] ya que la prueba de condición siempre se ejecuta y por qué se utiliza como raíz para todas las pruebas de condición.

Este ejemplo muestra cómo se utiliza una [!DNL And] condición para asegurarse de que la [!DNL Copy] transformación se produce cuando sólo la fecha de entrada de registro se produjo en el año 2006 y la página solicitada se [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Neither {#section-7e48b61266aa43ecbc48b979bf5e939b}

La [!DNL Neither] condición puede tener cero o más condiciones secundarias y devuelve false si alguna de sus condiciones secundarias se evalúa como verdadera. Si la [!DNL Neither] condición no contiene elementos secundarios, ninguno de los elementos secundarios puede devolver el valor true. Como resultado, la condición [!DNL Neither] se evalúa como verdadera.

El siguiente ejemplo muestra una [!DNL Neither] condición con dos [!DNL Range] condiciones como elementos secundarios. Según se define, la condición excluye las entradas de registro que se produjeron entre el 1 de enero de 2007 y el 10 de enero de 2007 o durante el período comprendido entre el 12 de enero de 2007 y el 14 de enero de 2007. [!DNL Neither] Tal condición podría utilizarse como [!DNL Log Entry Condition] para eliminar transacciones de un conjunto de datos durante períodos en los que se conociera un problema con los datos recopilados.

![](assets/cfg_Condition_NeitherCondition.png)

## O {#section-a3aa0f56b6234f2680fa81939228326b}

La [!DNL Or] condición puede tener cero o más condiciones secundarias y devuelve verdadero si al menos una de sus condiciones secundarias se evalúa como verdadera. Si la [!DNL Or] condición no contiene elementos secundarios, ninguno de los elementos secundarios puede devolver el valor true. Como resultado, la condición [!DNL Or] se evalúa como falsa.

Este ejemplo muestra la [!DNL Or] condición con una [!DNL String Match] condición y una [!DNL Range] condición como sus elementos secundarios. La condición solo se cumple [!DNL Or] si la entrada de registro tiene el [!DNL x-hasproblem] valor establecido en yes o si la entrada de registro se produjo durante el intervalo de tiempo comprendido entre el 1 de enero de 2007 y el 10 de enero de 2007.

![](assets/cfg_Condition_OrCondition.png)

