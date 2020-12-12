---
description: 詳細については、「コンパイラエラー C2653」を参照してください。
title: コンパイラエラー C2653
ms.date: 11/30/2017
f1_keywords:
- C2653
helpviewer_keywords:
- C2653
ms.assetid: 3f49e731-affd-43a0-a8d0-181db7650bc3
ms.openlocfilehash: f3be7ade8a6dcfc6aa8c5a83cc8a055fc230789d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286151"
---
# <a name="compiler-error-c2653"></a>コンパイラエラー C2653

> '*identifier*': クラスまたは名前空間の名前ではありません

言語の構文では、クラス、構造体、共用体、または名前空間の名前が必要です。

このエラーは、スコープ演算子の前にクラス、構造体、共用体、または名前空間として宣言されていない名前を使用した場合に発生する可能性があります。 この問題を解決するには、名前を宣言するか、名前を宣言するヘッダーを使用する前に含めます。

C2653 は、 *複合名前* 空間を定義しようとした場合にも可能です。これは、1つまたは複数のスコープで入れ子になった名前空間の名前を含む名前空間です。 C++ 17 より前の C++ では、複合名前空間の定義は許可されていません。 Visual Studio 2015 Update 3 以降では、 [/std: c + + latest](../../build/reference/std-specify-language-standard-version.md) コンパイラオプションを指定すると、複合名前空間がサポートされます。 Visual Studio 2017 バージョン15.5 以降では、 [/std: c++ 17](../../build/reference/std-specify-language-standard-version.md) オプションが指定されている場合、コンパイラは複合名前空間の定義をサポートします。

## <a name="examples"></a>例

このサンプルでは、スコープ名が使用されているが宣言されていないため、C2653 が生成されます。 コンパイラは、スコープ演算子 (::) の前に、クラス、構造体、共用体、または名前空間の名前を指定する必要があります。

```cpp
// C2653.cpp
// compile with: /c
class yy {
   void func1(int i);
};

void xx::func1(int m) {}   // C2653, xx is not declared
void yy::func1(int m) {}   // OK
```

C++ 17 以降の標準用にコンパイルされていないコードでは、入れ子になった名前空間で、入れ子のレベルごとに明示的な名前空間宣言を使用する必要があります。

```cpp
// C2653b.cpp
namespace a::b {int i;}   // C2653 prior to Visual Studio 2015 Update 3,
                          // C2429 thereafter. Use /std:c++17 or /std:c++latest to fix.

namespace a {             // Use this form for compliant code under /std:c++14 (the default)
   namespace b {          // or when using compilers before Visual Studio 2015 update 3.
      int i;
   }
}

int main() {
   a::b::i = 2;
}
```
