---
title: コンパイラ エラー C3642
ms.date: 11/04/2016
f1_keywords:
- C3642
helpviewer_keywords:
- C3642
ms.assetid: 429790c2-9614-4d85-b31c-687c8d8f83ff
ms.openlocfilehash: d524c49075c400caa345dd26ed681734ea0cfb94
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582651"
---
# <a name="compiler-error-c3642"></a>コンパイラ エラー C3642

' return_type/args ': _ _clrcall 呼び出し規約をネイティブ コードからの関数を呼び出すことはできません

マークされている関数、 [_ _clrcall](../../cpp/clrcall.md)呼び出し規約は、ネイティブ (アンマネージ) コードから呼び出すことができません。

*引数 return_type/* 、いずれかの関数の名前または種類の`__clrcall`関数を呼び出すしようとしています。  型は、関数ポインターを通じて呼び出すときに使用されます。

ネイティブ コンテキストから管理対象の関数を呼び出すには、「ラッパー」関数を呼び出すを追加する、`__clrcall`関数。 または、CLR マーシャ リング機構を使用することができます。参照してください[方法: PInvoke を使用して関数ポインターをマーシャ リング](../../dotnet/how-to-marshal-function-pointers-using-pinvoke.md)詳細についてはします。

次の例では、C3642 が生成されます。

```
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