---
title: STACKSIZE |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9b61febedde1a2647df6312a8588b08c6bdad7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705563"
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