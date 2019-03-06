---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: 5f0c23ad8b8d81f888616042ee5d6ba5bc63bd44
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412875"
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
