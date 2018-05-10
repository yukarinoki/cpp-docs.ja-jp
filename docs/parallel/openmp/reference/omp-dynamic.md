---
title: OMP_DYNAMIC |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- OMP_DYNAMIC
dev_langs:
- C++
helpviewer_keywords:
- OMP_DYNAMIC OpenMP environment variable
ms.assetid: e306049d-b644-4b73-8b63-46c835bff98b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: de4a81d861bf72943a67356577da37c36df63f69
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ompdynamic"></a>OMP_DYNAMIC
OpenMP ランタイムが、並行領域内のスレッドの数を調整できるかどうかを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
set OMP_DYNAMIC[=TRUE | =FALSE]  
```  
  
## <a name="remarks"></a>コメント  
 `OMP_DYNAMIC`で環境変数をオーバーライドすることができます、 [omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)関数。  
  
 OpenMP の標準の Visual C 実装では既定値は`OMP_DYNAMIC=FALSE`します。  
  
 詳細については、次を参照してください。 [4.3 OMP_DYNAMIC](../../../parallel/openmp/4-3-omp-dynamic.md)です。  
  
## <a name="example"></a>例  
 次のコマンド セット、`OMP_DYNAMIC`環境変数を TRUE にします。  
  
```  
set OMP_DYNAMIC=TRUE  
```  
  
 次のコマンドの現在の設定を表示する、`OMP_DYNAMIC`環境変数。  
  
```  
set OMP_DYNAMIC  
```  
  
## <a name="see-also"></a>関連項目  
 [環境変数](../../../parallel/openmp/reference/openmp-environment-variables.md)