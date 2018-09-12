---
title: C 型指定子 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- type specifiers, C
- specifiers, type
ms.assetid: fbe13441-04c3-4829-b047-06d374adc2b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f965481ae1d3abea40577680b1af72004f793123
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197229"
---
# <a name="c-type-specifiers"></a>C 型指定子

宣言内の型指定子は、変数または関数宣言の型を定義します。

## <a name="syntax"></a>構文

*type-specifier*:  
&nbsp;&nbsp;**void**  
&nbsp;&nbsp;**char**  
&nbsp;&nbsp;**short**  
&nbsp;&nbsp;**int**  
&nbsp;&nbsp;**long**  
&nbsp;&nbsp;**float**  
&nbsp;&nbsp;**double**  
&nbsp;&nbsp;**signed**  
&nbsp;&nbsp;**unsigned**  
&nbsp;&nbsp;*struct-or-union-specifier*  
&nbsp;&nbsp;*enum-specifier*  
&nbsp;&nbsp;*typedef-name*  

**signed char**、**signed int**、**signed short int**、および **signed long int** 型と、それに対応する **unsigned** 型および **enum** は、"*整数*" 型と呼ばれます。 **float**、**double**、および **long double** 型指定子は、"*浮動*" 型または "*浮動小数点*" 型と呼ばれます。 変数宣言または関数宣言で、整数型または浮動小数点型の指定子を使用できます。 *type-specifier* が宣言で指定されていない場合、**int** として処理されます。

省略可能なキーワード **signed** と **unsigned** は、**enum** 以外の整数型の前または後に置くことができ、型指定子として単独で使用することもできます。この場合、これらは、それぞれ **signed int** と **unsigned int** として解釈されます。 単独で使用した場合、**int** キーワードは **signed** であると見なされます。 単独で使用した場合、**long** キーワードおよび **short** キーワードは **long int** および **short int** であると見なされます。

列挙型は基本的な型と見なされます。 列挙型の型指定子については、[列挙型の宣言](../c-language/c-enumeration-declarations.md)に関するページで説明します。

キーワード **void** には 3 つの使用方法があります。関数の戻り値の型を指定する、引数を取らない関数の引数型リストを指定する、指定されていない型へのポインターを指定する、です。 **void** 型を使用して、値を返さない関数を宣言するか、未指定の型へのポインターを宣言することができます。 関数名に続くかっこ内に **void** が単独で表示される状況については、「[引数](../c-language/arguments.md)」をご覧ください。

**Microsoft 固有の仕様**

型チェックが ANSI に準拠するようになりました。つまり、**short** 型と **int** 型は別の型になります。 たとえば、これは以前のバージョンのコンパイラでは使用できた Microsoft C コンパイラの再定義です。

```C
int   myfunc();
short myfunc();
```

次の例も、異なる型への間接参照に関する警告を生成します。

```C
int *pi;
short *ps;

ps = pi;  /* Now generates warning */
```

Microsoft C コンパイラも、符号の違いに対して警告を生成します。 例:

```C
signed int *pi;
unsigned int *pu

pi = pu;  /* Now generates warning */
```

**void** 型の式の副作用が評価されます。 型が **void** の式の (存在しない) 値は使用できません。また、**void** 式を、**void** 以外の型に (暗黙または明示的な変換で) 変換することもできません。 **void** 式が必要なコンテキストでその他の型の式を使用している場合、その値は破棄されます。

ANSI 仕様に準拠するには、<strong>void\*\*</strong> は <strong>int\*\*</strong> として使用できません。 指定されていない型へのポインターとして使用できるのは、**void**<strong>\*</strong> だけです。

**Microsoft 固有の仕様はここまで**

「[typedef 宣言](../c-language/typedef-declarations.md)」に説明されているように、**typedef** 宣言で追加の型指定子を作成できます。 各型のサイズについては、「[基本型の格納](../c-language/storage-of-basic-types.md)」をご覧ください。

## <a name="see-also"></a>関連項目

[宣言と型](../c-language/declarations-and-types.md)  
