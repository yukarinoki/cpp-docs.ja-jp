---
title: OpenMP のデータの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf1e1045-4d12-4d03-80b7-d5843b80ef85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f33666b35f45bb668ab135941a0d15297442408a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690947"
---
# <a name="openmp-data-types"></a>OpenMP のデータ型
OpenMP API で使用されるデータ型へのリンクを提供します。  
  
 OpenMP の標準の Visual C の実装には、次のデータ型が含まれています。  
  
|データ型|説明|  
|---------------|-----------------|  
|[omp_lock_t](../../../parallel/openmp/reference/omp-lock-t.md)|ロックが、ロックが使用できるかどうか、またはスレッドにロックを所有しているかどうかの状態を保持する型。|  
|[omp_nest_lock_t](../../../parallel/openmp/reference/omp-nest-lock-t.md)|ロックに関する情報の次の 1 つを保持する型: かどうか、ロックが使用できる、およびスレッドの id を所有しているロックが解除され、入れ子になった回数です。|  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)