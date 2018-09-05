---
title: ML の致命的でないエラー A2031 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2031
dev_langs:
- C++
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf6744224847e114e76df6e7ad6470696d3e8387
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43682659"
---
# <a name="ml-nonfatal-error-a2031"></a>ML の致命的でないエラー A2031

**インデックスまたはベースの登録をする必要があります。**

メモリ式でベースまたはインデックス レジスタがレジスタの使用が試行されました。

たとえば、次の式では、このエラーが発生します。

```asm
[ax]
[bl]
```

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>