---
description: 詳細については、「コンパイラエラー C3073」を参照してください。
title: コンパイラ エラー C3073
ms.date: 11/04/2016
f1_keywords:
- C3073
helpviewer_keywords:
- C3073
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
ms.openlocfilehash: e26938d6c708c364bb2447b793abf7d51adb5779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320248"
---
# <a name="compiler-error-c3073"></a>コンパイラ エラー C3073

' type ': ref クラスにユーザー定義のコピーコンストラクターがありません。

[/Clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)コンパイルでは、コンパイラは参照型のコピーコンストラクターを生成しません。 任意の **/clr** コンパイルで、型のインスタンスがコピーされることが予想される場合は、参照型に対して独自のコピーコンストラクターを定義する必要があります。

詳細については、「 [参照型の C++ スタックセマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3073 が生成されます。

```cpp
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
