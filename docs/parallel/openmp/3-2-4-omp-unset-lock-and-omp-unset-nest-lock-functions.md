---
title: 3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f480a75efff737356c1477593e182537ae73a8c8
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690222"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数
これらの関数は、ロックの所有権を解放する手段を提供します。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_unset_lock(omp_lock_t *lock);  
void omp_unset_nest_lock(omp_nest_lock_t *lock);  
```  
  
 これらの各関数の引数は、関数を実行するスレッドが所有する初期化されたロック変数を指す必要があります。 スレッドがそのロックを所有していない場合、動作は定義されません。  
  
 単純ロック、`omp_unset_lock`関数は、ロックの所有権から関数を実行するスレッドを解放します。  
  
 入れ子にできるロックで、`omp_unset_nest_lock`関数デクリメント、入れ子のカウントとリリース、結果のカウントが 0 の場合は、ロックの所有権から関数を実行するスレッド。