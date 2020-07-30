---
title: コンパイラ エラー C2872
ms.date: 11/04/2016
f1_keywords:
- C2872
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
ms.openlocfilehash: f57b250f87bd7f2c5808b5a681ddfe49dfa5e876
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228896"
---
# <a name="compiler-error-c2872"></a>コンパイラ エラー C2872

'*symbol*': あいまいなシンボルです。

コンパイラは、参照しているシンボルを判別できません。 指定された名前を持つ複数のシンボルがスコープ内にあります。 コンパイラがあいまいなシンボルに対して検出したファイルの場所と宣言については、エラーメッセージに続くメモを参照してください。 この問題を解決するには、名前空間 (やなど) を使用して、あいまいなシンボルを完全修飾することができ `std::byte` `::byte` ます。 また、[名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases)を使用して、ソースコードでシンボルを明確化するときに使用する便利な短い名前を指定することもできます。

C2872 は、ヘッダーファイルに[using ディレクティブ](../../cpp/namespaces-cpp.md#using_directives)が含まれていて、ディレクティブで指定された名前空間にも含まれる型を含む後続のヘッダーファイルが含まれている場合に発生する可能性があり **`using`** ます。 ディレクティブは、 **`using`** すべてのヘッダーファイルがで指定された後にのみ指定し `#include` ます。

`Windows::Foundation::Metadata::Platform`列挙型と C++ で定義された名前空間の競合が原因で、Visual Studio 2013 で C2872 が発生する可能性があり `Platform` ます。 この問題を回避するには、次の手順を実行します。

- プロジェクトファイルから "using namespace Windows:: Foundation:: Metadata" 句を削除します。

- この名前空間に含まれる任意の型の完全修飾名を指定します。

## <a name="example"></a>例

次の例では、という名前の変数にあいまいな参照が行われるため、C2872 が生成されます `i` 。同じ名前の2つの変数はスコープ内にあります。

```cpp
// C2872.cpp
// compile with: cl /EHsc C2872.cpp
namespace A {
   int i;
}

using namespace A;
int i;
int main() {
   ::i++;   // ok, uses i from global namespace
   A::i++;   // ok, uses i from namespace A
   i++;   // C2872 ambiguous: ::i or A::i?
   // To fix this issue, use the fully qualified name
   // for the intended variable.
}
```
