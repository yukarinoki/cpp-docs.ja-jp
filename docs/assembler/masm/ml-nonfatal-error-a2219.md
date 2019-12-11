---
title: ML の致命的でないエラー A2219
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2219
helpviewer_keywords:
- A2219
ms.assetid: 5ebc2f40-e47e-4f8e-b7b9-960b9cfc9f6d
ms.openlocfilehash: cf2be5db2aa9c21597c199a6840f4aaa50e0a681
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854590"
---
# <a name="ml-nonfatal-error-a2219"></a>ML の致命的でないエラー A2219

> アンワインドコードのオフセットのアラインメントが正しくありません

## <a name="remarks"></a>Remarks

[&period;ALLOCSTACK](../../assembler/masm/dot-allocstack.md)および[&period;SAVEREG](../../assembler/masm/dot-savereg.md)のオペランドは8の倍数である必要があります。  [&period;SAVEXMM128](../../assembler/masm/dot-savexmm128.md)と[&period;setframe](../../assembler/masm/dot-setframe.md)のオペランドは16の倍数である必要があります。

## <a name="see-also"></a>参照

[ML エラーメッセージ](../../assembler/masm/ml-error-messages.md)
