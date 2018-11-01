---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: de2aa99375f588d682b714632590ba8e0db8ddcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597224"
---
# <a name="stacksize"></a>STACKSIZE

スタック サイズをバイト単位で設定します。

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Remarks

スタックを設定することは、[スタック割り当て](../../build/reference/stack-stack-allocations.md)(/stack) オプション。 に関する詳細については、そのオプションについては、ドキュメントを参照してください、*予約*と`commit`引数。

このオプションは、Dll への影響を与えません。

## <a name="see-also"></a>関連項目

[モジュール定義ステートメントに関する規則](../../build/reference/rules-for-module-definition-statements.md)