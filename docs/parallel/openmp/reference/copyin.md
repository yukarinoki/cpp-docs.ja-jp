---
title: copyin |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- copyin
dev_langs:
- C++
helpviewer_keywords:
- copyin OpenMP clause
ms.assetid: 369efa88-613c-4cb1-9e11-7b9ee08a4b25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 32137534a43eeb0b038eae547f9bc19283412159
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="copyin"></a>copyin
スレッドのマスター スレッドの値にアクセスできるように、 [threadprivate](../../../parallel/openmp/reference/threadprivate.md)変数。  
  
## <a name="syntax"></a>構文  
  
```  
copyin(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 `threadprivate` Parallel コンストラクトの前に存在する場合に、マスター スレッド内の変数の値で初期化される変数です。  
  
## <a name="remarks"></a>コメント  
 `copyin` 次のディレクティブに適用されます。  
  
-   [parallel](../../../parallel/openmp/reference/parallel.md)  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.7 copyin](../../../parallel/openmp/2-7-2-7-copyin.md)です。  
  
## <a name="example"></a>例  
 参照してください[threadprivate](../../../parallel/openmp/reference/threadprivate.md)の使用例については`copyin`します。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)