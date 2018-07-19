---
title: OpenMP から同時実行ランタイムへの移行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 16e10287526e6b815ba56183a8e3d590102507aa
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690489"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP から同時実行ランタイムへの移行
同時実行ランタイムでは、さまざまなプログラミング モデルを使用できます。 これらのモデルは、他のライブラリのモデルと重複する場合や、他のライブラリのモデルを補完する場合があります。 このドキュメントのセクション比較[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)同時実行ランタイムにし、同時実行ランタイムを使用する既存の OpenMP コードを移行する方法について例を示します。  
  
 OpenMP プログラミング モデルは、オープン標準により定義されており、Fortran および C/C++ プログラミング言語へのバインドが適切に定義されています。 OpenMP version 2.0 および 2.5 では、Visual C コンパイラでサポートされているは反復的な; は、並列アルゴリズムに最適つまり、並列反復処理をデータの配列を実行します。 OpenMP 3.0 では、反復的なタスクに加え、非反復的なタスクをサポートします。  
  
 OpenMP は、並列化の度合いが事前に決定され、システムで使用可能なリソースと対応する場合に最も効果的です。 OpenMP モデルは、高パフォーマンス コンピューティングに特に適したが非常に大規模な計算問題は、1 台のコンピューターの処理リソースを分散します。 このシナリオでハードウェア環境が一般的に固定であり、開発者は、アルゴリズムを実行すると、すべてのコンピューティング リソースに対する排他アクセスを持ちますを予測できます。  
  
 ただし、制約付きのコンピューティング環境以下できない可能性があります OpenMP のとよく一致します。 たとえば、(クイック ソート アルゴリズムやデータのツリーを検索) の再帰的な問題は OpenMP 2.0 および 2.5 を使用して実装することは困難です。 同時実行ランタイムを提供することによって、OpenMP の機能を補完、[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)と[並列パターン ライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md)(PPL)。 非同期エージェント ライブラリは、タスクの粒度の粗い並列処理をサポートしています。PPL では、複数の粒度の細かい並列タスクをサポートします。 同時実行ランタイムでは、アプリケーションのロジックに集中できるように、操作を並列で実行に必要なインフラストラクチャを提供します。 ただし、同時実行ランタイムには、さまざまなプログラミング モデルができますが、そのによるスケジューリング オーバーヘッドはより大きくなります OpenMP などの他の同時実行ライブラリです。 そのため、同時実行ランタイムを使用する既存の OpenMP コードを変換するときに増分パフォーマンスをテストすることをお勧めします。  
  
## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP から同時実行ランタイムに移行するときに  
 次の場合に、同時実行ランタイムを使用する既存の OpenMP コードを移行すると便利な場合があります。  
  
|Cases|同時実行ランタイムの利点|  
|-----------|-------------------------------------------|  
|拡張可能な同時実行プログラミング フレームワークが必要です。|同時実行ランタイムの機能の多くは拡張できます。 既存の機能を組み合わせて新しい機能を作成することもできます。 OpenMP では、コンパイラ ディレクティブを使用して、ため、簡単に拡張できません。|  
|アプリケーションを協調ブロッキングを享受できます。|タスクがブロックされていない使用可能なリソースが必要とするため、同時実行ランタイムは、最初のタスクがリソースを待機中に、この他のタスクを実行できます。|  
|動的負荷分散から得られるとします。|同時実行ランタイムでは、ワークロードの変化に応じてコンピューティング リソースの割り当てが調整されるスケジューリング アルゴリズムを使用します。 OpenMP でスケジューラは、並行領域にコンピューティング リソースを割り当てます場合、それらのリソース割り当ては、計算全体で固定されます。|  
|例外処理のサポートが必要です。|PPL では、両方の内部と外部並列領域またはループの例外をキャッチすることができます。 OpenMP では、並列領域またはループ内で例外を処理する必要があります。|  
|取り消し機構が必要です。|Ppl では、個々 のタスクと作業の並列のツリーの両方をキャンセルするアプリケーションを使用します。 OpenMP には、アプリケーションの独自のキャンセル メカニズムを実装する必要があります。|  
|開始元となるさまざまなコンテキストで終了する並列コードを必要とします。|同時実行ランタイムでは、タスクを 1 つのコンテキストでは、開始を待機し、別のコンテキストでそのタスクをキャンセルすることができます。 OpenMP では、すべての並列処理は、開始元のコンテキストで終了しなければなりません。|  
|デバッグ サポートの強化を必要とします。|Visual Studio では、**並列スタック**と**並列タスク**windows マルチ スレッド アプリケーションのデバッグをより簡単にできます。<br /><br /> 同時実行ランタイムのデバッグをサポートの詳細については、次を参照してください[タスク ウィンドウを使用して](/visualstudio/debugger/using-the-tasks-window)、[並列スタック ウィンドウを使用して](/visualstudio/debugger/using-the-parallel-stacks-window)、および[チュートリアル: 並列のデバッグ。アプリケーション](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)です。|  
  
## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP から同時実行ランタイムへの移行をしない場合  
 次の場合は、同時実行ランタイムを使用する既存の OpenMP コードを移行する適切ないる可能性がない場合について説明します。  
  
|Cases|説明|  
|-----------|-----------------|  
|アプリケーションで既にでは、お客様の要件を満たしています。|アプリケーションのパフォーマンスと現在のデバッグのサポートに満足したら、移行は適切なできない可能性があります。|  
|並列ループの本体は、ほとんどの作業を実行します。|同時実行ランタイムのタスク スケジューラのオーバーヘッドがない問題に対処並列実行されるループの本体、特にループの本体が比較的小さい場合の利点です。|  
|アプリケーションが c 言語で記述されました。|同時実行ランタイムでは、多くの C++ の機能を使用するために適さない場合がありますを完全に使用する C アプリケーションを有効にするコードを記述することはできません。|  
  
## <a name="related-topics"></a>関連トピック  
 [方法: OpenMP の parallel for ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)  

 OpenMP を使用する基本的なループを指定された[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)と[の](../../parallel/openmp/reference/for-openmp.md)ディレクティブは、同時実行ランタイムを使用するように変換する方法を示します[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムです。  

  
 [方法: キャンセル処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)  
 OpenMP を与え[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[の](../../parallel/openmp/reference/for-openmp.md)ループを実行するすべての反復処理を必要としませんが、同時実行ランタイムの取り消し機構を使用するように変換する方法を示します。  
  
 [方法: 例外処理を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that uses-exception-handling.md)  
 OpenMP を与え[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[の](../../parallel/openmp/reference/for-openmp.md)例外処理を実行するループが、同時実行ランタイムの例外処理メカニズムを使用するように変換する方法を示します。  
  
 [方法: 減少変数を使用する OpenMP ループを変換し、同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)  
 OpenMP を与え[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[の](../../parallel/openmp/reference/for-openmp.md)ループを使用する、[削減](../../parallel/openmp/reference/reduction.md)句は、同時実行ランタイムを使用するように変換する方法を示します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)   
 [OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)   
 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)   
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)

