---
title: コンパイラの警告 (レベル 1) C4145
ms.date: 11/04/2016
f1_keywords:
- C4145
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
ms.openlocfilehash: 19d2d1a018c7ee981f83aa6fa0914f1241c55538
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220107"
---
# <a name="compiler-warning-level-1-c4145"></a>コンパイラの警告 (レベル 1) C4145

'expression1' : switch ステートメントの制御式と関係する式 ; 式 'expression2' は、case 式と見なされます

ステートメントでは、 **`switch`** その制御式としてリレーショナル式を使用します。これにより、ステートメントのブール値が得ら **`case`** れます。 *expression2*を意図していましたか。

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
