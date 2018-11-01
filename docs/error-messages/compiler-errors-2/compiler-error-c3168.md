---
title: コンパイラ エラー C3168
ms.date: 11/04/2016
f1_keywords:
- C3168
helpviewer_keywords:
- C3168
ms.assetid: 4c36fcfb-c351-48ff-b4eb-78d2aa1b4d55
ms.openlocfilehash: f39160cc09825c6d87d56ff5ba80d21a35f41e12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676565"
---
# <a name="compiler-error-c3168"></a>コンパイラ エラー C3168

'type': 基になる列挙型の型が無効です

型の指定を基になる、`enum`型が無効です。 基になる型は、C++ の整数型または対応する CLR 型である必要があります。

次の例では、C3168 が生成されます。

```
// C3168.cpp
// compile with: /clr /c
ref class G{};

enum class E : G { e };   // C3168
enum class F { f };   // OK
```
