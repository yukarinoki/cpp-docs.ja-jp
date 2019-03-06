---
title: 推論による依存ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: d4d12d0ab686c604ce0d4495df89ec62c6160ebe
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414149"
---
# <a name="inferred-dependents"></a>推論による依存ファイル

推定の依存は推論規則から派生し、明示的な依存ファイルの前に評価されます。 推論による依存ファイルをそのターゲットに対して最新ではない場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 場合は、推論による依存ファイルが存在しないか、独自の依存オブジェクトと比べて古い、NMAKE はまず推論による依存ファイルを更新します。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](../build/inference-rules.md)します。

## <a name="see-also"></a>関連項目

[依存](../build/dependents.md)
