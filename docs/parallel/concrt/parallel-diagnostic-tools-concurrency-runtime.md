---
title: 並列診断ツール (同時実行ランタイム) |Microsoft Docs
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
ms.openlocfilehash: bb41f9630e22d9067743b106aed49ea9c51ee4ae
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541611"
---
# <a name="parallel-diagnostic-tools-concurrency-runtime"></a>並列診断ツール (同時実行ランタイム)
Visual Studio は、マルチ スレッド アプリケーションのデバッグおよびプロファイリングを広範にサポートします。  
  
## <a name="debugging"></a>デバッグ  
 Visual Studio デバッガーに、**並列スタック**ウィンドウで、**並列タスク**ウィンドウ、および**並列ウォッチ**ウィンドウ。 詳細については、次を参照してください。[チュートリアル: 並行アプリケーションのデバッグ](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)と[方法: 並列ウォッチ ウィンドウを使用して、](/visualstudio/debugger/how-to-use-the-parallel-watch-window)します。  
  
## <a name="profiling"></a>プロファイル  
 プロファイリング ツールは、マルチ スレッド アプリケーションで、自体とその他のプログラムがどのように対話する方法についてのグラフィカルな表形式、数値の情報を表示する 3 つのデータ ビューを提供します。 ビューは、関心のある領域をすばやく識別するを有効にし、呼び出し履歴、グラフィック表示上のポイントから移動するサイト、およびソース コードを呼び出します。 詳細については、「[同時実行ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)」を参照してください。  
  
## <a name="event-tracing"></a>イベントのトレース  
 同時実行ランタイムを使用して[Windows のイベント トレース](http://msdn.microsoft.com/library/windows/desktop/bb968803)(ETW) にさまざまなイベントが発生したときに、プロファイラーなどのインストルメンテーション ツールを通知します。 これらのイベントには、並列アルゴリズムを開始または停止時にスケジューラがアクティブまたは非アクティブ化されたときに、コンテキストを開始、終了、ブロック、ブロックを解除すると、または結果とが含まれます。  
  
 などのツール、[同時実行ビジュアライザー](/visualstudio/profiling/concurrency-visualizer)は、この機能を利用し、そのため、通常がありませんこれらのイベントを直接使用します。 ただし、これらのイベントは便利なカスタム プロファイラーを開発するときまたはなど、イベント トレース ツールを使用すると[Xperf](http://go.microsoft.com/fwlink/p/?linkid=160628)します。  
  
 同時実行ランタイムは、トレースが有効になっている場合にのみ、これらのイベントを発生させます。 呼び出す、 [concurrency::EnableTracing](reference/concurrency-namespace-functions.md#enabletracing)関数イベントのトレースを有効にして、 [concurrency::DisableTracing](reference/concurrency-namespace-functions.md#disabletracing)トレースを無効にする関数。  
  
 次の表では、イベントのトレースが有効にすると、ランタイムを発生させるイベントについて説明します。  
  
|event|説明|[値]|  
|-----------|-----------------|-----------|  

|[concurrency::ConcRT_ProviderGuid](reference/concurrency-namespace-constants1.md#concrt_providerguid)|同時実行ランタイムの ETW プロバイダーの識別子 |。`f7b697a3-4db5-4d3b-be71-c4d284e6592f`|  
|[concurrency::ContextEventGuid](reference/concurrency-namespace-constants1.md#contexteventguid)|コンテキストに関連するイベントをマークします |。`5727a00f-50be-4519-8256-f7699871fecb`|  
|[concurrency::PPLParallelForEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeventguid)|マークの入口と出口の呼び出しを[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズム |。`31c8da6b-6165-4042-8b92-949e315f4d84`|  
|[concurrency::PPLParallelForeachEventGuid](reference/concurrency-namespace-constants1.md#pplparallelforeacheventguid)|マークの入口と出口の呼び出しを[concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズム |。`5cb7d785-9d66-465d-bae1-4611061b5434`|  
|[concurrency::PPLParallelInvokeEventGuid](reference/concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|マークの入口と出口の呼び出しを[concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズム |。`d1b5b133-ec3d-49f4-98a3-464d1a9e4682`|  
|[concurrency::SchedulerEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)|マークに関連するイベント、[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)|。`e2091f8a-1e0a-4731-84a2-0dd57c8a5261`|  
|[concurrency::VirtualProcessorEventGuid](reference/concurrency-namespace-constants1.md#virtualprocessoreventguid)|仮想プロセッサに関連するイベントをマークします |。`2f27805f-1676-4ecc-96fa-7eb09d44302f`|  
  
 同時実行ランタイムを定義すると、現在発生させません、次のイベント。 ランタイムでは、将来使用するため、これらのイベントは予約されます。  
  
-   [concurrency::ConcRTEventGuid](reference/concurrency-namespace-constants1.md#concrteventguid)  
  
-   [concurrency::ScheduleGroupEventGuid](reference/concurrency-namespace-constants1.md#schedulereventguid)  
  
-   [concurrency::ChoreEventGuid](reference/concurrency-namespace-constants1.md#choreeventguid)  
  
-   [concurrency::LockEventGuid](reference/concurrency-namespace-constants1.md#lockeventguid)  
  
-   [concurrency::ResourceManagerEventGuid](reference/concurrency-namespace-constants1.md#resourcemanagereventguid)  
  
 [Concurrency::ConcRT_EventType](reference/concurrency-namespace-enums.md#concrt_eventtype)列挙可能なイベントを追跡する操作を指定します。 開始時など、`parallel_for`アルゴリズム、ランタイムを発生させます、`PPLParallelForEventGuid`イベントを示し、`CONCRT_EVENT_START`操作として。 前に、`parallel_for`アルゴリズムを返します、ランタイムが再度発生させる、`PPLParallelForEventGuid`イベントを示し、`CONCRT_EVENT_END`操作として。  
  
 次の例への呼び出しのトレースを有効にする方法を示しています。`parallel_for`します。 ランタイムは最初の呼び出しをトレースしません`parallel_for`トレースが有効になっていないためです。 呼び出し`EnableTracing`により、2 番目の呼び出しをトレースするランタイム`parallel_for`します。  
  
 [!code-cpp[concrt-etw#1](../../parallel/concrt/codesnippet/cpp/parallel-diagnostic-tools-concurrency-runtime_1.cpp)]  
  
 ランタイムを呼び出す回数を追跡する`EnableTracing`と`DisableTracing`します。 そのため、呼び出す場合`EnableTracing`呼び出す必要があります、数回`DisableTracing`トレースを無効にするには、同じ回数。  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイム](../../parallel/concrt/concurrency-runtime.md)

