---
title: コンパイラ エラー C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b37b28b4332b46aaaf803f58090a72c25e83f47f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587760"
---
# <a name="compiler-error-c3181"></a>コンパイラ エラー C3181

'type': 演算子のオペランドが無効です

無効なパラメーターが渡された、 [typeid](../../windows/typeid-cpp-component-extensions.md)演算子。 パラメーターは、マネージ型である必要があります。

コンパイラでは、共通言語ランタイムで型にマップするネイティブ型のエイリアスが使用されることに注意してください。

次の例では、C3181 が生成されます。

```
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
