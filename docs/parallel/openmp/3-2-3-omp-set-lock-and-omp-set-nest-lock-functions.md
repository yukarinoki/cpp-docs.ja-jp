---
title: 3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba24e923051eb887db2a81c1d9765d31a4ef7b24
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数
これらの各関数は、指定されたロックを使用し、ロックを設定するまでは、関数を実行するスレッドをブロックします。 単純なロックはロックされていない場合に使用できます。 ロックされていない場合、または関数を実行するスレッドによって既に所有している場合は、入れ子にできるロックは使用します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_lock(omp_lock_t *lock);  
void omp_set_nest_lock(omp_nest_lock_t *lock);  
```  
  
 単純ロックへの引数、`omp_set_lock`関数は、初期化されたロック変数を指す必要があります。 ロックの所有権は、関数を実行するスレッドに与えられます。  
  
 入れ子にできるロックへの引数、`omp_set_nest_lock`関数は、初期化されたロック変数を指す必要があります。 入れ子のカウントがインクリメントされ、スレッドが付与されるか、ロックの所有権を保持します。 します。