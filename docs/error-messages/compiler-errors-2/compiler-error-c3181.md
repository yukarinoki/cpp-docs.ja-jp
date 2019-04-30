---
title: コンパイラ エラー C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: dc848d4108ed4a1a7b6646647a1bbb1ec8dcadf7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62382400"
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
