---
title: ML の致命的でないエラー A2206 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2206
dev_langs:
- C++
helpviewer_keywords:
- A2206
ms.assetid: 711846d0-5a09-4353-8857-60588c25526a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 10edbe68ca7f0093cdeb6a9ca5a02cde07f556e6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676349"
---
# <a name="ml-nonfatal-error-a2206"></a>ML の致命的でないエラー A2206

**式で演算子がありません。**

演算子がないために、式を評価できません。 このエラー メッセージは、前のプログラム エラーの副作用もあります。

このエラーは、次の行が生成されます。

```asm
value1 = ( 1 + 2 ) 3
```

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>