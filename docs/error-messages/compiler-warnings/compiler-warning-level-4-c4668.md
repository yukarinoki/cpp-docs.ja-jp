---
title: コンパイラの警告 (レベル 4) C4668
ms.date: 11/04/2016
f1_keywords:
- C4668
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
ms.openlocfilehash: 11d96941a1efddde87068af8829e24259f2fa312
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529975"
---
# <a name="compiler-warning-level-4-c4668"></a>コンパイラの警告 (レベル 4) C4668

'symbol' は、'directives' を '0' に置換するプリプロセッサ マクロとして定義されていません。

プリプロセッサ ディレクティブで定義されていないシンボルが使用されました。 シンボルは、false に評価されます。 シンボルを定義する、いずれかを使用できます、 [#include ディレクティブを define](../../preprocessor/hash-define-directive-c-cpp.md)または[/D](../../build/reference/d-preprocessor-definitions.md)コンパイラ オプション。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C4668 が生成されます。

```
// C4668.cpp
// compile with: /W4
#include <stdio.h>

#pragma warning (default : 4668)   // turn warning on

int main()
{
    #if q   // C4668, q is not defined
        printf_s("defined");
    #else
        printf_s("undefined");
    #endif
}
```