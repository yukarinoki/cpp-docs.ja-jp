---
title: コンパイラエラー C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: 8ea3a106e8819bf067203f220ca51e17b87bfe46
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225463"
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
