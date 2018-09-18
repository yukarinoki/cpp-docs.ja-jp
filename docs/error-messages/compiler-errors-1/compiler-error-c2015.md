---
title: コンパイラ エラー C2015 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fb9c3ba86224906f749088b96e5daae364d99e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076048"
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