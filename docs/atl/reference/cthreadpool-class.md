---
title: CThreadPool クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CThreadPool
- ATLUTIL/ATL::CThreadPool
- ATLUTIL/ATL::CThreadPool::CThreadPool
- ATLUTIL/ATL::CThreadPool::AddRef
- ATLUTIL/ATL::CThreadPool::GetNumThreads
- ATLUTIL/ATL::CThreadPool::GetQueueHandle
- ATLUTIL/ATL::CThreadPool::GetSize
- ATLUTIL/ATL::CThreadPool::GetTimeout
- ATLUTIL/ATL::CThreadPool::Initialize
- ATLUTIL/ATL::CThreadPool::QueryInterface
- ATLUTIL/ATL::CThreadPool::QueueRequest
- ATLUTIL/ATL::CThreadPool::Release
- ATLUTIL/ATL::CThreadPool::SetSize
- ATLUTIL/ATL::CThreadPool::SetTimeout
- ATLUTIL/ATL::CThreadPool::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64a165bdffa9f37241991af919d60de2e0dc7a96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365690"
---
# <a name="cthreadpool-class"></a>CThreadPool クラス
このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Worker, class ThreadTraits = DefaultThreadTraits>  
class CThreadPool : public IThreadPoolConfig
```  
  
#### <a name="parameters"></a>パラメーター  
 *ワーカー*  
 準拠するクラス、[ワーカー原型](../../atl/reference/worker-archetype.md)項目は、スレッド プールのキューに置かれた作業の処理に使用するコードを提供します。  
  
 `ThreadTraits`  
 プール内のスレッドを作成するための関数を提供するクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|スレッド プールのコンス トラクターです。|  
|[CThreadPool:: ~ CThreadPool](#dtor)|スレッド プールのデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|実装`IUnknown::AddRef`です。|  
|[CThreadPool::GetNumThreads](#getnumthreads)|このメソッドを呼び出して、プール内のスレッドの数を取得します。|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|キューの作業項目に使用する IO 完了ポートのハンドルを取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetSize](#getsize)|このメソッドを呼び出して、プール内のスレッドの数を取得します。|  
|[CThreadPool::GetTimeout](#gettimeout)|このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を取得します。|  
|[CThreadPool::Initialize](#initialize)|このメソッドを呼び出してスレッド プールを初期化します。|  
|[CThreadPool::QueryInterface](#queryinterface)|実装**iunknown::queryinterface**です。|  
|[CThreadPool::QueueRequest](#queuerequest)|プール内のスレッドで処理する作業アイテムをキューにこのメソッドを呼び出します。|  
|[CThreadPool::Release](#release)|実装`IUnknown::Release`です。|  
|[CThreadPool::SetSize](#setsize)|プールのスレッドの数を設定するには、このメソッドを呼び出します。|  
|[CThreadPool::SetTimeout](#settimeout)|このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を設定します。|  
|[CThreadPool::Shutdown](#shutdown)|スレッド プールをシャット ダウンするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 プール内のスレッドが作成され、プールが初期化されて、サイズ変更、またはシャット ダウン時に破棄されます。 クラスのインスタンス*ワーカー*プール内の各ワーカー スレッドのスタック上に作成されます。 各インスタンスが、スレッドの有効期間にわたって有効です。  
  
 スレッドの作成後すぐに*ワーカー*::`Initialize`はそのスレッドに関連付けられているオブジェクトで呼び出されます。 スレッドの破棄する直前に*ワーカー*::`Terminate`が呼び出されます。 どちらの方法を受け入れる必要があります、 **void\*** 引数。 この引数の値が使用中のスレッド プールに渡される、`pvWorkerParam`のパラメーター [CThreadPool::Initialize](#initialize)です。  
  
 ワーカー スレッドがキューの呼び出しからの項目をプルする作業項目がキューおよびワーカー スレッドの作業に使用できる、ときに、 **Execute**のメソッド、*ワーカー*そのスレッドのオブジェクト。 3 つの項目は、メソッドに渡されます: 同じキューからアイテム`pvWorkerParam`に渡される*ワーカー*::`Initialize`と*ワーカー*:: `Terminate`、および、へのポインター[OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) IO 完了ポートのキューに使用される構造です。  
  
 *ワーカー*クラスは、typedef を提供することにより、スレッド プールのキューの項目の型を宣言して*ワーカー*::`RequestType`です。 この型との間にキャストできる必要があります、 **ULONG_PTR**です。  
  
 例、*ワーカー*クラスは[CNonStatelessWorker クラス](../../atl/reference/cnonstatelessworker-class.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="addref"></a>  CThreadPool::AddRef  
 実装`IUnknown::AddRef`です。  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスは、参照カウントを使用して有効期間の制御を実装しません。  
  
##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool  
 スレッド プールのコンス トラクターです。  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>コメント  
 タイムアウトの値を初期化します`ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`です。 既定の時間は、36 秒です。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。  
  
##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool  
 スレッド プールのデストラクターです。  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[CThreadPool::Shutdown](#shutdown)です。  
  
##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads  
 このメソッドを呼び出して、プール内のスレッドの数を取得します。  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>戻り値  
 プールのスレッドの数を返します。  
  
##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle  
 キューの作業項目に使用する IO 完了ポートのハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 スレッド プールが初期化されていない場合は、キュー ハンドルまたは NULL を返します。  
  
##  <a name="getsize"></a>  CThreadPool::GetSize  
 このメソッドを呼び出して、プール内のスレッドの数を取得します。  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pnNumThreads`  
 [out]成功した場合、プール内のスレッドの数を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="gettimeout"></a>  CThreadPool::GetTimeout  
 このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を取得します。  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pdwMaxWait`  
 [out]成功した場合、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を受け取る変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このタイムアウト値を使って[CThreadPool::Shutdown](#shutdown)そのメソッドにその他の値が指定されていない場合。  
  
##  <a name="initialize"></a>  CThreadPool::Initialize  
 このメソッドを呼び出してスレッド プールを初期化します。  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pvWorkerParam`  
 ワーカー スレッドのオブジェクトに渡されるワーカー パラメーター `Initialize`、 **Execute**、および`Terminate`メソッドです。  
  
 `nNumThreads`  
 プール内のスレッドの要求数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合`nNumThreads`ゼロ、`ATLS_DEFAULT_THREADSPERPROC`スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。  既定では、プロセッサごとの 2 つのスレッドです。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。
  
 `dwStackSize`  
 プール内の各スレッドのスタック サイズ。  
  
 *hCompletion*  
 完了ポートに関連付けるオブジェクトのハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
##  <a name="queryinterface"></a>  CThreadPool::QueryInterface  
 実装**iunknown::queryinterface**です。  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>コメント  
 正常にこのクラスのオブジェクトを照会することができます、 **IUnknown**と[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)インターフェイスです。  
  
##  <a name="queuerequest"></a>  CThreadPool::QueueRequest  
 プール内のスレッドで処理する作業アイテムをキューにこのメソッドを呼び出します。  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `request`  
 キューに置かれた要求。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、TRUE を返しますエラー発生時に false を指定します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、作業項目をキューに追加します。 プール内のスレッドは、受信した順序でキューからアイテムを選択します。  
  
##  <a name="release"></a>  CThreadPool::Release  
 実装`IUnknown::Release`です。  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスは、参照カウントを使用して有効期間の制御を実装しません。  
  
##  <a name="setsize"></a>  CThreadPool::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nNumThreads`  
 プール内のスレッドの要求数。  
  
 場合`nNumThreads`は負の場合、その絶対値を掛けたスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合`nNumThreads`ゼロ、`ATLS_DEFAULT_THREADSPERPROC`スレッドの合計数を取得するマシンのプロセッサ数で乗算されます。 既定では、プロセッサごとの 2 つのスレッドです。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 指定されたスレッドの数がプール内の現在のスレッドの数より小さい場合は、オブジェクトは、待機中のスレッドによって取得されるをキューにシャット ダウン メッセージを格納します。 待機中のスレッドがキューからメッセージを取得、スレッド プールに通知して、スレッド処理を終了します。 によって指定された期間内のスレッドが終了していないか、プール内のスレッドの数が、指定した数に達するとするまでこのプロセスが繰り返される[GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)です。 このような状況で、メソッドは返しますに対応する HRESULT**正常に終了した**保留中のシャット ダウン メッセージが取り消されるとします。  
  
##  <a name="settimeout"></a>  CThreadPool::SetTimeout  
 このメソッドを呼び出して、スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で時間の最大値を設定します。  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で要求の最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 タイムアウトに初期化`ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT`です。 既定の時間は、36 秒です。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。 
  
 なお`dwMaxWait`プールがシャット ダウンする 1 つのスレッドの待機時間です。 複数のスレッド プールから削除されるまでの最大時間よりもやや少ない`dwMaxWait`スレッドの数を掛けた値します。  
  
##  <a name="shutdown"></a>  CThreadPool::Shutdown  
 スレッド プールをシャット ダウンするには、このメソッドを呼び出します。  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwMaxWait`  
 スレッド プールがシャット ダウンするスレッドを待機するミリ秒単位で要求の最大時間。 このメソッドが設定されているタイムアウトを使用して 0 または値はありませんは、指定した場合、 [CThreadPool::SetTimeout](#settimeout)です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、プール内のすべてのスレッドをシャット ダウン要求を送信します。 このメソッドの呼び出しがタイムアウトになると、 [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717)任意のスレッドを終了しませんでした。 このメソッドは、クラスのデストラクターから自動的に呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [クラス](../../atl/reference/atl-classes.md)
