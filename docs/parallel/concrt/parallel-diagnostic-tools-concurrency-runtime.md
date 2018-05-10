---
title: 並列診断ツール (同時実行ランタイム) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Parallel Diagnostic Tools [Concurrency Runtime]
ms.assetid: b1a3f1d2-f5df-4f29-852e-906b3d8341fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cd3ce4c86332719e299c11fee3ffbee8b41c14f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>並列診断ツール (同時実行ランタイム)
[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] は、マルチ スレッド アプリケーションのデバッグおよびプロファイリングを広範にサポートします。  
  
## <a name="debugging"></a>デバッグ  
 Visual Studio デバッガーには、**並列スタック**ウィンドウで、**並列タスク**ウィンドウ、および**並列ウォッチ**ウィンドウです。 詳細については、次を参照してください。[チュートリアル: 並行アプリケーションのデバッグ](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)と[する方法: 並列ウォッチ ウィンドウを使用して](/visualstudio/debugger/how-to-use-the-parallel-watch-window)です。  
  
## <a name="profiling"></a>プロファイル  
 プロファイリング ツールでは、マルチ スレッド アプリケーションで、それ自体とその他のプログラムがどのようにやり取りする方法に関する情報をグラフィカルな表形式、数値を表示する次の 3 つのデータ ビューを提供します。 ビューは、使用すると、重要な領域をすばやく識別され、呼び出し履歴のグラフィック表示上のポイントから移動する、サイト、およびソース コードを呼び出します。 詳細については、「[同時実行ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)」を参照してください。  
  
## <a name="event-tracing"></a>イベントのトレース  
 同時実行ランタイムを使用して[Event Tracing for Windows](http://msdn.microsoft.com/library/windows/desktop/bb968803) (ETW) にさまざまなイベントが発生したときに、プロファイラーなどのインストルメンテーション ツールを通知します。 これらのイベントなどのスケジューラがアクティブ化または非アクティブ化されたときにコンテキストを開始、終了、ブロック、ブロックを解除すると、または生成すると、ときに、並列アルゴリズムを開始または終了するとします。  
  
 などのツール、[同時実行ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)この機能を利用してです。 したがって、通常がありませんこれらのイベントを直接操作します。 ただし、これらのイベントは、カスタムのプロファイラーを開発する場合または役立ちますなど、イベント トレース ツールを使用すると[Xperf](http://go.microsoft.com/fwlink/p/?linkid=160628)です。  
  
 同時実行ランタイムでは、トレースが有効になっている場合にのみ、これらのイベントを発生させます。 呼び出す、 [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing)イベントのトレースを有効にする関数、および[concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing)トレースを無効にする関数。  
  
 次の表では、イベントのトレースが有効にすると、ランタイムを発生させるイベントについて説明します。  
  
|event|説明|[値]|  
|-----------|-----------------|-----------|  

|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|同時実行ランタイムの ETW プロバイダーの識別子 |。`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|コンテキストに関連付けられているイベントをマークします |。`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|マークの入口と出口への呼び出しを[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムです |。`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|マークの入口と出口への呼び出しを[concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムです |。`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|マークの入口と出口への呼び出しを[concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムです |。`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|関連付けられているイベントをマーク、[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|。`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|仮想プロセッサに関連付けられているイベントをマークします |。`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 同時実行ランタイムが定義されているさせません現在、次のイベントです。 ランタイムは、将来使用するため、これらのイベントを予約します。  
  
-   [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 [Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype)列挙体は、イベントを追跡できる操作を指定します。 開始位置などで、`parallel_for`アルゴリズム、ランタイムを発生させます、`PPLParallelForEventGuid`イベントを示し、`CONCRT_EVENT_START`操作とします。 前に、`parallel_for`アルゴリズムが返されるは、ランタイムは再度を発生させる、`PPLParallelForEventGuid`イベントを示し、`CONCRT_EVENT_END`操作として。  
  
 次の例への呼び出しのトレースを有効にする方法を示しています。`parallel_for`です。 ランタイムは、最初の呼び出しをトレースしないように`parallel_for`トレースが有効になっていないためです。 呼び出し`EnableTracing`、ランタイムに 2 番目の呼び出しのトレースを`parallel_for`です。  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 ランタイムを呼び出す回数を追跡する`EnableTracing`と`DisableTracing`です。 そのため、呼び出す場合は、 `EnableTracing` 、複数回呼び出す必要があります`DisableTracing`トレースを無効にするために、同じ回数。  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)

