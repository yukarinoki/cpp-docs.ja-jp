---
title: CThreadPool クラス |Microsoft Docs
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
ms.openlocfilehash: f55f7d676988e43216adbf6e8a0b6c21afd958a3
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884088"
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
 準拠するクラス、[ワーカーのアーキタイプ](../../atl/reference/worker-archetype.md)スレッド プールのアイテムがキューに作業を処理するために使用するコードを提供します。  
  
 *ThreadTraits*  
 プール内のスレッドを作成するために使用する関数を提供するクラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::CThreadPool](#cthreadpool)|スレッド プールのコンス トラクター。|  
|[CThreadPool:: ~ CThreadPool](#dtor)|スレッド プールのデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CThreadPool::AddRef](#addref)|実装`IUnknown::AddRef`します。|  
|[CThreadPool::GetNumThreads](#getnumthreads)|プールのスレッドの数を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetQueueHandle](#getqueuehandle)|IO 完了ポートを使用して作業項目のキューのハンドルを取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetSize](#getsize)|プールのスレッドの数を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::GetTimeout](#gettimeout)|スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。|  
|[CThreadPool::Initialize](#initialize)|スレッド プールを初期化するためには、このメソッドを呼び出します。|  
|[CThreadPool::QueryInterface](#queryinterface)|実装`IUnknown::QueryInterface`します。|  
|[CThreadPool::QueueRequest](#queuerequest)|プール内のスレッドによって処理される作業項目キューには、このメソッドを呼び出します。|  
|[CThreadPool::Release](#release)|実装`IUnknown::Release`します。|  
|[CThreadPool::SetSize](#setsize)|プールのスレッドの数を設定するには、このメソッドを呼び出します。|  
|[CThreadPool::SetTimeout](#settimeout)|スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時間を設定するには、このメソッドを呼び出します。|  
|[CThreadPool::Shutdown](#shutdown)|スレッド プールをシャット ダウンするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>Remarks  
 プール内のスレッドが作成され、プールの初期化、サイズ変更、またはシャット ダウンするたびに破棄します。 クラスのインスタンス*ワーカー*プール内の各ワーカー スレッドのスタック上に作成されます。 各インスタンスがスレッドの有効期間にわたって有効です。  
  
 スレッドの作成後すぐに*ワーカー*::`Initialize`はそのスレッドに関連付けられているオブジェクトで呼び出されます。 スレッドの破棄する直前に*ワーカー*::`Terminate`が呼び出されます。 両方のメソッドが受け入れる必要があります、 **void\*** 引数。 この引数の値がでスレッド プールに渡される、 *pvWorkerParam*パラメーターの[CThreadPool::Initialize](#initialize)します。  
  
 ワーカー スレッドがキューの呼び出しからの項目をプルするがある場合に作業項目キューやワーカー スレッドで作業に使用できる、`Execute`のメソッド、*ワーカー*そのスレッドのオブジェクト。 3 つの項目は、メソッドに渡されます同じキューから項目`pvWorkerParam`に渡される*ワーカー*::`Initialize`と*ワーカー*:: `Terminate`、、へのポインター[。OVERLAPPED](http://msdn.microsoft.com/library/windows/desktop/ms684342) IO 完了ポートのキューに対して使用される構造体。  
  
 *ワーカー*クラスは、typedef を提供することで、スレッド プールのキューは項目の型を宣言して*ワーカー*::`RequestType`します。 この型と、ULONG_PTR の間でキャストされていることができる必要があります。  
  
 例を*ワーカー*クラスは[CNonStatelessWorker クラス](../../atl/reference/cnonstatelessworker-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IUnknown`  
  
 [IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)  
  
 `CThreadPool`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlutil.h  
  
##  <a name="addref"></a>  CThreadPool::AddRef  
 実装`IUnknown::AddRef`します。  
  
```
ULONG STDMETHODCALLTYPE AddRef() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>Remarks  
 このクラスは、参照カウントを使用して、有効期間のコントロールを実装していません。  
  
##  <a name="cthreadpool"></a>  CThreadPool::CThreadPool  
 スレッド プールのコンス トラクター。  
  
```
CThreadPool() throw();
```  
  
### <a name="remarks"></a>Remarks  
 ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT タイムアウトの値を初期化します。 既定の時間は、36 秒です。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。  
  
##  <a name="dtor"></a>  CThreadPool:: ~ CThreadPool  
 スレッド プールのデストラクターです。  
  
```
~CThreadPool() throw();
```  
  
### <a name="remarks"></a>Remarks  
 呼び出し[CThreadPool::Shutdown](#shutdown)します。  
  
##  <a name="getnumthreads"></a>  CThreadPool::GetNumThreads  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
int GetNumThreads() throw();
```  
  
### <a name="return-value"></a>戻り値  
 プールのスレッドの数を返します。  
  
##  <a name="getqueuehandle"></a>  CThreadPool::GetQueueHandle  
 IO 完了ポートを使用して作業項目のキューのハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetQueueHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 スレッド プールが初期化されていない場合は、キュー ハンドルまたは NULL を返します。  
  
##  <a name="getsize"></a>  CThreadPool::GetSize  
 プールのスレッドの数を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pnNumThreads*  
 [out]成功した場合、プールのスレッドの数を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
##  <a name="gettimeout"></a>  CThreadPool::GetTimeout  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時刻を取得するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pdwMaxWait*  
 [out]成功した場合、スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で時間の最大値を受け取る変数のアドレス。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 このタイムアウト値を使って[CThreadPool::Shutdown](#shutdown)メソッドに他の値が指定されていない場合。  
  
##  <a name="initialize"></a>  CThreadPool::Initialize  
 スレッド プールを初期化するためには、このメソッドを呼び出します。  
  
```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *pvWorkerParam*  
 ワーカー スレッドのオブジェクトに渡されるワーカー パラメーター `Initialize`、 `Execute`、および`Terminate`メソッド。  
  
 *nNumThreads*  
 要求されたプール内のスレッド数。  
  
 場合*nNumThreads*が負の場合、その絶対値で乗算されますスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合*nNumThreads*ゼロ、ATLS_DEFAULT_THREADSPERPROC はスレッドの合計数を取得するマシンのプロセッサ数が乗算されます。  既定では 1 プロセッサあたり 2 つのスレッドです。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。
  
 *dwStackSize*  
 プール内の各スレッドのスタック サイズ。  
  
 *hCompletion*  
 完了ポートに関連付けるオブジェクトのハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
##  <a name="queryinterface"></a>  CThreadPool::QueryInterface  
 実装`IUnknown::QueryInterface`します。  
  
```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```  
  
### <a name="remarks"></a>Remarks  
 正常にこのクラスのオブジェクトを照会することができます、`IUnknown`と[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)インターフェイス。  
  
##  <a name="queuerequest"></a>  CThreadPool::QueueRequest  
 プール内のスレッドによって処理される作業項目キューには、このメソッドを呼び出します。  
  
```
BOOL QueueRequest(Worker::RequestType request) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *要求*  
 キューに入れられる要求です。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、true を返します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、作業項目をキューに追加します。 プール内のスレッドは、受信される順序でキューからアイテムを選択します。  
  
##  <a name="release"></a>  CThreadPool::Release  
 実装`IUnknown::Release`します。  
  
```
ULONG STDMETHODCALLTYPE Release() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 1 を返します。  
  
### <a name="remarks"></a>Remarks  
 このクラスは、参照カウントを使用して、有効期間のコントロールを実装していません。  
  
##  <a name="setsize"></a>  CThreadPool::SetSize  
 プールのスレッドの数を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *nNumThreads*  
 要求されたプール内のスレッド数。  
  
 場合*nNumThreads*が負の場合、その絶対値で乗算されますスレッドの合計数を取得するマシンでプロセッサの数。  
  
 場合*nNumThreads*ゼロ、ATLS_DEFAULT_THREADSPERPROC はスレッドの合計数を取得するマシンのプロセッサ数が乗算されます。 既定では 1 プロセッサあたり 2 つのスレッドです。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 指定されたスレッドの数がプール内の現在のスレッドの数よりも小さい場合は、オブジェクトがシャット ダウン メッセージをキューに待機中のスレッドで取り上げられることにします。 待機中のスレッドがキューからメッセージを取得、スレッド プールに通知して、スレッド プロシージャを終了します。 によって指定された期間内のスレッドが終了していないか、プール内のスレッドの数が、指定した数に達するまで、このプロセスが繰り返されます[GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)します。 このような状況でメソッドが WAIT_TIMEOUT に対応する HRESULT を返す、保留中のシャット ダウン メッセージがキャンセルされます。  
  
##  <a name="settimeout"></a>  CThreadPool::SetTimeout  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で最大の時間を設定するには、このメソッドを呼び出します。  
  
```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwMaxWait*  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で要求された最大時間。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK または失敗時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>Remarks  
 タイムアウトは、ATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUT に初期化されます。 既定の時間は、36 秒です。 Atlutil.h する前に、必要に応じて、このシンボルには、独自の正の整数値を定義できます。 
  
 なお*dwMaxWait*をシャット ダウンする単一のスレッドのプールが待機する時間です。 複数のスレッド プールから削除されるまでの最大時間より若干小さい*dwMaxWait*スレッドの数を掛けた値します。  
  
##  <a name="shutdown"></a>  CThreadPool::Shutdown  
 スレッド プールをシャット ダウンするには、このメソッドを呼び出します。  
  
```
void Shutdown(DWORD dwMaxWait = 0) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwMaxWait*  
 スレッド プール スレッドをシャット ダウンを待機するミリ秒単位で要求された最大時間。 このメソッドは設定されたタイムアウトを使用して、0 または値が指定されている場合[CThreadPool::SetTimeout](#settimeout)します。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは、プール内のすべてのスレッドをシャット ダウン要求をポストします。 このメソッドの呼び出しがタイムアウトになると、 [TerminateThread](http://msdn.microsoft.com/library/windows/desktop/ms686717)任意のスレッドを終了しませんでした。 このメソッドは、クラスのデストラクターから自動的に呼び出されます。  
  
## <a name="see-also"></a>関連項目  
 [IThreadPoolConfig インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)   
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [クラス](../../atl/reference/atl-classes.md)
