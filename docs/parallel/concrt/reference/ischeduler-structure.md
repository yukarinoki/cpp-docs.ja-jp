---
title: IScheduler 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c78d02ccd5639369ad8b4d0183458da2ba85269
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ischeduler-structure"></a>IScheduler 構造体
作業スケジューラの抽象化のインターフェイスです。 同時実行ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。  
  
## <a name="syntax"></a>構文  
  
```
struct IScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|使用のため、仮想プロセッサ ルートのセットをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラの代わりの作業を実行できる 1 つのスレッドを実行する権限を表します。|  
|[IScheduler::GetId](#getid)|スケジューラの一意の識別子を返します。|  
|[IScheduler::GetPolicy](#getpolicy)|スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)です。|  
|[Ischeduler::notifyresourcesexternallybusy](#notifyresourcesexternallybusy)|この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラで使用されているようになりました。|  
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。|  
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。|  
|[IScheduler::Statistics](#statistics)|タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーとの通信を行うカスタム スケジューラを実装している場合は、実装を提供する必要があります、`IScheduler`インターフェイスです。 このインターフェイスは、双方向チャネル スケジューラおよびリソース マネージャー間の通信の一方の端です。 もう一方の end がによって表される、`IResourceManager`と`ISchedulerProxy`リソース マネージャーによって実装されるインターフェイス。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="addvirtualprocessors"></a>  Ischeduler::addvirtualprocessors メソッド  
 使用のため、仮想プロセッサ ルートのセットをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラの代わりの作業を実行できる 1 つのスレッドを実行する権限を表します。  
  
```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`スケジューラに追加されている仮想プロセッサを表すインターフェイスのルートです。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを起動、`AddVirtualProcessor`スケジューラへの仮想プロセッサ ルートの初期セットを許可するメソッド。 スケジューラ間でリソースが再分配するときに、仮想プロセッサ ルートをスケジューラに追加するメソッドを呼び出すことも、します。  
  
##  <a name="getid"></a>  Ischeduler::getid メソッド  
 スケジューラの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 一意の整数識別子。  
  
### <a name="remarks"></a>コメント  
 使用する必要があります、 [GetSchedulerId](concurrency-namespace-functions.md)を実装するオブジェクトの一意の識別子を取得する関数、`IScheduler`インターフェイス、メソッドのパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでを指定します。 同じ識別子を返している必要がときに、`GetId`関数が呼び出されます。  
  
 未定義の動作は、別のソースから取得した識別子の可能性があります。  
  
##  <a name="getpolicy"></a>  Ischeduler::getpolicy メソッド  
 スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)です。  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラのポリシーのコピー。  
  
##  <a name="notifyresourcesexternallybusy"></a>  Ischeduler::notifyresourcesexternallybusy メソッド  
 この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラで使用されているようになりました。  
  
```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を他のスケジューラになった使用中のハードウェア スレッドに関連付けられているインターフェイス。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 同時に複数のスケジューラに割り当てられる特定のハードウェア スレッドのことができます。 この理由の 1 つは、されていないこと十分なハードウェア スレッド リソースを共有せずにすべてのスケジューラでは、最小同時実行性を満たすためにシステムの可能性があります。 別の方法としては、リソースが所有しているスケジューラを使用しない場合、それらの非アクティブ化するハードウェア スレッド上のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的にです。  
  
 ハードウェア スレッドのサブスクリプション レベルがサブスクライブしているスレッドの数で示され、そのハードウェア スレッドに関連付けられた仮想プロセッサ ルートをアクティブ化します。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルは、正の値にゼロから離れるときに、スケジューラにリソースが外部でビジー状態になる通知が送信されます。  
  
 スケジューラ ポリシーを持つにはこの方法で通知が送信のみ場所の値、`MinConcurrency`ポリシー キーがの値と等しい、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)です。  
  
 通知用資格のあるスケジューラを取得初期通知のセットが作成されるときにだけに割り当てられているリソースが外部でビジー状態かアイドル状態かどうかを示すことです。  
  
##  <a name="notifyresourcesexternallyidle"></a>  Ischeduler::notifyresourcesexternallyidle メソッド  
 この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。  
  
```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を他のスケジューラがアイドル状態になるハードウェア スレッドに関連付けられているインターフェイス。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 同時に複数のスケジューラに割り当てられる特定のハードウェア スレッドのことができます。 この理由の 1 つは、されていないこと十分なハードウェア スレッド リソースを共有せずにすべてのスケジューラでは、最小同時実行性を満たすためにシステムの可能性があります。 別の方法としては、リソースが所有しているスケジューラを使用しない場合、それらの非アクティブ化するハードウェア スレッド上のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的にです。  
  
 ハードウェア スレッドのサブスクリプション レベルがサブスクライブしているスレッドの数で示され、そのハードウェア スレッドに関連付けられた仮想プロセッサ ルートをアクティブ化します。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルに前の正の値から 0 になった場合に、スケジューラにリソースが外部でビジー状態である通知が送信されます。  
  
 スケジューラ ポリシーを持つにはこの方法で通知が送信のみ場所の値、`MinConcurrency`ポリシー キーがの値と等しい、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)です。  
  
 通知用資格のあるスケジューラを取得初期通知のセットが作成されるときにだけに割り当てられているリソースが外部でビジー状態かアイドル状態かどうかを示すことです。  
  
##  <a name="removevirtualprocessors"></a>  Ischeduler::removevirtualprocessors メソッド  
 このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。  
  
```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `ppVirtualProcessorRoots`  
 配列`IVirtualProcessorRoot`を削除する仮想プロセッサ ルートを表すインターフェイス。  
  
 `count`  
 数`IVirtualProcessorRoot`配列内のインターフェイスです。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを起動、`RemoveVirtualProcessors`スケジューラからの仮想プロセッサ ルートのセットを実行するメソッド。 呼び出すため、スケジューラが期待どおり、[削除](iexecutionresource-structure.md#remove)仮想プロセッサ ルートを持つことが行われるときは、各インターフェイスのメソッドです。 使用しないで、`IVirtualProcessorRoot`インターフェイスの起動した後、`Remove`メソッドです。  
  
 パラメーター`ppVirtualProcessorRoots`インターフェイスの配列を指します。 削除する仮想プロセッサ ルートのセット間のルートがアクティブ化されていないを使用してすぐに返される、`Remove`メソッドです。 ルートがアクティブ化されたいずれかの処理を実行中または非アクティブ化されているし、は、到着する作業を待機していることを非同期に返される必要があります。 スケジューラは、仮想プロセッサ ルートをできるだけ早く削除する各接続試行を行う必要があります。 仮想プロセッサ ルートの削除が遅れると、スケジューラ内でオーバー サブスクリプションを意図的でない可能性があります。  
  
##  <a name="statistics"></a>  Ischeduler::statistics メソッド  
 タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。  
  
```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pTaskCompletionRate`  
 このメソッドに最後に呼び出した後、スケジューラによって完了したタスクの数。  
  
 `pTaskArrivalRate`  
 このメソッドに最後に呼び出した後、スケジューラで到着したタスクの数。  
  
 `pNumberOfTasksEnqueued`  
 すべてのスケジューラ キュー内のタスクの合計数。  
  
### <a name="remarks"></a>コメント  
 このメソッドには、スケジューラの統計情報を収集するためにリソース マネージャーでは呼び出されます。 動的なフィードバック アルゴリズムである場合、スケジューラに他のリソースを割り当てる適切なとリソースを 1 回実行するタイミングを判断するには、ここに収集された統計情報が使用されます。 スケジューラによって提供される値は、オプティミスティックを指定でき、現在の数を正確に反映する必ずしも必要はありません。  
  
 タスクの到着時として、スケジューラとリソース マネージャーに登録されている他のスケジューラ間でリソースのバランスをとる方法を決定するなどの操作に関するフィードバックを使用するリソース マネージャーの場合は、このメソッドを実装する必要があります。 統計情報を収集しないように選択する場合は、ポリシー キーを設定することができます`DynamicProgressFeedback`値に`DynamicProgressFeedbackDisabled`Manager が、スケジューラでは、このメソッドを呼び出せませんスケジューラのポリシー、およびリソースです。  
  
 統計情報がない場合は、リソース マネージャーは決定を行うリソース割り当てと移行のハードウェア スレッドのサブスクリプション レベルを使用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [SchedulerPolicy クラス](schedulerpolicy-class.md)   
 [IExecutionContext 構造体](iexecutioncontext-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)
