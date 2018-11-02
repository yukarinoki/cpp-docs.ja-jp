---
title: 推論による依存ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 958a33c29be0d68fee1044fff1d81235ea9370c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641377"
---
# <a name="inferred-dependents"></a>推論による依存ファイル

推定の依存は推論規則から派生し、明示的な依存ファイルの前に評価されます。 推論による依存ファイルをそのターゲットに対して最新ではない場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 場合は、推論による依存ファイルが存在しないか、独自の依存オブジェクトと比べて古い、NMAKE はまず推論による依存ファイルを更新します。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](../build/inference-rules.md)します。

## <a name="see-also"></a>関連項目

[依存](../build/dependents.md)