---
title: コンパイラ エラー C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: d761dfde26cce9c99ccd4c3e6fd86ae1d6e16ddc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573278"
---
# <a name="compiler-error-c2015"></a>コンパイラ エラー C2015

定数の文字列の文字が多すぎます

文字定数には、2 つ以上の文字が含まれています。 制限には、標準の文字定数の 1 つの文字長の文字定数の 2 つの文字がされています。

\T などのエスケープ シーケンスは、1 つの文字に変換されます。

## <a name="example"></a>例

次の例では、C2015 が生成されます。

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>例

C2015 は、Microsoft 拡張機能、文字定数の整数に変換を使用する場合にも発生します。  次の例では、C2015 が生成されます。

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```