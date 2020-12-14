---
description: 詳細については、「コンパイラエラー C2009」を参照してください。
title: コンパイラエラー C2009
ms.date: 11/04/2016
f1_keywords:
- C2009
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
ms.openlocfilehash: e7cc3078a8e404635dda531533bd3b1c629a0155
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221053"
---
# <a name="compiler-error-c2009"></a>コンパイラエラー C2009

マクロの仮引数リストで 'identifier' が 2 回以上使われています

マクロ定義の仮パラメーターリストで、識別子が複数回使用されています。 マクロのパラメーターリスト内の識別子は一意である必要があります。

## <a name="examples"></a>例

次の例では、C2009 が生成されます。

```cpp
// C2009.cpp
#include <stdio.h>

#define macro1(a,a) (a*a)   // C2009

int main()
{
    printf_s("%d\n", macro1(2));
}
```

考えられる解決策:

```cpp
// C2009b.cpp
#include <stdio.h>

#define macro2(a)   (a*a)
#define macro3(a,b) (a*b)

int main()
{
    printf_s("%d\n", macro2(2));
    printf_s("%d\n", macro3(2,4));
}
```
