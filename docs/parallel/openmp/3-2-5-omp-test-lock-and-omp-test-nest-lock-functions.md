---
title: 3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5023f0b089d76e92be886f4917905f57dda7a018
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686228"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数
これらの関数は、ロックを設定しようとしていますが、スレッドの実行をブロックしません。 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_test_lock(omp_lock_t *lock);  
int omp_test_nest_lock(omp_nest_lock_t *lock);  
```  
  
 引数は、初期化されたロック変数を指す必要があります。 これらの関数と同じ方法で、ロックを設定しようとしました。`omp_set_lock`と`omp_set_nest_lock`スレッドの実行をブロックしないことを除いて、します。  
  
 単純ロック、`omp_test_lock`関数が正常にロックが設定されている場合、0 以外の値を返します。 それ以外の場合、0 を返します。  
  
 入れ子にできるロックで、`omp_test_nest_lock`関数が正常にロックが設定されている場合、新しい入れ子になった数を返します。 それ以外の場合、0 を返します。