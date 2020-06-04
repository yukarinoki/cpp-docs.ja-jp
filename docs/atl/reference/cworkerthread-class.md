---
title: クラス
ms.date: 11/04/2016
f1_keywords:
- CWorkerThread
- ATLUTIL/ATL::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::CWorkerThread
- ATLUTIL/ATL::CWorkerThread::AddHandle
- ATLUTIL/ATL::CWorkerThread::AddTimer
- ATLUTIL/ATL::CWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CWorkerThread::GetThreadId
- ATLUTIL/ATL::CWorkerThread::Initialize
- ATLUTIL/ATL::CWorkerThread::RemoveHandle
- ATLUTIL/ATL::CWorkerThread::Shutdown
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
ms.openlocfilehash: 05e6b432d44927fa7e276792643e29c80c42d822
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330219"
---
# <a name="cworkerthread-class"></a>クラス

このクラスは、ワーカー スレッドを作成するか、既存のスレッドを使用して、1 つ以上のカーネル オブジェクト ハンドルを待機し、ハンドルの 1 つがシグナル状態になったときに、指定されたクライアント関数を実行します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class ThreadTraits = DefaultThreadTraits>
class CWorkerThread
```

### <a name="parameters"></a>パラメーター

*スレッドトレイト*<br/>
スレッド作成関数を提供するクラス ( [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)や[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)など ) 。

## <a name="members"></a>メンバー

### <a name="protected-structures"></a>保護された構造

|名前|説明|
|----------|-----------------|
|`WorkerClientEntry`||

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[::Cワーカースレッド](#cworkerthread)|ワーカー スレッドのコンストラクター。|
|[::~Cワーカースレッド](#dtor)|ワーカー スレッドのデストラクター。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ハンドルを追加します。](#addhandle)|ワーカー スレッドによって管理されるリストに待機可能オブジェクトのハンドルを追加します。|
|[を使用します。](#addtimer)|ワーカー スレッドによって維持されるリストに、定期的な待機可能タイマーを追加します。|
|[を処理します。](#getthreadhandle)|ワーカー スレッドのスレッド ハンドルを取得します。|
|[を使用します。](#getthreadid)|ワーカー スレッドのスレッド ID を取得します。|
|[初期化](#initialize)|ワーカー スレッドを初期化します。|
|[ハンドルを削除します。](#removehandle)|待機可能オブジェクトのリストからハンドルを削除します。|
|[Cワーカースレッド::シャットダウン](#shutdown)|ワーカー スレッドをシャットダウンします。|

## <a name="remarks"></a>解説

### <a name="to-use-cworkerthread"></a>C ワーカー スレッドを使用するには

1. このクラスのインスタンスを作成します。

1. を呼び出します[。](#initialize)

1. カーネル オブジェクトのハンドルと[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)の実装へのポインターを使用して[CWorkerThread::AddHandle](#addhandle)を呼び出します。

   \- または

   を呼び出す[C ワーカー スレッド::追加タイマー](#addtimer)を呼び出し[、IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)の実装へのポインターを使用します。

1. ハンドルまたはタイマーがシグナル状態になったときに何らかのアクションを実行する[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)を実装します。

1. 待機可能オブジェクトのリストからオブジェクトを削除するには[、CWorkerThread::RemoveHandle](#removehandle)を呼び出します。

1. スレッドを終了するには[、CWorkerThread::Shutdown](#shutdown)を呼び出します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="cworkerthreadaddhandle"></a><a name="addhandle"></a>ハンドルを追加します。

ワーカー スレッドによって管理されるリストに待機可能オブジェクトのハンドルを追加します。

```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
待機可能オブジェクトへのハンドル。

*クライアント*<br/>
ハンドルがシグナル状態になったときに呼び出されるオブジェクトの[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)インターフェイスへのポインター。

*ドウパラム*<br/>
ハンドルがシグナル状態になったときに[実行を実行](../../atl/reference/iworkerthreadclient-interface.md#execute)するパラメーター。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[ハンドル hObject が](../../atl/reference/iworkerthreadclient-interface.md#execute)シグナル状態になると *、p クライアント*を介して実行*hObject*が呼び出されます。

## <a name="cworkerthreadaddtimer"></a><a name="addtimer"></a>を使用します。

ワーカー スレッドによって維持されるリストに、定期的な待機可能タイマーを追加します。

```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```

### <a name="parameters"></a>パラメーター

*間隔*<br/>
タイマーの期間をミリ秒単位で指定します。

*クライアント*<br/>
ハンドルがシグナル状態になったときに呼び出されるオブジェクトの[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)インターフェイスへのポインター。

*ドウパラム*<br/>
ハンドルがシグナル状態になったときに[実行を実行](../../atl/reference/iworkerthreadclient-interface.md#execute)するパラメーター。

*フタイマー*<br/>
[アウト]成功時に新しく作成されたタイマーへのハンドルを受け取る HANDLE 変数のアドレス。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

[タイマーがシグナル状態になると](../../atl/reference/iworkerthreadclient-interface.md#execute)*、p クライアントを*介して実行が呼び出されます。

タイマー ハンドルを*phTimer*から[CWorkerThread::RemoveHandle](#removehandle)に渡して、タイマーを閉じます。

## <a name="cworkerthreadcworkerthread"></a><a name="cworkerthread"></a>::Cワーカースレッド

コンストラクターです。

```
CWorkerThread() throw();
```

## <a name="cworkerthreadcworkerthread"></a><a name="dtor"></a>::~Cワーカースレッド

デストラクターです。

```
~CWorkerThread() throw();
```

### <a name="remarks"></a>解説

を呼び出します[。](#shutdown)

## <a name="cworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>を処理します。

ワーカー スレッドのスレッド ハンドルを取得します。

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>戻り値

ワーカー スレッドが初期化されていない場合は、スレッド ハンドルを返します。

## <a name="cworkerthreadgetthreadid"></a><a name="getthreadid"></a>を使用します。

ワーカー スレッドのスレッド ID を取得します。

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>戻り値

ワーカー スレッドが初期化されていない場合は、スレッド ID または NULL を返します。

## <a name="cworkerthreadinitialize"></a><a name="initialize"></a>初期化

ワーカー スレッドを初期化します。

```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```

### <a name="parameters"></a>パラメーター

*をクリックします。*<br/>
既存のワーカー スレッド。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

このメソッドは、作成後、または[CWorkerThread::Shutdown](#shutdown)の呼び出し後にオブジェクトを初期化するために呼び出す必要があります。

2 つ以上`CWorkerThread`のオブジェクトに同じワーカー スレッドを使用するには、引数を渡さずにそのうちの 1 つを初期化し、`Initialize`そのオブジェクトへのポインターを他のメソッドに渡します。 ポインターを使用して初期化されたオブジェクトは、初期化に使用されるオブジェクトの前にシャットダウンする必要があります。

既存のオブジェクトへのポインターを使用して初期化されたときのメソッドの動作の変化については[、「CWorkerThread::Shutdown」](#shutdown)を参照してください。

## <a name="cworkerthreadremovehandle"></a><a name="removehandle"></a>ハンドルを削除します。

待機可能オブジェクトのリストからハンドルを削除します。

```
HRESULT RemoveHandle(HANDLE hObject) throw();
```

### <a name="parameters"></a>パラメーター

*hオブジェクト*<br/>
削除するハンドル。

### <a name="return-value"></a>戻り値

成功時にS_OKを返すか、失敗した場合に HRESULT エラーを返します。

### <a name="remarks"></a>解説

ハンドルが削除されると[、IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle)は[、AddHandle](#addhandle)に渡された関連付けられたオブジェクトに対して呼び出されます。 この呼び出し`CWorkerThread`が失敗した場合は、ハンドルの Windows [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle)関数を呼び出します。

## <a name="cworkerthreadshutdown"></a><a name="shutdown"></a>Cワーカースレッド::シャットダウン

ワーカー スレッドをシャットダウンします。

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="parameters"></a>パラメーター

*dwWait*<br/>
ワーカー スレッドがシャットダウンするまでの待機時間 (ミリ秒単位)。 ATL_WORKER_THREAD_WAITデフォルトは 10 秒です。 必要に応じて、atlutil.h を含める前に、このシンボルに独自の値を定義できます。

### <a name="return-value"></a>戻り値

タイムアウト値*dwWait*を超えた場合など、成功時にS_OK、またはエラー HRESULT を返します。

### <a name="remarks"></a>解説

オブジェクトを再利用するには、このメソッドを呼び出した後[に CWorkerThread::Initialize を](#initialize)呼び出します。

別`CWorkerThread`のオブジェクト`Shutdown`へのポインターで初期化されたオブジェクトを呼び出しても、常にS_OK返されることに注意してください。

## <a name="see-also"></a>関連項目

[既定のスレッドトレイト](atl-typedefs.md#defaultthreadtraits)<br/>
[クラス](../../atl/reference/atl-classes.md)<br/>
[マルチスレッド: ワーカー スレッドの生成](../../parallel/multithreading-creating-worker-threads.md)<br/>
[インターフェイス](../../atl/reference/iworkerthreadclient-interface.md)
