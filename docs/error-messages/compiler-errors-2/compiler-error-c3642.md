---
description: 詳細については、「コンパイラエラー C3642」を参照してください。
title: コンパイラ エラー C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: 77d65d2bb2c426fe78671328b0eccab739b9dabe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340308"
---
# <a name="compiler-error-c3642"></a>コンパイラ エラー C3642

' return_type/args ': ネイティブコードから __clrcall 呼び出し規約を持つ関数を呼び出すことはできません

[__Clrcall](../../cpp/clrcall.md)呼び出し規約でマークされた関数は、ネイティブ (アンマネージ) コードから呼び出すことができません。

*return_type/args* は、関数の名前か、呼び出そうとし `__clrcall` ている関数の型のいずれかです。  型は、関数ポインターを使用してを呼び出しているときに使用されます。

ネイティブコンテキストからマネージ関数を呼び出すには、関数を呼び出す "ラッパー" 関数を追加し `__clrcall` ます。 または、CLR マーシャリング機構を使用することもできます。詳細については、「 [方法: PInvoke を使用して関数ポインターをマーシャリングする](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md) 」を参照してください。

次の例では、C3642 が生成されます。

```cpp
// C3642.cpp
// compile with: /clr
using namespace System;
struct S {
   void Test(String ^ s) {   // CLR type in signature, implicitly __clrcall
      Console::WriteLine(s);
   }
   void Test2(char * s) {
      Test(gcnew String(s));
   }
};

#pragma unmanaged
int main() {
   S s;
   s.Test("abc");   // C3642
   s.Test2("abc");   // OK
}
```
