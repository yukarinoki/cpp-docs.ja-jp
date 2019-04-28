---
title: 推論による依存ファイル
ms.date: 11/04/2016
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
ms.openlocfilehash: 2382dec960ef93fc2f73987ad27b4670768a68cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291536"
---
# <a name="inferred-dependents"></a>推論による依存ファイル

推定の依存は推論規則から派生し、明示的な依存ファイルの前に評価されます。 推論による依存ファイルをそのターゲットに対して最新ではない場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 場合は、推論による依存ファイルが存在しないか、独自の依存オブジェクトと比べて古い、NMAKE はまず推論による依存ファイルを更新します。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](inference-rules.md)します。

## <a name="see-also"></a>関連項目

[依存](dependents.md)
