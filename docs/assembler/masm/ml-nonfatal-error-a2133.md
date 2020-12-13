---
description: '詳細情報: ML の致命的でないエラー A2133'
title: ML の致命的でないエラー A2133
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2133
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
ms.openlocfilehash: 11a2d27a00ac4e1d8b669ec7a7d4fe523476b5c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128467"
---
# <a name="ml-nonfatal-error-a2133"></a>ML の致命的でないエラー A2133

**レジスタの値が INVOKE によって上書きされます**

レジスタが引数としてプロシージャに渡されましたが、他の引数を渡すために [INVOKE](invoke.md) によって生成されたコードは、レジスタの内容を破棄しました。

アセンブラーは、AX、AL、AH、EAX、DX、DL、DH、および EDX レジスタを使用して、データ変換を実行できます。

別のレジスタを使用してください。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](ml-error-messages.md)
