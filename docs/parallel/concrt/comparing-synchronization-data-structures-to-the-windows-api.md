---
title: Windows API の同期データ構造との比較 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- synchronization data structures, compared to Windows API
- event class, example
ms.assetid: 8b0b1a3a-ef80-408c-91fa-93e6af920b4e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb6dc90a272c8e288a4370ae18ad3d1fda150eed
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197549"
---
# <a name="comparing-synchronization-data-structures-to-the-windows-api"></a>同期データ構造と Windows API の比較
ここでは、同時実行ランタイムが提供する同期データ構造と Windows API が提供する同期データ構造の動作を比較します。  
  
 同時実行ランタイムによって提供される同期データ構造に従って、*協調スレッド処理モデル*します。 協調スレッド処理モデルでは、同期プリミティブは処理リソースを他のスレッドに明示的に譲渡します。 これに対し、*プリエンプティブ スレッド処理モデル*制御スケジューラまたはオペレーティング システムによって、処理リソースを他のスレッドに転送されます場所、します。  
  
## <a name="criticalsection"></a>critical_section  
 [Concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md) 、Windows と似ています`CRITICAL_SECTION`のため、1 つのプロセスのスレッドでのみ使用できます。 Windows API のクリティカル セクションの詳細については、次を参照してください。[クリティカル セクション オブジェクト](/windows/desktop/Sync/critical-section-objects)します。  
  
## <a name="readerwriterlock"></a>reader_writer_lock  
 [:Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)クラスが Windows のスリム リーダー/ライター (SRW) ロックに似ています。 類似点と相違点を次の表に示します。  
  
|機能|`reader_writer_lock`|SRW ロック|  
|-------------|--------------------------|--------------|  
|再入不可能|[はい]|[はい]|  
|リーダーをライターに昇格 (アップグレード サポート)|いいえ|いいえ|  
|ライターをリーダーに降格 (ダウングレード サポート)|いいえ|いいえ|  
|書き込み優先ロック|[はい]|いいえ|  
|ライターへの FIFO アクセス|[はい]|いいえ|  
  
 SRW ロックの詳細については、次を参照してください。[スリム リーダー/ライター (SRW) ロック](https://msdn.microsoft.com/library/windows/desktop/aa904937)プラットフォーム SDK に含まれています。  
  
## <a name="event"></a>event  
 [Concurrency::event](../../parallel/concrt/reference/event-class.md)名前のない Windows 手動リセット イベントと似ています。 ただし、`event` オブジェクトは協調して動作しますが、Windows イベントはプリエンプティブに動作します。 Windows イベントの詳細については、次を参照してください。[イベント オブジェクト](/windows/desktop/Sync/event-objects)します。  
  
## <a name="example"></a>例  
  
### <a name="description"></a>説明  
 `event` クラスと Windows イベントの相違点をより詳しく理解するために、次の例について考えてみましょう。 この例により、スケジューラは最大で 2 つの同時タスクを作成した後、`event` クラスと Windows 手動リセット イベントを使用する 2 つの類似した関数を呼び出すことができます。 各関数は、まず共有イベントがシグナル状態になるのを待機する複数のタスクを作成します。 次に、実行中のタスクに制御を渡し、イベントに通知します。 その後、各関数はシグナル状態イベントを待機します。  
  
### <a name="code"></a>コード  
 [!code-cpp[concrt-event-comparison#1](../../parallel/concrt/codesnippet/cpp/comparing-synchronization-data-structures-to-the-windows-api_1.cpp)]  
  
### <a name="comments"></a>コメント  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
Cooperative event:  
    Context 0: waiting on an event.  
    Context 1: waiting on an event.  
    Context 2: waiting on an event.  
    Context 3: waiting on an event.  
    Context 4: waiting on an event.  
    Setting the event.  
    Context 5: received the event.  
    Context 6: received the event.  
    Context 7: received the event.  
    Context 8: received the event.  
    Context 9: received the event.  
Windows event:  
    Context 10: waiting on an event.  
    Context 11: waiting on an event.  
    Setting the event.  
    Context 12: received the event.  
    Context 14: waiting on an event.  
    Context 15: received the event.  
    Context 16: waiting on an event.  
    Context 17: received the event.  
    Context 18: waiting on an event.  
    Context 19: received the event.  
    Context 13: received the event.  
```  
  
 `event` クラスは協調して動作するため、イベントがシグナル状態になるのを待機している場合、スケジューラは処理リソースを別のコンテキストに再割り当てすることができます。 したがって、`event` クラスを使用するバージョンで、より多くの作業が実行されます。 Windows イベントを使用するバージョンでは、待機中の各タスクは次のタスクが開始される前にシグナル状態になる必要があります。  
  
 タスクの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
## <a name="see-also"></a>関連項目  
 [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)
