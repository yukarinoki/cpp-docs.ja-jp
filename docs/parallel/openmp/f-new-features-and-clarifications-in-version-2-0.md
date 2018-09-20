---
title: F. 新機能とバージョン 2.0 の説明 |Microsoft Docs
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
ms.openlocfilehash: d15cbbf60609208a200bd73536d0ebdc8a714f7e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373504"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. 新機能とバージョン 2.0 の説明

この付録では、OpenMP C と C++ 仕様バージョン 1.0 からバージョン 2.0 に移行する際に変更をまとめたものです。 次の項目は、仕様に追加された新機能を示します。

- OpenMP ディレクティブにコンマを使用できる ([セクション 2.1](../../parallel/openmp/2-1-directive-format.md) 7 ページ)。

- 追加、`num_threads`句。 この句は、ユーザーは、parallel コンストラクトのスレッド数が特定の要求を使用できます ([セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) [8] ページ)。

- `threadprivate`静的ブロック スコープ変数を受け入れるように拡張されたディレクティブ ([セクション 2.7.1](../../parallel/openmp/2-7-1-threadprivate-directive.md) 23 ページ上)。

- C99 可変長配列は完全な型、され、したがって指定できます任意の場所完全な型は許可されて、インスタンスの一覧で`private`、 `firstprivate`、および`lastprivate`句 ([セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページ上)。

- 並列領域内のプライベート変数は、入れ子になったディレクティブにもう一度プライベート マークできます ([セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 ページ上)。

- `copyprivate`句が追加されました。 これは、プライベート変数を使用して、他のメンバーにチームの 1 つのメンバーから値をブロードキャストするメカニズムを提供します。 このような共有変数を提供するが難しい (たとえばの各レベルで別の変数を必要とする再帰) ときに、値の共有変数を使用する代わりにすることをお勧めします。 `copyprivate`句にのみ表示できる、**単一**ディレクティブ ([セクション 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) [32] ページ)。

- タイミング ルーチンの加算`omp_get_wtick`と`omp_get_wtime`MPI ルーチンに似ています。 これらの関数がウォール クロックのタイミングを実行するために必要な ([セクション 3.3.1](../../parallel/openmp/3-3-1-omp-get-wtime-function.md) 44 ページで、[のセクション 3.3.2](../../parallel/openmp/3-3-2-omp-get-wtick-function.md) 45 ページ)。

- OpenMP C/C の実装で定義された動作の一覧が付録が追加されました。 実装が定義し、このような場合は、その動作を文書化するために必要 ([付録 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md) 97 ページ上)。

- 明確にまたは C と C++ の以前の OpenMP API 仕様の機能を修正するには、次の変更を果たします。

   - 明確にされましたの動作`omp_set_nested`と`omp_set_dynamic`とき`omp_in_parallel`返します 0 以外の値が定義されて ([セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページと[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページの)。

   - 入れ子になった並列を使用する場合は、ディレクティブの入れ子を明記しました ([セクション 2.9](../../parallel/openmp/2-9-directive-nesting.md) 33 ページ上)。

   - 並列領域で、ロックの初期化とロック破棄関数を呼び出すことができます ([セクション 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 42 ページと[セクション 3.2.2](../../parallel/openmp/3-2-2-omp-destroy-lock-and-omp-destroy-nest-lock-functions.md) 42 ページ上)。

   - 新しいサンプルが追加されています ([付録 A](../../parallel/openmp/a-examples.md) 51 ページ)。