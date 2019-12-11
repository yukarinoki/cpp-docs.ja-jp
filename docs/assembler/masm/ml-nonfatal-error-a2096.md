---
title: ML の致命的でないエラー A2096
ms.date: 08/30/2018
ms.custom: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: 14fb30214cf7badf51368672dc52635d50a067f1
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "74855475"
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096

**セグメント、グループ、またはセグメントの登録が必要です**

セグメントまたはグループが必要ですが、見つかりませんでした。

次のいずれかが発生しました。

- セグメントの上書き演算子 ( **:** ) で指定された左オペランドは、セグメントレジスタ (CS、DS、SS、ES、FS、または GS)、グループ名、セグメント名、またはセグメント式ではありませんでした。

- [想定](../../assembler/masm/assume.md)されるディレクティブに、有効なセグメントアドレス、セグメントレジスタ、グループ、または特殊な**フラット**グループのないセグメントレジスタが指定されました。

## <a name="see-also"></a>参照

[ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)<br/>