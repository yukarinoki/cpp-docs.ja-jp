---
title: F. 新機能とバージョン 2.0 では説明 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e48f299e66ed1b4c075757a9cd143d0afe897db
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693144"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. 新機能とバージョン 2.0 の説明
この付録の内容は、バージョン 1.0 からバージョン 2.0 に移行する際、OpenMP C と C++ 仕様に加えられた主な変更点をまとめたものです。 次の項目は、仕様に追加された新機能を示します。  
  
-   OpenMP ディレクティブにコンマを使用できる ([セクション 2.1](../../parallel/openmp/2-1-directive-format.md)ページ 7 で)。  
  
-   追加、`num_threads`句。 この句を使用するユーザーは、parallel コンストラクトのスレッド数が特定の要求 ([セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの)。  
  
-   `threadprivate`ディレクティブが静的ブロック スコープ変数を受け入れるように拡張されて ([セクション 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md)ページ 23)。  
  
-   C99 可変長配列は完全な型したがってを指定する任意の場所完全な型は許可されているのインスタンスの一覧に`private`、 `firstprivate`、および`lastprivate`句 ([セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) [25] ページ)。  
  
-   並行領域内のプライベート変数マークできるは、入れ子になったディレクティブでもう一度プライベート ([セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) [25] ページ)。  
  
-   `copyprivate`句が追加されました。 他のメンバーにチームの 1 つのメンバーから値をブロードキャストするプライベート変数を使用するためのメカニズムを提供します。 このような共有変数を提供することは困難 (たとえば、レベルごとに異なる変数を必要とする再帰) がある場合に、値の共有変数を使用する代わりにすることをお勧めします。 `copyprivate`句でのみ使用できます、**単一**ディレクティブ ([セクション 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) [32] ページ)。  
  
-   タイミング ルーチンの加算`omp_get_wtick`と`omp_get_wtime`MPI ルーチンに似ています。 これらの関数はウォール クロックを実行するために必要な ([セクション 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md)ページ 44 と[セクション 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) 45 ページで)。  
  
-   OpenMP C と C++ の実装で定義される動作の一覧を付録が追加されました。 実装を定義して、ドキュメントのこのような場合は、その動作に必要な ([付録 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md)ページ 97 で)。  
  
-   次の変更の提供を明確にするか、C と C++ の以前の OpenMP API 仕様の機能を修正します。  
  
    -   明確にされましたの動作`omp_set_nested`と`omp_set_dynamic`とき`omp_in_parallel`0 以外を返しますが定義されていません ([セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39、ページ上および[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページの)。  
  
    -   入れ子になった並列を使用する場合は、ディレクティブの入れ子を明確にされました。 ([セクション 2.9](../../parallel/openmp/2-9-directive-nesting.md) 33 ページ上)。  
  
    -   並列領域で、ロックの初期化関数とロック破棄関数を呼び出すことができる ([セクション 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md)ページ 42 でと[セクション 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md)ページ 42 で)。  
  
    -   新しい例が追加されました ([付録 A](../../parallel/openmp/a-examples.md) 51 ページ)。