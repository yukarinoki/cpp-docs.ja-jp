---
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: db246cda79c778f37c5afbfda4a68c191c474e12
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190496"
---
# <a name="bool-c"></a>bool (C++)

このキーワードは組み込みの型です。 この型の変数には、 [true](../cpp/true-cpp.md)と[false](../cpp/false-cpp.md)の値を指定できます。 条件式の型は**bool**であるため、 **bool**型の値を持つことになります。 たとえば、`i!=0` は `i`の値に応じて TRUE または FALSE になります。

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): 後置または前置インクリメントまたはデクリメント演算子のオペランドを**bool**型にすることはできません。 言い換えると、**ブール**型の変数 `b` した場合、次の式は使用できなくなります。

```cpp
    b++;
    ++b;
    b--;
    --b;
```

値 TRUE と FALSE には、次のリレーションシップがあります。

```cpp
!false == true
!true == false
```

次のステートメントがあるとします。

```cpp
if (condexpr1) statement1;
```

`condexpr1` が TRUE の場合、`statement1` は常に実行されます。`condexpr1` が FALSE の場合、`statement1` は実行されません。

後置または前置 **++** 演算子が**bool**型の変数に適用されると、変数は TRUE に設定されます。
**Visual Studio 2017 バージョン15.3 以降**:**ブール**値の operator + + は言語から削除されたため、サポートされなくなりました。

後置または前置 **--** 演算子は、この型の変数には適用できません。

**Bool**型は、整数の上位変換に関与します。 **Bool**型の右辺値は**int**型の r 値に変換できますが、FALSE はゼロになり、TRUE は1になります。 別個の型として、 **bool**はオーバーロードの解決に関与します。

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)<br/>
[組み込みの型](../cpp/fundamental-types-cpp.md)
