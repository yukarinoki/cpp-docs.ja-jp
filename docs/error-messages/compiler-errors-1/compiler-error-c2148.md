---
title: コンパイラ エラー C2148
ms.date: 11/04/2016
f1_keywords:
- C2148
helpviewer_keywords:
- C2148
ms.assetid: e510c2c9-7b57-4ce8-be03-ba363e2cc5d9
ms.openlocfilehash: 893f1f029b2ea1aaf7ff53a5ee5cee7fcbe36e7c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175382"
---
# <a name="compiler-error-c2148"></a>コンパイラ エラー C2148

配列の合計サイズは、0x7fffffff バイトを超えていない必要があります。

配列は、制限を超えています。 配列のサイズを小さきます。

## <a name="example"></a>例

次の例では、C2148 が生成されます。

```
// C2148.cpp
#include <stdio.h>
#include <stdlib.h>

int main( ) {
   char MyArray[0x7ffffffff];   // C2148
   char * MyArray2 = (char *)malloc(0x7fffffff);

   if (MyArray2)
      printf_s("It worked!");
   else
      printf_s("It didn't work.");
}
```