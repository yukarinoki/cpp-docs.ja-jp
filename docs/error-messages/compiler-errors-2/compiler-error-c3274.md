---
description: 詳細については、「コンパイラエラー C3274」を参照してください。
title: コンパイラ エラー C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: 6706cc404bd6540aff7aa1afb94ada28249a0ade
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185740"
---
# <a name="compiler-error-c3274"></a>コンパイラ エラー C3274

__finally/finally に対応する try がありません

一致するがない [__finally](../../cpp/try-finally-statement.md) または [finally](../../dotnet/finally.md) ステートメントが見つかりました **`try`** 。 これを解決するには、ステートメントを削除するか **`__finally`** 、のステートメントを追加し **`try`** **`__finally`** ます。

次の例では C3274 が生成されます。

```cpp
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```
