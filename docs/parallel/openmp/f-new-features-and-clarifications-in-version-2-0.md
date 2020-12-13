---
description: 詳細については、「F」を参照してください。バージョン2.0 の新機能と説明
title: F. Version 2.0 の新機能と説明
ms.date: 01/22/2019
ms.assetid: 0d4beb66-f2d5-468c-8cd3-4b00dcbab061
ms.openlocfilehash: 77a27ed6d15986f787297b37a904d4625d649ced
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342466"
---
# <a name="f-new-features-and-clarifications-in-version-20"></a>F. Version 2.0 の新機能と説明

この付録では、バージョン1.0 からバージョン2.0 に移行するときに、OpenMP C/c + + 仕様に加えられた主変更の概要を示します。 次の項目は、仕様に追加された新機能です。

- OpenMP [ディレクティブ](2-directives.md#21-directive-format)ではコンマを使用できます。

- 句の追加 `num_threads` 。 この句を使用すると、ユーザーは [parallel コンストラクト](2-directives.md#23-parallel-construct)に特定の数のスレッドを要求できます。

- [Threadprivate](2-directives.md#271-threadprivate-directive)ディレクティブが拡張され、静的ブロックスコープ変数を受け入れるようになりました。

- C99 可変長配列は完全な型であり、、、および句のリストなど、完全な型を任意に指定でき `private` `firstprivate` `lastprivate` ます (「 [」セクション 2.7.2](2-directives.md#272-data-sharing-attribute-clauses)を参照)。

- 並列領域のプライベート変数は、入れ子になったディレクティブで再び [private](2-directives.md#2721-private) としてマークできます。

- `copyprivate`句が追加されました。 プライベート変数を使用して、チームのあるメンバーから他のメンバーに値をブロードキャストするメカニズムを提供します。 このような共有変数を指定する場合は、共有変数を値として使用するのが難しい場合があります (たとえば、各レベルで異なる変数を必要とする再帰の場合など)。 [Copyprivate](2-directives.md#2728-copyprivate)句は、ディレクティブでのみ使用でき `single` ます。

- タイミングルーチンの追加 [omp_get_wtick](3-run-time-library-functions.md#332-omp_get_wtick-function) と [omp_get_wtime](3-run-time-library-functions.md#331-omp_get_wtime-function) MPI ルーチンに似ています。 これらの関数は、ウォールクロックのタイミングを実行するために必要です。

- OpenMP C/c + + で [実装定義の動作](e-implementation-defined-behaviors-in-openmp-c-cpp.md) の一覧を含む付録が追加されました。 このような場合は、実装を定義し、その動作を文書化する必要があります。

- 次の変更は、C/c + + の前の OpenMP API 仕様の機能を明確または修正するために役立ちます。

  - が0以外の値を返すときの [omp_set_nested](3-run-time-library-functions.md#319-omp_set_nested-function) および [omp_set_dynamic](3-run-time-library-functions.md#317-omp_set_dynamic-function) の動作が未定義であることが明確にされてい `omp_in_parallel` ます。

  - 入れ子になった並列を使用するときの [ディレクティブの入れ子](2-directives.md#29-directive-nesting) を明確にします。

  - [ロックの初期化](3-run-time-library-functions.md#321-omp_init_lock-and-omp_init_nest_lock-functions)関数と[ロック破棄](3-run-time-library-functions.md#322-omp_destroy_lock-and-omp_destroy_nest_lock-functions)関数は、並列領域で呼び出すことができます。

  - [付録 a](a-examples.md)に新しい例が追加されました。
