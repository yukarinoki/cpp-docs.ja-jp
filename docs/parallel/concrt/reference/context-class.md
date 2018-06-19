---
title: コンテキスト クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
dev_langs:
- C++
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bf574fc679b879e2fa9084ed6fbd4ed82e66f70
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694181"
---
# <a name="context-class"></a>Context クラス
実行コンテキストの抽象化を表します。  
  
## <a name="syntax"></a>構文  
  
```
class Context;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-constructors"></a>プロテクト コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ Context デストラクター](#dtor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ブロック](#block)|現在のコンテキストをブロックします。|  
|[CurrentContext](#currentcontext)|現在のコンテキストへのポインターを返します。|  
|[GetId](#getid)|コンテキストが属するスケジューラ内で一意のコンテキストの識別子を返します。|  
|[GetScheduleGroupId](#getschedulegroupid)|コンテキストが現在実行されているスケジュール グループの識別子を返します。|  
|[GetVirtualProcessorId](#getvirtualprocessorid)|コンテキストが現在実行されている仮想プロセッサの識別子を返します。|  
|[Id](#id)|現在のコンテキストが属するスケジューラ内で一意の現在のコンテキストの識別子を返します。|  
|[IsCurrentTaskCollectionCanceling](#iscurrenttaskcollectioncanceling)|現在のコンテキストで現在インラインで実行されているタスク コレクションがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。|  
|[IsSynchronouslyBlocked](#issynchronouslyblocked)|コンテキストが同期的にブロックされているかどうかを判断します。 コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。|  
|[Oversubscribe](#oversubscribe)|スケジューラの仮想プロセッサのいずれかで実行されるコンテキストで呼び出された場合に、コード ブロックの期間中、追加の仮想プロセッサをそのスケジューラに挿入します。|  
|[ScheduleGroupId](#schedulegroupid)|現在のコンテキストが実行されているスケジュール グループの識別子を返します。|  
|[ブロックを解除します。](#unblock)|コンテキストのブロックを解除し、実行できるようにします。|  
|[VirtualProcessorId](#virtualprocessorid)|現在のコンテキストが実行されている仮想プロセッサの識別子を返します。|  
|[Yield](#yield)|別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイム スケジューラ (を参照してください[スケジューラ](scheduler-class.md)) アプリケーションで作業を実行する実行コンテキストを使用してキューに登録されています。 Win32 スレッドは、Windows オペレーティング システムの実行コンテキストの例です。  
  
 スケジューラの同時実行レベルは、リソース マネージャーによって許可された仮想プロセッサの数と常に等しくなります。 仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。 指定された時点に 1 つの仮想プロセッサで実行できるスケジューラ コンテキストは 1 つのみです。  
  
 スケジューラは本質的に協調的であるため、実行コンテキストが待機状態になると、常に仮想プロセッサを別のコンテキストに渡す可能性があります。 待機状態が終了すると、スケジューラの使用可能な仮想プロセッサが実行を開始するまで再開できません。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Context`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="block"></a> ブロック 

 現在のコンテキストをブロックします。  
  
```
static void __cdecl Block();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
 仮想プロセッサが可能性のあるまたはを実行する別の実行可能なコンテキストを見つける場合は呼び出し元のコンテキストは、仮想プロセッサで実行されて、新しいものを作成します。  
  
 後に、`Block`への呼び出しとペアリングする必要があります、メソッドが呼び出されたかが呼び出される、[ブロックを解除する](#unblock)でもう一度実行するために別の実行コンテキストからメソッドです。 コードが別のスレッドを呼び出せるようにするには、そのコンテキストを公開するポイント間で重要な期間があることに注意してください、`Unblock`メソッドと、実際のメソッドの呼び出しポイント`Block`が行われます。 この期間中には、順番がブロックされ、独自の理由 (たとえば、ロックの獲得) ブロックを解除するすべてのメソッドを呼び出さないでください。 呼び出し、`Block`と`Unblock`メソッドは、ブロックおよびブロック解除の理由を追跡しません。 1 つのオブジェクトの所有権が必要な`Block` -  `Unblock`ペア。  
  
 このメソッドを含む、例外のさまざまな[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)です。  
  
##  <a name="dtor"></a> ~ コンテキスト 

```
virtual ~Context();
```  
  
##  <a name="currentcontext"></a> CurrentContext 

 現在のコンテキストへのポインターを返します。  
  
```
static Context* __cdecl CurrentContext();
```  
  
### <a name="return-value"></a>戻り値  
 現在のコンテキストへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
##  <a name="getid"></a> GetId 

 コンテキストが属するスケジューラ内で一意のコンテキストの識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 コンテキストが属するスケジューラ内で一意であるコンテキストの識別子。  
  
##  <a name="getschedulegroupid"></a> GetScheduleGroupId 

 コンテキストが現在実行されているスケジュール グループの識別子を返します。  
  
```
virtual unsigned int GetScheduleGroupId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 コンテキストが現在の作業のスケジュール グループの識別子です。  
  
### <a name="remarks"></a>コメント  
 このメソッドからの戻り値は、コンテキストが実行されているスケジュール グループの瞬間的にサンプリングします。 このメソッドが呼び出された場合、現在のコンテキスト以外のコンテキストで、値が古くなっているが返され、依存することはできませんが、現在。 通常、このメソッドは、デバッグやトレースのみを目的に使用されます。  
  
##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId 

 コンテキストが現在実行されている仮想プロセッサの識別子を返します。  
  
```
virtual unsigned int GetVirtualProcessorId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 仮想プロセッサ、コンテキストが現在実行されている; 仮想プロセッサの識別子では、コンテキストは実行されている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドからの戻り値は、コンテキストが実行されている仮想プロセッサの瞬間的にサンプリングします。 この値が返され、依存することはできませんが、現在古いできます。 通常、このメソッドは、デバッグやトレースのみを目的に使用されます。  
  
##  <a name="id"></a> id 

 現在のコンテキストが属するスケジューラ内で一意の現在のコンテキストの識別子を返します。  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>戻り値  
 現在のコンテキストが、現在のコンテキストが属する; スケジューラ内で一意では、現在のコンテキストの識別子のスケジューラにアタッチされている場合それ以外の場合、値`-1`です。  
  
##  <a name="iscurrenttaskcollectioncanceling"></a> IsCurrentTaskCollectionCanceling 

 現在のコンテキストで現在インラインで実行されているタスク コレクションがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。  
  
```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出し元のコンテキストにスケジューラがアタッチされ、タスク インライン タスク グループは、そのコンテキストで実行されて、かどうかを示すそのタスク グループは、アクティブなキャンセル中 (またはいたします);それ以外の場合、値`false`です。  
  
##  <a name="issynchronouslyblocked"></a> IsSynchronouslyBlocked 

 コンテキストが同期的にブロックされているかどうかを判断します。 コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。  
  
```
virtual bool IsSynchronouslyBlocked() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 コンテキストが同期的にブロックされているかどうか。  
  
### <a name="remarks"></a>コメント  
 コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。 スレッド スケジューラのこの場合の直接呼び出し、`Context::Block`メソッド、またはを使用してビルドされた同期オブジェクト、`Context::Block`メソッドです。  
  
 このメソッドからの戻り値は、コンテキストが同期的にブロックされているかどうかの瞬間的な例です。 この値が返され、非常に特定の状況でのみ使用できますが、現在古い可能性があります。  
  
##  <a name="operator_delete"></a> delete 演算子 

 A`Context`オブジェクトは、ランタイムによって内部的に破棄されます。 これは明示的に削除できません。  
  
```
void operator delete(void* _PObject);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PObject`  
 削除するオブジェクトへのポインター。  
  
##  <a name="oversubscribe"></a> Oversubscribe 

 スケジューラの仮想プロセッサのいずれかで実行されるコンテキストで呼び出された場合に、コード ブロックの期間中、追加の仮想プロセッサをそのスケジューラに挿入します。  
  
```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```  
  
### <a name="parameters"></a>パラメーター  
 `_BeginOversubscription`  
 場合`true`、予備の仮想プロセッサが、オーバー サブスクリプションの中に追加することを示します。 場合`false`、ことを示している、オーバー サブスクリプションを終了する必要があります、以前に追加された仮想プロセッサを削除する必要があります。  
  
##  <a name="schedulegroupid"></a> ScheduleGroupId 

 現在のコンテキストが実行されているスケジュール グループの識別子を返します。  
  
```
static unsigned int __cdecl ScheduleGroupId();
```  
  
### <a name="return-value"></a>戻り値  
 現在のコンテキストはスケジューラにアタッチされ、スケジュール グループにも取り組んで、スケジューラの識別子をグループ化する場合、現在のコンテキスト取り組んでいます。それ以外の場合、値`-1`です。  
  
##  <a name="unblock"></a> ブロックを解除します。 

 コンテキストのブロックを解除し、実行できるようにします。  
  
```
virtual void Unblock() = 0;
```  
  
### <a name="remarks"></a>コメント  
 呼び出しを完全に適合している、`Unblock`メソッドに対応する呼び出しの前に、[ブロック](#block)メソッドです。 呼び出しとして長い、`Block`と`Unblock`メソッドは正しくペアになって、ランタイムが適切に自然な順序の競合を処理します。 `Unblock`前に、の呼び出し、`Block`呼び出しの影響を無効にするだけ、`Block`呼び出します。  
  
 いくつかの例外が、このメソッドからスローされる可能性があります。 コンテキストが呼び出しを試みると、`Unblock`メソッド自体を[context_self_unblock](context-self-unblock-class.md)例外がスローされます。 場合を呼び出す`Block`と`Unblock`が正しくペアになっていません (を 2 回の呼び出しなど、`Unblock`が現在実行されているコンテキストに対して行われた)、 [context_unblock_unbalanced](context-unblock-unbalanced-class.md)例外がスローされます。  
  
 コードが別のスレッドを呼び出せるようにするには、そのコンテキストを公開するポイント間で重要な期間があることに注意してください、`Unblock`メソッドと、実際のメソッドの呼び出しポイント`Block`が行われます。 この期間中には、順番がブロックされ、独自の理由 (たとえば、ロックの獲得) ブロックを解除するすべてのメソッドを呼び出さないでください。 呼び出し、`Block`と`Unblock`メソッドは、ブロックおよびブロック解除の理由を追跡しません。 1 つのオブジェクトの所有権が必要な`Block`と`Unblock`ペア。  
  
##  <a name="virtualprocessorid"></a> VirtualProcessorId 

 現在のコンテキストが実行されている仮想プロセッサの識別子を返します。  
  
```
static unsigned int __cdecl VirtualProcessorId();
```  
  
### <a name="return-value"></a>戻り値  
 現在のコンテキストが、現在のコンテキストが; で実行されている仮想プロセッサの識別子のスケジューラにアタッチされている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドからの戻り値は、現在のコンテキストが実行されている仮想プロセッサの瞬間的にサンプリングします。 この値が返され、依存することはできませんが、現在古いできます。 通常、このメソッドは、デバッグやトレースのみを目的に使用されます。  
  
##  <a name="yield"></a> Yield 

 別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。  
  
```
static void __cdecl Yield();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
##  <a name="yieldexecution"></a> YieldExecution 

 別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。  
  
```
static void __cdecl YieldExecution();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
 この関数で新しい[!INCLUDE[vs_dev14](../../../ide/includes/vs_dev14_md.md)]と同一で、 [Yield](#yield)機能しますが、Windows.h の Yield マクロと競合しません。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



