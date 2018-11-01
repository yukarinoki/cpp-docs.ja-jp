---
title: コンパイラ エラー C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: 8a4a2011124056af7064c8241450e1f3613776a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580870"
---
# <a name="compiler-error-c3073"></a>コンパイラ エラー C3073

'type': ref クラスには、ユーザー定義のコピー コンス トラクターがありません。

[/Clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)のコンパイル時に、コンパイラでは、参照型のコピー コンス トラクターは生成されません。 いずれかで **/clr**のコンパイル時にコピーする型のインスタンスが予想される場合、参照型の独自のコピー コンス トラクターを定義する必要があります。

詳細については、次を参照してください。[参照型の C++ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)します。

## <a name="example"></a>例

次の例では、C3073 が生成されます。

```
// C3073.cpp
// compile with: /clr
ref class R {
public:
   R(int) {}
};

ref class S {
public:
   S(int) {}
   S(const S %rhs) {}   // copy constructor
};

void f(R) {}
void f2(S) {}
void f3(R%){}

int main() {
   R r(1);
   f(r);   // C3073
   f3(r);   // OK

   S s(1);
   f2(s);   // OK
}
```