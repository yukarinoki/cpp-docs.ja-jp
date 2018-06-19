---
title: lastprivate |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- lastprivate
dev_langs:
- C++
helpviewer_keywords:
- lastprivate OpenMP clause
ms.assetid: 6ef87b31-375a-47e8-8d0d-281be45fb56a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5aaf80e3061877c42154ab9ee5ccd30f47f17135
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696228"
---
# <a name="lastprivate"></a>lastprivate
いる変数の外側のコンテキストのバージョンを設定して、最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行したスレッドのプライベート バージョンを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
lastprivate(var)  
```  
  
## <a name="remarks"></a>コメント  
 指定項目  
  
 `var`  
 どのスレッドのプライベート バージョンと同じに設定されている変数は、最後の反復処理 (for ループ コンストラクト) または最後のセクション (#pragma セクション) を実行します。  
  
## <a name="remarks"></a>コメント  
 `lastprivate` 次のディレクティブに適用されます。  
  
-   [for](../../../parallel/openmp/reference/for-openmp.md)  
  
-   [sections](../../../parallel/openmp/reference/sections-openmp.md)  
  
 詳細については、次を参照してください。 [2.7.2.3 lastprivate](../../../parallel/openmp/2-7-2-3-lastprivate.md)です。  
  
## <a name="example"></a>例  
 参照してください[スケジュール](../../../parallel/openmp/reference/schedule.md)の使用例については`lastprivate`句。  
  
## <a name="see-also"></a>関連項目  
 [句](../../../parallel/openmp/reference/openmp-clauses.md)