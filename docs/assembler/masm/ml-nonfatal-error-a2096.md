---
title: ML の致命的でないエラー A2096
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: e6b31afeff801e7128b5a76576e9eaa3398f68e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676279"
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096

**セグメント、グループ、またはセグメントのレジスタが必要です。**

セグメントまたはグループが必要ですが、見つかりませんでした。

次のいずれかが発生しました。

- セグメントに指定した左オペランドに演算子がオーバーライド (**:**) セグメントのレジスタ (CS、DS、SS、ES、FS、または gs シリーズ)、グループ名、セグメント名、またはセグメント式でした。

- [ASSUME](../../assembler/masm/assume.md)セグメント レジスタに有効なセグメントのアドレスをセグメントの登録、グループ、または特殊なが指定されたディレクティブ**フラット**グループ。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>