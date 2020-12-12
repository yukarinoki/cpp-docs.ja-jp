---
description: 詳細については、「コンパイラエラー C2632」を参照してください。
title: コンパイラエラー C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b6f1091b512d3a01efa933c998bde3d0885bbff1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123514"
---
# <a name="compiler-error-c2632"></a>コンパイラエラー C2632

' type1 ' の後に続く ' type1 ' は無効です

このエラーは、2つの型指定子の間にコードが欠落している場合に発生する可能性があります。

次の例では、C2632 が生成されます。

```cpp
// C2632.cpp
int float i;   // C2632
```

このエラーは、Visual Studio .NET 2003 で実行されたコンパイラ準拠作業の結果として生成されることもあります。 **`bool`** は、適切な型になりました。 以前のバージョンでは、は **`bool`** typedef であり、その名前を持つ識別子を作成できました。

次の例では、C2632 が生成されます。

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

このエラーを解決して、Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C++ でコードが有効になるようにするには、識別子の名前を変更します。
