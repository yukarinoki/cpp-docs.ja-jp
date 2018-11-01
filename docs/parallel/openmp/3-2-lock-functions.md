---
title: 3.2 ロック関数
ms.date: 11/04/2016
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
ms.openlocfilehash: c189ba5b1f0bb365b387b4b4b887cfdb74d1bf2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573070"
---
# <a name="32-lock-functions"></a>3.2 ロック関数

このセクションで説明した関数では、同期に使用されるロックを操作します。

ロックの変数、次の関数の型である必要があります**omp_lock_t**します。 この変数は、これらの関数からのみアクセスする必要があります。 ポインターを持つ引数を必要とするすべてのロック関数**omp_lock_t**型。

- `omp_init_lock`関数は、単純なロックを初期化します。

- `omp_destroy_lock`関数は、単純なロックを削除します。

- `omp_set_lock`関数は、単純なロックが使用できるまで待機します。

- `omp_unset_lock`関数は、単純なロックを解放します。

- `omp_test_lock`関数は、単純なロックをテストします。

ロックの変数、次の関数の型である必要があります**omp_nest_lock_t**します。  この変数は、これらの関数からのみアクセスする必要があります。 ポインターを持つ引数を必要とするすべての入れ子にできるロック関数**omp_nest_lock_t**型。

- `omp_init_nest_lock`関数を入れ子にできるロックを初期化します。

- `omp_destroy_nest_lock`関数が入れ子にできるロックを削除します。

- `omp_set_nest_lock`関数が入れ子にできるロックが使用できるまでに待機します。

- `omp_unset_nest_lock`関数が入れ子にできるロックを解放します。

- `omp_test_nest_lock`関数は入れ子にできるロックをテストします。

OpenMP のロック関数が常に読み取りをロック変数の最新の値を更新方法でロック変数にアクセスします。 そのため、OpenMP プログラムの明示的なを含める必要はありません**フラッシュ**ロック変数の値が別のスレッド間で一貫性のあることを確認するためのディレクティブ。 (必要である可能性があります**フラッシュ**ディレクティブを一貫性のあるその他の変数の値を作成します)。