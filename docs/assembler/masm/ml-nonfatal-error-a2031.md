---
title: ML の致命的でないエラー A2031
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2031
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
ms.openlocfilehash: f964c67ba7bf399e9a3761e4e201662a6a712a1b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74856702"
---
# <a name="ml-nonfatal-error-a2031"></a>ML の致命的でないエラー A2031

**インデックスまたはベースレジスタである必要があります**

メモリ式でベースレジスタまたはインデックスレジスタではないレジスタを使用しようとしました。

たとえば、次の式では、このエラーが発生します。

```asm
[ax]
[bl]
```

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>