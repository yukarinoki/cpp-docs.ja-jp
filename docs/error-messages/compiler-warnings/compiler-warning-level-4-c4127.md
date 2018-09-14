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
ms.openlocfilehash: 1bfd913b95b84d8425649476649f9bffa6163141
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601523"
---
# <a name="compiler-warning-level-4-c4127"></a>コンパイラの警告 (レベル 4) C4127

> 条件式が定数です。

## <a name="remarks"></a>Remarks

`if` ステートメントまたは `while` ループの制御式が定数に評価されます。 以降では、Visual Studio 2015 update 3 では、単純な定数 1 などの一般的な慣用用法のためまたは`true`式内の操作の結果でない限り、警告をトリガーしません。

場合の制御式を`while`中央のループが終了したため、ループが定数の場合を考慮してください、`while`ループでは、`for`ループします。 初期化、終了テストを省略でき、ループのインクリメント、`for`ループと同じように、無限にループ`while(1)`の本文からループを終了して、`for`ステートメント。

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