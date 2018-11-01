---
title: コンパイラの警告 (レベル 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 7d9a4ed09f026267e2c0f37fbbe4550ecd668dfc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514427"
---
# <a name="compiler-warning-level-2-c4156"></a>コンパイラの警告 (レベル 2) C4156

'delete'; の形式は、配列を使用せず、配列式の削除配列形式の代わりに使用

非配列形式の**削除**配列を削除することはできません。 コンパイラの翻訳**削除**形式は、配列にします。

この警告は、Microsoft 拡張機能 (/Ze) でのみ発生します。

## <a name="example"></a>例

```
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```