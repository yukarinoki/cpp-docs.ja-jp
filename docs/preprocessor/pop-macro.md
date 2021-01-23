---
description: pragmaMicrosoft C/c + + での pop_macro ディレクティブの詳細については、こちらを参照してください。
title: pop_macro pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.pop_macro
- pop_macro_CPP
helpviewer_keywords:
- pop_macro pragma
- pragma, pop_macro
no-loc:
- pragma
ms.openlocfilehash: 99b0567838bac2a683f2a31fe13dd423e2efe651
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713364"
---
# <a name="pop_macro-no-locpragma"></a>`pop_macro` pragma

*マクロ名* マクロの値を、このマクロのスタックの一番上にある値に設定します。

## <a name="syntax"></a>構文

> **`#pragma pop_macro(`** "*マクロ名*" **`)`**

## <a name="remarks"></a>解説

を [`push_macro`](../preprocessor/push-macro.md) 実行する前に、 *マクロ名* のが発行されている必要があり **`pop_macro`** ます。

## <a name="example"></a>例

```cpp
// pragma_directives_pop_macro.cpp
// compile with: /W1
#include <stdio.h>
#define X 1
#define Y 2

int main() {
   printf("%d",X);
   printf("\n%d",Y);
   #define Y 3   // C4005
   #pragma push_macro("Y")
   #pragma push_macro("X")
   printf("\n%d",X);
   #define X 2   // C4005
   printf("\n%d",X);
   #pragma pop_macro("X")
   printf("\n%d",X);
   #pragma pop_macro("Y")
   printf("\n%d",Y);
}
```

```Output
1
2
1
2
1
3
```

## <a name="see-also"></a>関連項目

[プラグマディレクティブと `__pragma` `_Pragma` キーワードおよびキーワード](./pragma-directives-and-the-pragma-keyword.md)
