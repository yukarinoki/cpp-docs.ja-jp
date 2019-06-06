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
ms.openlocfilehash: e481cb9de7c80d147179efceab2fda9b160f3c21
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184287"
---
# <a name="bool-c"></a>bool (C++)

このキーワードは組み込みの型です。 この型の変数に値を持つことができます[true](../cpp/true-cpp.md)と[false](../cpp/false-cpp.md)します。 条件式の型である**bool**ための型の値を指定**bool**します。 たとえば、`i!=0`の値に応じて、TRUE または FALSE を今すぐが`i`します。

**Visual Studio 2017 バージョン 15.3 以降**(で使用可能な[/std:c + + 17](../build/reference/std-specify-language-standard-version.md))。オペランドの後置または前置インクリメントまたはデクリメント演算子できない可能性があります型の**bool**します。 つまり、変数がある`b`型の**bool**、これらの式はもう行えません。

```cpp
    b++;
    ++b;
    b--;
    --b;
```

値 TRUE および FALSE は、次のリレーションシップを持ちます。

```cpp
!false == true
!true == false
```

次のステートメントがあるとします。

```cpp
if (condexpr1) statement1;
```

場合`condexpr1`が true の場合、`statement1`が常に実行されます。 場合`condexpr1`false で、`statement1`は実行されません。

後置または前置と **++** 型の変数に演算子を適用**bool**変数が TRUE に設定します。
**Visual Studio 2017 バージョン 15.3 以降**: の operator++ **bool**は言語から削除され、現在サポートされていません。

後置または前置 **--** 演算子は、この型の変数に適用することはできません。

**Bool**型が整数の上位変換に参加します。 型の右辺**bool**右辺値の型に変換できる**int**、FALSE になることを TRUE になりつつある 1 つと 0 です。 別個の型として**bool**オーバー ロードの解決に関与します。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[基本的な型](../cpp/fundamental-types-cpp.md)