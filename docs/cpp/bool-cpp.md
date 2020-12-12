---
description: '詳細情報: bool (C++)'
title: bool (C++)
ms.date: 11/04/2016
f1_keywords:
- bool_cpp
- __BOOL_DEFINED
helpviewer_keywords:
- bool keyword [C++]
- __BOOL_DEFINED macro
ms.assetid: 9abed3f2-d21c-4eb4-97c5-716342e613d8
ms.openlocfilehash: ea3af17260f21d3724f05b8bbad54091b23203e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229588"
---
# <a name="bool-c"></a>bool (C++)

このキーワードは組み込みの型です。 この型の変数は、値およびを持つことができ [`true`](../cpp/true-cpp.md) [`false`](../cpp/false-cpp.md) ます。 条件式の型は **`bool`** であるため、型の値を持ち **`bool`** ます。 たとえば、に `i != 0` は、 **`true`** **`false`** の値に応じてまたはが含まれるようになりました `i` 。

**Visual Studio 2017 バージョン15.3 以降** ( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): 後置または前置インクリメントまたはデクリメント演算子のオペランドを型にすることはできません **`bool`** 。 つまり、型の変数を指定すると、次の `b` **`bool`** 式は使用できなくなります。

```cpp
    b++;
    ++b;
    b--;
    --b;
```

およびの値には、 **`true`** **`false`** 次のリレーションシップがあります。

```cpp
!false == true
!true == false
```

次のステートメントがあるとします。

```cpp
if (condexpr1) statement1;
```

がの場合 `condexpr1` **`true`** 、 `statement1` は常に実行されます。 `condexpr1` がの場合 **`false`** 、 `statement1` は実行されません。

後置または前置 **`++`** 演算子が型の変数に適用されると **`bool`** 、変数はに設定され **`true`** ます。

**Visual Studio 2017 バージョン15.3 以降**: のは言語から削除され、サポートされ `operator++` なくなり **`bool`** ました。

後置または前置演算子は、 **`--`** この型の変数には適用できません。

この **`bool`** 型は、既定の整数の上位変換に参加します。 型の右辺値 **`bool`** を型の右辺値に変換できます。これは **`int`** ゼロに **`false`** **`true`** なり、1になります。 別個の型として、は **`bool`** オーバーロードの解決に参加します。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[組み込み型](../cpp/fundamental-types-cpp.md)
