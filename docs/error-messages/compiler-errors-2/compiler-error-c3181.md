---
title: コンパイラ エラー C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: dc848d4108ed4a1a7b6646647a1bbb1ec8dcadf7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781810"
---
# <a name="compiler-error-c3181"></a>コンパイラ エラー C3181

'type': 演算子のオペランドが無効です

無効なパラメーターが渡された、 [typeid](../../extensions/typeid-cpp-component-extensions.md)演算子。 パラメーターは、マネージ型である必要があります。

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
