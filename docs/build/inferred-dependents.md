---
title: 推論による依存ファイル |Microsoft ドキュメント
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
ms.openlocfilehash: a86ed1a8fe6c97ae11af50f59cb639ef6fd7c1da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367899"
---
# <a name="inferred-dependents"></a>推論による依存ファイル
推論による依存ファイルでは、推論規則からは派生し、明示的な依存オブジェクトの前に評価されます。 推論による依存ファイルがターゲットと比べて古い場合は、(nmake の) は、依存関係のコマンド ブロックを呼び出します。 推論による依存ファイルが存在しないか、独自の依存オブジェクトに対して最新ではないが場合、(nmake の) は、推論による依存ファイルを最初に更新されます。 推論による依存ファイルの詳細については、次を参照してください。[推論規則](../build/inference-rules.md)です。  
  
## <a name="see-also"></a>関連項目  
 [依存](../build/dependents.md)