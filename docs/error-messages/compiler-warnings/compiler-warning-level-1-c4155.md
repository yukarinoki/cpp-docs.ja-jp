---
description: '詳細情報: コンパイラの警告 (レベル 1) C4155'
title: コンパイラの警告 (レベル 1) C4155
ms.date: 11/04/2016
f1_keywords:
- C4155
helpviewer_keywords:
- C4155
ms.assetid: ba233353-09e3-4195-8127-13a27ddd8d70
ms.openlocfilehash: 04ea5ae01799fcda17c3591cf4dbc14daf4236ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267301"
---
# <a name="compiler-warning-level-1-c4155"></a>コンパイラの警告 (レベル 1) C4155

'delete' の配列でない形式を使った配列の削除は、定義されていません。

配列を削除するには、の配列形式を **`delete`** 使用する必要があります。 この警告は、ANSI 互換 (/Za) の環境でのみ発生します。

## <a name="example"></a>例

次の例では C4155 が生成されます。

```cpp
// C4155.cpp
// compile with: /Za /W1
#include <stdio.h>

int main(void)
{
    int (*array)[ 10 ] = new int[ 5 ] [ 10 ];
    array[0][0] = 8;

    printf_s("%d\n", array[0][0]);

   delete array;   // C4155
    // try the following line instead
    // delete [] array;   // C4155
}
```
