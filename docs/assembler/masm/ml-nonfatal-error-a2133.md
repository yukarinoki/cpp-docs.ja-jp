---
title: ML の致命的でないエラー A2133
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: c2d13aefe02543129340bcc307771a1026776d61
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74854616"
---
# <a name="ml-nonfatal-error-a2133"></a>ML の致命的でないエラー A2133

**レジスタの値が INVOKE によって上書きされます**

レジスタが引数としてプロシージャに渡されましたが、他の引数を渡すために[INVOKE](../../assembler/masm/invoke.md)によって生成されたコードは、レジスタの内容を破棄しました。

アセンブラーは、AX、AL、AH、EAX、DX、DL、DH、および EDX レジスタを使用して、データ変換を実行できます。

別のレジスタを使用してください。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>