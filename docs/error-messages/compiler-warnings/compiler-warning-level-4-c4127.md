---
title: コンパイラの警告 (レベル 4) C4127
ms.date: 09/13/2018
f1_keywords:
- C4127
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
ms.openlocfilehash: 7f1e23d15d8daa126987278611cb5a85a5a36fc9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401313"
---
# <a name="compiler-warning-level-4-c4127"></a>コンパイラの警告 (レベル 4) C4127

> 条件式が定数です。

## <a name="remarks"></a>Remarks

制御式、**場合**ステートメントまたは**中**ループが定数に評価されます。 以降では、Visual Studio 2015 update 3 では、単純な定数 1 などの一般的な慣用用法のためまたは**true**式内の操作の結果でない限り、警告をトリガーしません。

場合の制御式を**中に**中央のループが終了したため、ループが定数の場合を考慮してください、**中**ループでは、**の**ループします。 初期化、終了テストを省略でき、ループのインクリメント、**の**ループと同じように、無限にループ`while(1)`の本文からループを終了して、**の**ステートメント。

## <a name="example"></a>例

次のサンプルは C4127 が生成され、使用する方法を示しています。 2 つの方法、for ループ、警告を回避します。

```cpp
// C4127.cpp
// compile with: /W4
#include <stdio.h>
int main() {
   if (true) {}           // OK in VS2015 update 3 and later
   if (1 == 1) {}         // C4127
   while (42) { break; }  // C4127

   // OK
   for ( ; ; ) {
      printf("test\n");
      break;
   }
}
```