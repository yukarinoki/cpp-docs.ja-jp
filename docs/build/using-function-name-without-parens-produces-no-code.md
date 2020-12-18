---
description: '詳細情報: "()" のない関数名とコードの生成'
title: "\"()\" のない関数名とコードの生成"
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 1fedc296422a759878c26469ccc20955043b3913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277259"
---
# <a name="using-function-name-without--produces-no-code"></a>"()" のない関数名とコードの生成

プログラム内で宣言した関数名をかっこなしで使用すると、コンパイラによるコードの生成が行われません。 これは、コンパイラにより関数のアドレスが計算されるため、この関数がパラメーターを受け取るかどうかに関係なく発生します。ただし、関数呼び出し演算子 "()" が存在しないため、呼び出しは行われません。 この結果は、以下に似ています。

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

Visual C++ では、警告レベル 4 を使用していても、診断出力が生成されません。 警告は発行されず、コードは生成されません。

次のサンプル コードは、コンパイルされ (警告あり)、エラーなしで正しくリンクされますが、`funcn( )` への参照のコードは生成されません。 これを正しく機能させるには、関数呼び出し演算子 "()" を追加します。

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>関連項目

[コードの最適化](optimizing-your-code.md)
