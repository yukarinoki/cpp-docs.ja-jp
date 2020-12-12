---
description: 詳細については、「コンパイラエラー C3063」を参照してください。
title: コンパイラ エラー C3063
ms.date: 11/04/2016
f1_keywords:
- C3063
helpviewer_keywords:
- C3063
ms.assetid: 0ecf6f1f-e4a7-487a-9fd5-79d8ac470001
ms.openlocfilehash: 304359e34b6cbae07d2f901db02c6e5ed04e373c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281705"
---
# <a name="compiler-error-c3063"></a>コンパイラ エラー C3063

演算子 ' operator ': すべてのオペランドには、同じ列挙型を指定しなければなりません

列挙子に対して演算子を使用する場合、両方のオペランドが列挙型である必要があります。 詳細については、「 [方法: C++/cli で列挙型を定義および使用する](../../dotnet/how-to-define-and-consume-enums-in-cpp-cli.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3063 を生成し、その修正方法を示しています。

```cpp
// C3063.cpp
// compile with: /clr
enum class E { a, b } e, mask;
int main() {
   if ( ( e & mask ) != 0 ) ;   // C3063 no operator!= (E, int)

   if ( ( e & mask ) != E() )   // OK
      ;
}
```
