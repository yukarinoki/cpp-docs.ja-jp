---
description: 詳細については、「コンパイラエラー C3181」を参照してください。
title: コンパイラエラー C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b9b9c6e8c6271abbea2d97adf92f33c35eb2028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174131"
---
# <a name="compiler-error-c3181"></a>コンパイラエラー C3181

' type ': 演算子に対して無効なオペランドです

[Typeid](../../extensions/typeid-cpp-component-extensions.md)演算子に無効なパラメーターが渡されました。 パラメーターはマネージ型である必要があります。

コンパイラは、共通言語ランタイムの型にマップされるネイティブ型にエイリアスを使用することに注意してください。

次の例では、C3181 が生成されます。

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
