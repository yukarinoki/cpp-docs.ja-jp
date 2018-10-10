---
title: コンパイラ エラー C2872 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2872
dev_langs:
- C++
helpviewer_keywords:
- C2872
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4bdc67e13db11949371e2f9e3d8a205b146d701
ms.sourcegitcommit: d3c41b16bf05af2149090e996d8e71cd6cd55c7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/09/2018
ms.locfileid: "48890117"
---
# <a name="compiler-error-c2872"></a>コンパイラ エラー C2872

'*シンボル*': あいまいなシンボル

コンパイラを参照する記号を特定できません。 指定した名前の 1 つ以上のシンボルはスコープです。 コンパイラによって、あいまいなシンボルの検出されたノートでは、次のファイルの場所と宣言のエラー メッセージを参照してください。 この問題を解決するを完全に修飾あいまいなシンボルが、名前空間などを使用して`std::byte`または`::byte`します。 使用することも、[名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases)ソース コード内のシンボルの明確化時に、含まれる名前空間を使用するための便利な短い名前を付与します。

C2872 は、ヘッダー ファイルが含まれている場合に発生することが、[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)、後続のヘッダー ファイルが含まれるともで指定された名前空間内にある型を含む、`using`ディレクティブ。 指定、`using`後にのみ、ヘッダー ファイルで指定されますディレクティブ`#include`します。

C2872 は、Visual Studio 2013 で、間の競合により発生することができます、`Windows::Foundation::Metadata::Platform`列挙型と c++/cli CX 定義`Platform`名前空間。 この問題を回避するには、次の手順に従います。

- プロジェクト ファイルから"名前空間 Windows::Foundation::Metadata using"句を削除します。

- この名前空間に含まれている任意の型の完全修飾名を指定します。

## <a name="example"></a>例

次の例では、という名前の変数に、あいまいな参照が行われたため、C2872 が生成されます`i`2 つと同じ名前の変数のスコープは。

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