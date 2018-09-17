---
title: 推論による依存ファイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 631c5631b60f0e05dd1f1541facc767f35944d3d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45701481"
---
# <a name="inferred-dependents"></a>推論による依存ファイル

推定の依存は推論規則から派生し、明示的な依存ファイルの前に評価されます。 推論による依存ファイルをそのターゲットに対して最新ではない場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 場合は、推論による依存ファイルが存在しないか、独自の依存オブジェクトと比べて古い、NMAKE はまず推論による依存ファイルを更新します。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](../build/inference-rules.md)します。

## <a name="see-also"></a>関連項目

[依存](../build/dependents.md)