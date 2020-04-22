---
title: クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CThreadPool class
ms.assetid: 06683718-01b9-413c-9481-2dc1734ec70f
ms.openlocfilehash: 5e52868f23883836919b96be9aec1815bc1c17b3
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747450"
---
# <a name="cthreadpool-class"></a>クラス

このクラスは、作業項目のキューを処理するワーカー スレッドのプールを提供します。

## <a name="syntax"></a>構文

```
template <class Worker, class ThreadTraits = DefaultThreadTraits>
class CThreadPool : public IThreadPoolConfig
```

#### <a name="parameters"></a>パラメーター

*ワーカー*<br/>
スレッド プールにキューに置かれた作業項目の処理に使用されるコードを提供する[ワーカー の原型](../../atl/reference/worker-archetype.md)に準拠するクラス。

*スレッドトレイト*<br/>
プール内のスレッドの作成に使用される関数を提供するクラス。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cスレッドプール](#cthreadpool)|スレッド プールのコンストラクター。|
|[::~Cスレッドプール](#dtor)|スレッド プールのデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を使用します。](#addref)|`IUnknown::AddRef` の実装です。|
|[スレッドプール::スレッド](#getnumthreads)|プール内のスレッドの数を取得します。|
|[をキューに格納します。](#getqueuehandle)|作業項目のキューに使用される IO 完了ポートのハンドルを取得します。|
|[を使用します。](#getsize)|プール内のスレッドの数を取得します。|
|[を使用します。](#gettimeout)|スレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を取得します。|
|[を初期化します。](#initialize)|スレッド プールを初期化します。|
|[次のクエリインターフェイス](#queryinterface)|`IUnknown::QueryInterface` の実装です。|
|[キューリクエスト](#queuerequest)|プール内のスレッドによって処理される作業項目をキューに入れます。|
|[Cスレッドプール::リリース](#release)|`IUnknown::Release` の実装です。|
|[を設定します。](#setsize)|プール内のスレッドの数を設定します。|
|[を設定します。](#settimeout)|スレッド プールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定します。|
|[Cスレッドプール::シャットダウン](#shutdown)|スレッド プールをシャットダウンします。|

## <a name="remarks"></a>解説

プール内のスレッドは、プールの初期化、サイズ変更、またはシャットダウン時に作成および破棄されます。 *ワーカー*クラスのインスタンスは、プール内の各ワーカー スレッドのスタックに作成されます。 各インスタンスは、スレッドの有効期間内に存続します。

スレッドの作成直後に、*その*スレッドに関連`Initialize`付けられたオブジェクトに対してワーカー :: が呼び出されます。 スレッドが破棄される直前に、*ワーカー*::`Terminate`が呼び出されます。 どちらのメソッドも**void**<strong>\*</strong>引数を受け入れる必要があります。 この引数の値は[、CThreadPool::初期化](#initialize)の*pvWorkerParam*パラメーターを介してスレッド プールに渡されます。

キューに作業項目があり、作業に使用できるワーカー スレッドがある場合、ワーカー スレッドはキューからアイテムをプルし、そのスレッド`Execute`の*Worker*オブジェクトのメソッドを呼び出します。 次に、キューのアイテム、ワーカー :: と`pvWorkerParam`*ワーカー*:: `Initialize` *Worker*`Terminate`に渡される項目、および IO 完了ポート キューに使用される[OVERLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped)構造体へのポインターの 3 つの項目がメソッドに渡されます。

*ワーカー*クラスは、typedef を指定して、スレッド プールにキューに入る項目の型を宣言*Worker*`RequestType`します。 この型は、ULONG_PTRとの間でキャストできる必要があります。

*ワーカー*クラスの例としては[、CNonStateless ワーカー クラスがあります](../../atl/reference/cnonstatelessworker-class.md)。

## <a name="inheritance-hierarchy"></a>継承階層

`IUnknown`

[を構成します。](../../atl/reference/ithreadpoolconfig-interface.md)

`CThreadPool`

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="cthreadpooladdref"></a><a name="addref"></a>を使用します。

`IUnknown::AddRef` の実装です。

```
ULONG STDMETHODCALLTYPE AddRef() throw();
```

### <a name="return-value"></a>戻り値

常に 1 を返します。

### <a name="remarks"></a>解説

このクラスは、参照カウントを使用して有効期間コントロールを実装しません。

## <a name="cthreadpoolcthreadpool"></a><a name="cthreadpool"></a>::Cスレッドプール

スレッド プールのコンストラクター。

```
CThreadPool() throw();
```

### <a name="remarks"></a>解説

タイムアウト値をATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUTに初期化します。 デフォルトの時間は 36 秒です。 必要に応じて、atlutil.h を含める前に、このシンボルに対して独自の正の整数値を定義できます。

## <a name="cthreadpoolcthreadpool"></a><a name="dtor"></a>::~Cスレッドプール

スレッド プールのデストラクター。

```
~CThreadPool() throw();
```

### <a name="remarks"></a>解説

を呼び出します[。](#shutdown)

## <a name="cthreadpoolgetnumthreads"></a><a name="getnumthreads"></a>スレッドプール::スレッド

プール内のスレッドの数を取得します。

```
int GetNumThreads() throw();
```

### <a name="return-value"></a>戻り値

プール内のスレッドの数を返します。

## <a name="cthreadpoolgetqueuehandle"></a><a name="getqueuehandle"></a>をキューに格納します。

作業項目のキューに使用される IO 完了ポートのハンドルを取得します。

```
HANDLE GetQueueHandle() throw();
```

### <a name="return-value"></a>戻り値

スレッド プールが初期化されていない場合は、キュー ハンドルを返します。

## <a name="cthreadpoolgetsize"></a><a name="getsize"></a>を使用します。

プール内のスレッドの数を取得します。

```
HRESULT STDMETHODCALLTYPE GetSize(int* pnNumThreads) throw();
```

### <a name="parameters"></a>パラメーター

*スレッド*<br/>
[アウト]成功時にプール内のスレッド数を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cthreadpoolgettimeout"></a><a name="gettimeout"></a>を使用します。

スレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を取得します。

```
HRESULT STDMETHODCALLTYPE GetTimeout(DWORD* pdwMaxWait) throw();
```

### <a name="parameters"></a>パラメーター

*を待つ*<br/>
[アウト]成功時にスレッド プールがスレッドのシャットダウンを待機する最大時間 (ミリ秒単位) を受け取る変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このタイムアウト値は、そのメソッドに他の値が指定されていない場合は[、CThreadPool::Shutdown](#shutdown)によって使用されます。

## <a name="cthreadpoolinitialize"></a><a name="initialize"></a>を初期化します。

スレッド プールを初期化します。

```
HRESULT Initialize(
    void* pvWorkerParam = NULL,
    int nNumThreads = 0,
    DWORD dwStackSize = 0,
    HANDLE hCompletion = INVALID_HANDLE_VALUE) throw();
```

### <a name="parameters"></a>パラメーター

*を使用する*<br/>
ワーカー スレッド オブジェクト`Initialize`、、`Execute`および`Terminate`メソッドに渡されるワーカー パラメーター。

*nNumスレッド*<br/>
プール内の要求されたスレッド数。

*nNumThreads*が負の値の場合、その絶対値は、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算します。

*nNumThreads*が 0 の場合、ATLS_DEFAULT_THREADSPERPROCは、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算されます。  デフォルトは、プロセッサあたり 2 スレッドです。 必要に応じて、atlutil.h を含める前に、このシンボルに対して独自の正の整数値を定義できます。

*サイズを変更します。*<br/>
プール内の各スレッドのスタック サイズ。

*h完了*<br/>
完了ポートに関連付けるオブジェクトのハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

## <a name="cthreadpoolqueryinterface"></a><a name="queryinterface"></a>次のクエリインターフェイス

`IUnknown::QueryInterface` の実装です。

```
HRESULT STDMETHODCALLTYPE QueryInterface(REFIID riid, void** ppv) throw();
```

### <a name="remarks"></a>解説

このクラスのオブジェクトは、`IUnknown`インターフェイスおよび[IThreadPoolConfig](../../atl/reference/ithreadpoolconfig-interface.md)インターフェイスに対して正常に照会できます。

## <a name="cthreadpoolqueuerequest"></a><a name="queuerequest"></a>キューリクエスト

プール内のスレッドによって処理される作業項目をキューに入れます。

```
BOOL QueueRequest(Worker::RequestType request) throw();
```

### <a name="parameters"></a>パラメーター

*request*<br/>
キューに入れられる要求。

### <a name="return-value"></a>戻り値

成功した場合は TRUE を返し、失敗した場合は FALSE を返します。

### <a name="remarks"></a>解説

このメソッドは、作業項目をキューに追加します。 プール内のスレッドは、受信した順序でアイテムをキューから選択します。

## <a name="cthreadpoolrelease"></a><a name="release"></a>Cスレッドプール::リリース

`IUnknown::Release` の実装です。

```
ULONG STDMETHODCALLTYPE Release() throw();
```

### <a name="return-value"></a>戻り値

常に 1 を返します。

### <a name="remarks"></a>解説

このクラスは、参照カウントを使用して有効期間コントロールを実装しません。

## <a name="cthreadpoolsetsize"></a><a name="setsize"></a>を設定します。

プール内のスレッドの数を設定します。

```
HRESULT STDMETHODCALLTYPE SetSizeint nNumThreads) throw();
```

### <a name="parameters"></a>パラメーター

*nNumスレッド*<br/>
プール内の要求されたスレッド数。

*nNumThreads*が負の値の場合、その絶対値は、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算します。

*nNumThreads*が 0 の場合、ATLS_DEFAULT_THREADSPERPROCは、スレッドの合計数を取得するコンピューター内のプロセッサの数を乗算されます。 デフォルトは、プロセッサあたり 2 スレッドです。 必要に応じて、atlutil.h を含める前に、このシンボルに対して独自の正の整数値を定義できます。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

指定されたスレッド数が現在プール内のスレッド数より少ない場合、オブジェクトは待機中のスレッドによって取得されるシャットダウン・メッセージをキューに書き込みます。 待機中のスレッドがキューからメッセージをプルすると、スレッド プールに通知し、スレッド プロシージャを終了します。 このプロセスは、プール内のスレッドの数が指定した数に達するまで、または[GetTimeout](#gettimeout)/ [SetTimeout](#settimeout)で指定された期間内にスレッドが終了するまで繰り返されます。 この場合、メソッドはWAIT_TIMEOUTに対応する HRESULT を返し、保留中のシャットダウン メッセージがキャンセルされます。

## <a name="cthreadpoolsettimeout"></a><a name="settimeout"></a>を設定します。

スレッド プールがスレッドのシャットダウンを待機する最大時間をミリ秒単位で設定します。

```
HRESULT STDMETHODCALLTYPE SetTimeout(DWORD dwMaxWait) throw();
```

### <a name="parameters"></a>パラメーター

*を待つ*<br/>
スレッド プールがスレッドのシャットダウンを待機する要求された最大時間 (ミリ秒単位)。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

タイムアウトはATLS_DEFAULT_THREADPOOLSHUTDOWNTIMEOUTに初期化されます。 デフォルトの時間は 36 秒です。 必要に応じて、atlutil.h を含める前に、このシンボルに対して独自の正の整数値を定義できます。

*dwMaxWait*は、プールが単一のスレッドがシャットダウンするまで待機する時間であることに注意してください。 プールから複数のスレッドを削除するために取ることができる最大時間は *、dwMaxWait*にスレッド数を掛けた数よりわずかに短くなる可能性があります。

## <a name="cthreadpoolshutdown"></a><a name="shutdown"></a>Cスレッドプール::シャットダウン

スレッド プールをシャットダウンします。

```cpp
void Shutdown(DWORD dwMaxWait = 0) throw();
```

### <a name="parameters"></a>パラメーター

*を待つ*<br/>
スレッド プールがスレッドのシャットダウンを待機する要求された最大時間 (ミリ秒単位)。 0 または値が指定されていない場合、このメソッドは[、CThreadPool::SetTimeout](#settimeout)によって設定されたタイムアウトを使用します。

### <a name="remarks"></a>解説

このメソッドは、プール内のすべてのスレッドにシャットダウン要求を送信します。 タイムアウトが経過すると、このメソッドは終了しなかったスレッドで[TerminateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-terminatethread)を呼び出します。 このメソッドは、クラスのデストラクターから自動的に呼び出されます。

## <a name="see-also"></a>関連項目

[インターフェイス](../../atl/reference/ithreadpoolconfig-interface.md)<br/>
[既定のスレッドトレイト](atl-typedefs.md#defaultthreadtraits)<br/>
[クラス](../../atl/reference/atl-classes.md)
