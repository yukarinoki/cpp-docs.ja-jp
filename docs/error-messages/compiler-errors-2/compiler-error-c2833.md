---
title: コンパイラ エラー C2833
ms.date: 11/04/2016
f1_keywords:
- C2833
helpviewer_keywords:
- C2833
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
ms.openlocfilehash: a6ffcb13d04f3c7c5ac62e147a2b6b2b305e11e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218170"
---
# <a name="compiler-error-c2833"></a>コンパイラ エラー C2833

> ' operator *operator-name*' は演算子または型として認識されません

この単語の後には、 **`operator`** オーバーライドする*演算子名*または変換する型を指定する必要があります。

マネージ型で定義できる演算子の一覧については、「[ユーザー定義演算子](../../dotnet/user-defined-operators-cpp-cli.md)」を参照してください。

次の例では、C2833 が生成されます。

```cpp
// C2833.cpp
// compile with: /c
class A {};

void operator ::* ();   // C2833
void operator :: ();   // OK
```
