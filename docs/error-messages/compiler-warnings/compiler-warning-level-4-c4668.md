---
title: コンパイラの警告 (レベル 4) C4668 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4668
dev_langs:
- C++
helpviewer_keywords:
- C4668
ms.assetid: c6585460-bc4a-4a15-9242-4cbfce53c961
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c960eb2cc79298977c8d7c91808b0a5492d05758
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074006"
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