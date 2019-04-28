---
title: コンパイラの警告 (レベル 1) C4401
ms.date: 11/04/2016
f1_keywords:
- C4401
helpviewer_keywords:
- C4401
ms.assetid: 2e7ca136-f144-4b40-b847-82976e8643fc
ms.openlocfilehash: c7e6cf8a52288d895b74481678dc91fee387a6a3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280426"
---
# <a name="compiler-warning-level-1-c4401"></a>コンパイラの警告 (レベル 1) C4401

'ビット フィールド': メンバーがビット フィールドです

インライン アセンブリ コードは、ビット フィールド メンバーにアクセスしようとします。 ビット フィールド メンバーの前に最後のパッキング境界が使用されるため、インライン アセンブリは、ビット フィールド メンバーにアクセスできません。

この警告を回避するには、インライン アセンブリ コード内の参照を行う前に適切な型をビット フィールドをキャストします。 次の例では、C4401 が生成されます。

```
// C4401.cpp
// compile with: /W1
// processor: x86
typedef struct bitfield {
   signed bit : 1;
} mybitfield;

int main() {
   mybitfield bf;
   bf.bit = 0;
   __asm {
      mov bf.bit,0;   // C4401
   }

   /* use the following __asm block to resolve the warning
   int i = (int)bf.bit;
   __asm {
      mov i,0;
   }
   */
}
```