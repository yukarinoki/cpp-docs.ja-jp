---
description: 詳細については、「コンパイラエラー C2015」を参照してください。
title: コンパイラエラー C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 0c27dbf8f7383ebd6424e9482fd1ce8cc0839a39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220956"
---
# <a name="compiler-error-c2015"></a>コンパイラエラー C2015

定数に文字が多すぎます

文字定数に3文字以上が含まれています。 制限は、標準文字定数の場合は1文字、長い文字定数の場合は2文字です。

エスケープシーケンス (\t など) は、1つの文字に変換されます。

## <a name="examples"></a>例

次の例では、C2015 が生成されます。

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

C2015 は、Microsoft 拡張機能、文字定数を整数に変換して使用する場合にも発生します。  次の例では、C2015 が生成されます。

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
