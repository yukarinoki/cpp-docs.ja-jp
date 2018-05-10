---
title: 3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8f14e182e6c981cd5de7a4cf92d8c285a4b49c66
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数
これらの関数は、ロックの初期化の唯一の手段を提供します。 各関数は、パラメーターに関連付けられているロック、初期化*ロック*後続の呼び出しで使用するためです。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_init_lock(omp_lock_t *lock);  
void omp_init_nest_lock(omp_nest_lock_t *lock);  
```  
  
 初期状態のロックが解除されている (つまり、スレッド ロックを所有していません)。 入れ子にできるロックでは、最初の入れ子になった数は 0 です。 これらのルーチンは既に初期化されているロック変数のいずれかを呼び出さない非準拠であります。