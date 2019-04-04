---
title: コンパイラ エラー C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 9e53d9fe273a392695212df6dbeb679822a39068
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485537"
---
# <a name="compiler-error-c3063"></a>コンパイラ エラー C3063

演算子 'operator': すべてのオペランドは同じ列挙型である必要があります

演算子で列挙子を使用する場合は、両方のオペランドが列挙型でなければなりません。 詳細については、[方法: 定義および c++ の列挙型を使用する/cli CLI](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)を参照してください。

## <a name="example"></a>例

次の例では、C3063 を生成し、その修正方法を示しています。

```
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```