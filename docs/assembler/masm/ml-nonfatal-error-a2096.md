---
title: ML の致命的でないエラー A2096 |Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f4ef76dca10b1208a931bc3e1cc09d82a639d2
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679599"
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096

**セグメント、グループ、またはセグメントのレジスタが必要です。**

セグメントまたはグループが必要ですが、見つかりませんでした。

次のいずれかが発生しました。

- セグメントに指定した左オペランドに演算子がオーバーライド (**:**) セグメントのレジスタ (CS、DS、SS、ES、FS、または gs シリーズ)、グループ名、セグメント名、またはセグメント式でした。

- [ASSUME](../../assembler/masm/assume.md)セグメント レジスタに有効なセグメントのアドレスをセグメントの登録、グループ、または特殊なが指定されたディレクティブ**フラット**グループ。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>