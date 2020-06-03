---
title: コンパイラの警告 (レベル 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 5028ae20c2413c98fa55bd81081552d22381cdbc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163677"
---
# <a name="compiler-warning-level-1-c4145"></a>コンパイラの警告 (レベル 1) C4145

'expression1' : switch ステートメントの制御式と関係する式 ; 式 'expression2' は、case 式と見なされます

`switch` ステートメントで、関係式をその制御式として使用した結果、 **case** ステートメントにブール値が返されます。 *expression2*を意図していましたか。

## <a name="example"></a>例

次の例では C4145 が生成されます。

```cpp
// C4145.cpp
// compile with: /W1
int main() {
   int i = 0;
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve
      case 1:
         break;
      default:
         break;
   }
}
```
