---
title: コンパイラの警告 (レベル 4) C4127 |Microsoft Docs
ms.custom: ''
ms.date: 09/13/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4127
dev_langs:
- C++
helpviewer_keywords:
- C4127
ms.assetid: f59ded9e-5227-45bd-ac43-2aa861581363
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80f831d527e918fce0551f6a1336fd2fe994917d
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161282"
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