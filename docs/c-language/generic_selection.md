---
title: 汎用選択 (C11)
description: Microsoft Visual C コンパイラで使用される C11 の _Generic キーワードについて説明します
ms.date: 12/9/2020
helpviewer_keywords:
- _Generic keyword [C]
ms.openlocfilehash: de0e840c19186219d53800b9d008d7695b807bc1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97348894"
---
# <a name="generic-selection-c11"></a>汎用選択 (C11)

**`_Generic`** キーワードを使用して、コンパイル時に引数の型に基づいて式を選択するコードを記述します。 これは、引数の型によって評価する式が選択される点を除いて、引数の型によって呼び出される関数が選択される、C++ のオーバーローディングに似ています。

たとえば、式 `_Generic(42, int: "integer", char: "character", default: "unknown");` では `42` の型を評価し、リスト内で一致する型 `int` を検索します。 これを検出し、`"integer"` を返します。

## <a name="syntax"></a>構文

*`generic-selection`*:\
&nbsp;&nbsp;&nbsp;&nbsp;**`_Generic`** **(** *`assignment-expression`, `assoc-list`* **)**

*`assoc-list`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`association`*\
&nbsp;&nbsp;&nbsp;&nbsp;*`assoc-list`, `association`*

*`association`*:\
&nbsp;&nbsp;&nbsp;&nbsp;*`type-name`* : *`assignment-expression`*\
&nbsp;&nbsp;&nbsp;&nbsp;**`default`** : *`assignment-expression`*

最初の *`assignment-expression`* は、制御式と呼ばれます。 制御式の型はコンパイル時に決まり、 *`assoc-list`* に対して照合され、評価して返す式を検索します。 制御式は評価されません。 たとえば、`_Generic(intFunc(), int: "integer", default: "error");` では、`intFunc()` の実行時に呼び出しは行われません。 

制御式の型が決まったら、`const`、`volatile`、および `restrict` は *`assoc-list`* と照合される前に削除されます。

選択されていない `assoc-list` のエントリは評価されません。

## <a name="constraints"></a>制約

- *`assoc-list`* では、同じ型を複数回指定することはできません。
- *`assoc-list`* では、列挙型やその列挙型の基になる型など、相互に互換性のある型を指定することはできません。
- 汎用選択に既定値がない場合、制御式の汎用結合リストには、互換性のある型名が 1 つだけ含まれている必要があります。

## <a name="example"></a>例

**`_Generic`** を使用する 1 つの方法は、マクロです。 <tgmath.h> ヘッダー ファイルでは **_Generic** を使用して、引数の型に応じて適切な数値演算関数を呼び出します。 たとえば、`cos()` のマクロでは、float を持つ呼び出しを `cosf()` にマップし、複雑な double を持つ呼び出しを `ccos()` にマップします。

次の例は、渡される引数の型を識別するマクロを記述する方法を示します。 *`assoc-list`* のエントリが制御式に一致しない場合、`"unknown"` が生成されます。

```C
// Compile with /std:c11

#include <stdio.h>

/* Get a type name string for the argument x */
#define TYPE_NAME(X) _Generic((X), \
      int: "int", \
      char: "char", \
      double: "double", \
      default: "unknown")

int main()
{
    printf("Type name: %s\n", TYPE_NAME(42.42));

    // The following would result in a compile error because 
    // 42.4 is a double, doesn't match anything in the list, 
    // and there is no default.
    // _Generic(42.4, int: "integer", char: "character"));
}

/* Output:
Type name: double
*/

```

## <a name="see-also"></a>関連項目

[`/std` (言語の標準バージョンの指定)](../build/reference/std-specify-language-standard-version.md)\
[ジェネリック型数値演算](../c-runtime-library/tgmath.md)