---
title: コンパイラ エラー C2009
ms.date: 11/04/2016
f1_keywords:
- C2009
helpviewer_keywords:
- C2009
ms.assetid: fe9d94ed-20a5-4d83-b9c4-60ee69d2f30a
ms.openlocfilehash: d2216b3fe990109828492fb2b2055e9425c1e306
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361908"
---
# <a name="compiler-error-c2009"></a>コンパイラ エラー C2009

マクロの仮引数リストで 'identifier' が 2 回以上使われています

マクロ定義の仮パラメーター リストは、2 回以上、識別子を使用します。 マクロのパラメーター リストの識別子は一意である必要があります。

## <a name="example"></a>例

次の例では、C2009 が生成されます。

```
// C2009.cpp
#include <stdio.h>

#define macro1(a,a) (a*a)   // C2009

int main()
{
    printf_s("%d\n", macro1(2));
}
```

## <a name="example"></a>例

考えられる解決方法:

```
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