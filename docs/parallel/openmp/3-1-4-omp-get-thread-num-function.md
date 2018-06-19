---
title: 3.1.4 omp_get_thread_num 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad749b91470f7834169fe8ed734f1d627aa228e
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686072"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num 関数
`omp_get_thread_num`関数、スレッドの数を返します、そのチーム内で関数を実行するスレッド。 0 との間のスレッドの番号にあると**omp_get_num_threads()**-1、包括的です。 チームのマスター スレッドはスレッド 0 です。  
  
 形式は次のとおりです。  
  
```  
#include <omp.h>  
int omp_get_thread_num(void);  
```  
  
 シリアル領域から呼び出された場合`omp_get_thread_num`0 を返します。 シリアル化される入れ子になった並行領域内から呼び出されると、この関数は 0 を返します。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   `omp_get_num_threads` 関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ。