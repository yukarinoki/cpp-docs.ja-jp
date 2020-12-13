---
description: '詳細情報: ML の致命的でないエラー A2031'
title: ML の致命的でないエラー A2031
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: 8c92b4e3439a4e660c7c128e52bcadc668778189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129221"
---
# <a name="ml-nonfatal-error-a2031"></a>ML の致命的でないエラー A2031

**インデックスまたはベースレジスタである必要があります**

メモリ式でベースレジスタまたはインデックスレジスタではないレジスタを使用しようとしました。

たとえば、次の式では、このエラーが発生します。

```asm
[ax]
[bl]
```

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](ml-error-messages.md)
