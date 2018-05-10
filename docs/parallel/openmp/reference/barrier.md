---
title: バリア |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- barrier
dev_langs:
- C++
helpviewer_keywords:
- barrier OpenMP directive
ms.assetid: 5c73ad4f-c768-443a-8f9e-4fd8bc2253c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf5b2cd9edf54e58c06e7d2a48529393cd3ced64
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="barrier"></a>barrier
チーム内のすべてのスレッドを同期します。すべてのスレッドがバリアを実行するまで、すべてのスレッドがバリアで一時停止します。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma omp barrier  
```  
  
## <a name="remarks"></a>コメント  
 `barrier`ディレクティブに OpenMP 句がサポートされていません。  
  
 詳細については、次を参照してください。 [2.6.3 barrier ディレクティブ](../../../parallel/openmp/2-6-3-barrier-directive.md)です。  
  
## <a name="example"></a>例  
 使用する方法のサンプルについては`barrier`を参照してください[マスター](../../../parallel/openmp/reference/master.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)