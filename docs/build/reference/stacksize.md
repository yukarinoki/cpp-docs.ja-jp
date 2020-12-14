---
description: '詳細情報: STACKSIZE'
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: b5d52bccc09979084b9023d380e86fe90e4def32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230342"
---
# <a name="stacksize"></a>STACKSIZE

スタック サイズをバイト単位で設定します。

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>解説

スタックの設定方法は、 [スタック割り当て](stack-stack-allocations.md) (/STACK) オプションを使用する場合と同じです。 *予約* および引数の詳細については、そのオプションに関するドキュメントを参照してください `commit` 。

このオプションは、Dll には影響しません。

## <a name="see-also"></a>関連項目

[Module-Definition ステートメントの規則](rules-for-module-definition-statements.md)
