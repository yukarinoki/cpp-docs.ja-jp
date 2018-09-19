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
ms.openlocfilehash: 038c3475a6041dfb719bb2270a87ac2898f8b958
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036762"
---
# <a name="compiler-error-c2872"></a>コンパイラ エラー C2872

'*シンボル*': あいまいなシンボル

コンパイラを参照する記号を特定できません。 指定した名前の 1 つ以上のシンボルはスコープです。 コンパイラによって、あいまいなシンボルの検出されたノートでは、次のファイルの場所と宣言のエラー メッセージを参照してください。 この問題を解決するを完全に修飾あいまいなシンボルが、名前空間などを使用して`std::byte`または`::byte`します。 使用することも、[名前空間エイリアス](../../cpp/namespaces-cpp.md#namespace_aliases)ソース コード内のシンボルの明確化時に、含まれる名前空間を使用するための便利な短い名前を付与します。

C2872 は、ヘッダー ファイルが含まれている場合に発生することが、[ディレクティブを使用して](../../cpp/namespaces-cpp.md#using_directives)、後続のヘッダー ファイルが含まれるともで指定された名前空間内にある型を含む、`using`ディレクティブ。 指定、`using`後にのみ、ヘッダー ファイルで指定されますディレクティブ`#include`します。

C2872 の詳細については、サポート技術情報の記事をご覧ください[PRB: コンパイラ エラー時に使用する #import Visual c .NET で XML を](http://support.microsoft.com/kb/316317)と["エラー C2872: 'Platform': あいまいなシンボル"を使用すると、エラー メッセージ、。Visual Studio 2013 で名前空間を Windows::Foundation::Metadata](https://support.microsoft.com/kb/2890859)します。

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