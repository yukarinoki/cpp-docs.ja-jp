---
description: '詳細情報: ML の致命的でないエラー A2096'
title: ML の致命的でないエラー A2096
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: cbef33a8147b9f4cbe436860611f643b4f272516
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128532"
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096

**セグメント、グループ、またはセグメントの登録が必要です**

セグメントまたはグループが必要ですが、見つかりませんでした。

次のいずれかが発生しました。

- セグメントの上書き演算子 (**:**) で指定された左オペランドは、セグメントレジスタ (CS、DS、SS、ES、FS、または GS)、グループ名、セグメント名、またはセグメント式ではありませんでした。

- [想定](assume.md)されるディレクティブに、有効なセグメントアドレス、セグメントレジスタ、グループ、または特殊な **フラット** グループのないセグメントレジスタが指定されました。

## <a name="see-also"></a>関連項目

[ML エラー メッセージ](ml-error-messages.md)
