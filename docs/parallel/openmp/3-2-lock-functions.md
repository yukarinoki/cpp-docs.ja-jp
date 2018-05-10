---
title: 3.2 ロック関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd788b0ef1c72b1f38a44ee608ce0c7760e24adc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="32-lock-functions"></a>3.2 ロック関数
このセクションで説明した関数では、同期に使用されるロックを操作します。  
  
 ロック変数、次の関数の型である必要があります**omp_lock_t**です。 この変数は、これらの関数を介してのみアクセスできる必要があります。 すべてのロック関数へのポインターを持つ引数を必要と**omp_lock_t**型です。  
  
-   `omp_init_lock`関数は、単純ロックを初期化します。  
  
-   `omp_destroy_lock`関数は、単純なロックを解除します。  
  
-   `omp_set_lock`関数は、単純なロックが使用できるまで待機します。  
  
-   `omp_unset_lock`関数は、単純ロックを解放します。  
  
-   `omp_test_lock`関数は、単純なロックをテストします。  
  
 ロック変数、次の関数の型である必要があります**omp_nest_lock_t**です。  この変数は、これらの関数を介してのみアクセスできる必要があります。 入れ子にできるロックのすべての関数へのポインターを持つ引数を必要と**omp_nest_lock_t**型です。  
  
-   `omp_init_nest_lock`関数は入れ子にできるロックを初期化します。  
  
-   `omp_destroy_nest_lock`関数が入れ子にできるロックを解除します。  
  
-   `omp_set_nest_lock`関数は、入れ子にできるロックが使用できるまで待機します。  
  
-   `omp_unset_nest_lock`関数が入れ子にできるロックを解放します。  
  
-   `omp_test_nest_lock`関数は入れ子にできるロックをテストします。  
  
 OpenMP ロック関数は、このような形を常に読み取り、更新ロック変数の最新の値でロック変数にアクセスします。 したがって、OpenMP プログラムの明示的なを含める必要はありません**フラッシュ**ロック変数の値が別のスレッド間で一貫性のあることを確認するためのディレクティブ。 (の必要性がある可能性があります**フラッシュ**ディレクティブを他の変数の値の一貫性が維持されます)。