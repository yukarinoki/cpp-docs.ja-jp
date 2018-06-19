---
title: クラスの使用 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWorkerThread class
ms.assetid: be79a832-1345-4a36-a13e-a406cc65286f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e87001ca341ae27cb173357f74e06e543f5eb262
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365521"
---
# <a name="cworkerthread-class"></a>クラスの使用
このクラスは、ワーカー スレッドを作成または既存のものを使用して化し、1 つまたは複数のカーネル オブジェクトのハンドルを待機がシグナルを受け取るハンドルのいずれかに指定されたクライアント関数を実行します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <class ThreadTraits = DefaultThreadTraits>  
class CWorkerThread
```  
  
#### <a name="parameters"></a>パラメーター  
 `ThreadTraits`  
 スレッドの作成関数をなどを提供するクラス[CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md)または[Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md)です。  
  
## <a name="members"></a>メンバー  
  
### <a name="protected-structures"></a>保護された構造体  
  
|名前|説明|  
|----------|-----------------|  
|`WorkerClientEntry`||  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWorkerThread::CWorkerThread](#cworkerthread)|ワーカー スレッドのコンス トラクターです。|  
|[使用:: ~ 使用](#dtor)|ワーカー スレッドのデストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWorkerThread::AddHandle](#addhandle)|このメソッドを呼び出して待機可能オブジェクトのハンドルをワーカー スレッドによって保持されたリストに追加します。|  
|[CWorkerThread::AddTimer](#addtimer)|ワーカー スレッドによって保持されたリストに、定期的な待機可能なタイマーを追加するには、このメソッドを呼び出します。|  
|[CWorkerThread::GetThreadHandle](#getthreadhandle)|ワーカー スレッドのスレッド ハンドルを取得するには、このメソッドを呼び出します。|  
|[CWorkerThread::GetThreadId](#getthreadid)|ワーカー スレッドのスレッド ID を取得するには、このメソッドを呼び出します。|  
|[CWorkerThread::Initialize](#initialize)|このメソッドを呼び出して、ワーカー スレッドを初期化します。|  
|[CWorkerThread::RemoveHandle](#removehandle)|このメソッドを呼び出して待機可能オブジェクトの一覧からハンドルを削除します。|  
|[CWorkerThread::Shutdown](#shutdown)|ワーカー スレッドをシャット ダウンするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
  
### <a name="to-use-cworkerthread"></a>使用を使用するには  
  
1.  このクラスのインスタンスを作成します。  
  
2.  呼び出す[CWorkerThread::Initialize](#initialize)です。  
  
3.  呼び出す[CWorkerThread::AddHandle](#addhandle)カーネル オブジェクトとの実装へのポインターのハンドルを持つ[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)です。  
  
     - または  
  
     呼び出す[CWorkerThread::AddTimer](#addtimer)の実装へのポインターを[IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)です。  
  
4.  実装[IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルまたはタイマーが通知されるときに何らかのアクションを実行します。  
  
5.  待機可能オブジェクトの一覧からオブジェクトを削除するには、呼び出す[CWorkerThread::RemoveHandle](#removehandle)です。  
  
6.  スレッドを終了するには、呼び出す[CWorkerThread::Shutdown](#shutdown)です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="addhandle"></a>  CWorkerThread::AddHandle  
 このメソッドを呼び出して待機可能オブジェクトのハンドルをワーカー スレッドによって保持されたリストに追加します。  
  
```
HRESULT AddHandle(
    HANDLE hObject,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 待機可能オブジェクトのハンドルです。  
  
 `pClient`  
 ポインター、 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)ハンドルがシグナルを受け取るときに呼び出されるオブジェクトのインターフェイスです。  
  
 `dwParam`  
 渡されるパラメーター [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルがシグナルを受け取るときにします。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)を介して呼び出される`pClient`ときに、ハンドル`hObject`、通知されます。  
  
##  <a name="addtimer"></a>  CWorkerThread::AddTimer  
 ワーカー スレッドによって保持されたリストに、定期的な待機可能なタイマーを追加するには、このメソッドを呼び出します。  
  
```
HRESULT AddTimer(
    DWORD dwInterval,
    IWorkerThreadClient* pClient,
    DWORD_PTR dwParam,
    HANDLE* phTimer) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 *dwInterval*  
 タイマーの間隔をミリ秒単位で指定します。  
  
 `pClient`  
 ポインター、 [IWorkerThreadClient](../../atl/reference/iworkerthreadclient-interface.md)ハンドルがシグナルを受け取るときに呼び出されるオブジェクトのインターフェイスです。  
  
 `dwParam`  
 渡されるパラメーター [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)ハンドルがシグナルを受け取るときにします。  
  
 `phTimer`  
 [out]成功した場合、新しく作成されたタイマーを識別するハンドルを受け取るハンドル変数のアドレスです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 [IWorkerThreadClient::Execute](../../atl/reference/iworkerthreadclient-interface.md#execute)を介して呼び出される`pClient`タイマーが通知されます。  
  
 タイマー ハンドルを渡す`phTimer`に[CWorkerThread::RemoveHandle](#removehandle)タイマーを閉じます。  
  
##  <a name="cworkerthread"></a>  CWorkerThread::CWorkerThread  
 コンストラクターです。  
  
```
CWorkerThread() throw();
```  
  
##  <a name="dtor"></a>  使用:: ~ 使用  
 デストラクターです。  
  
```
~CWorkerThread() throw();
```  
  
### <a name="remarks"></a>コメント  
 呼び出し[CWorkerThread::Shutdown](#shutdown)です。  
  
##  <a name="getthreadhandle"></a>  CWorkerThread::GetThreadHandle  
 ワーカー スレッドのスレッド ハンドルを取得するには、このメソッドを呼び出します。  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ワーカー スレッドが初期化されていない場合は、スレッド ハンドルまたは NULL を返します。  
  
##  <a name="getthreadid"></a>  CWorkerThread::GetThreadId  
 ワーカー スレッドのスレッド ID を取得するには、このメソッドを呼び出します。  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ワーカー スレッドが初期化されていない場合は、スレッド ID または NULL を返します。  
  
##  <a name="initialize"></a>  CWorkerThread::Initialize  
 このメソッドを呼び出して、ワーカー スレッドを初期化します。  
  
```
HRESULT Initialize() throw();

HRESULT Initialize(CWorkerThread<ThreadTraits>* pThread) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pThread`  
 既存のワーカー スレッドです。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、作成後、または呼び出しの後に、オブジェクトを初期化するために呼び出す必要があります[CWorkerThread::Shutdown](#shutdown)です。  
  
 2 つ以上に`CWorkerThread`オブジェクトが同じワーカー スレッドを使用して、任意の引数は、オブジェクトを指すポインターを渡す渡されずうち 1 つを初期化、`Initialize`他のメソッドです。 ポインターを使用して初期化されたオブジェクトは、オブジェクトの初期化に使用する前にシャット ダウンする必要があります。  
  
 参照してください[CWorkerThread::Shutdown](#shutdown)については、既存のオブジェクトへのポインターを使用して初期化されるときに、そのメソッドの動作がどのように変化するかをします。  
  
##  <a name="removehandle"></a>  CWorkerThread::RemoveHandle  
 このメソッドを呼び出して待機可能オブジェクトの一覧からハンドルを削除します。  
  
```
HRESULT RemoveHandle(HANDLE hObject) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hObject`  
 削除するハンドル。  
  
### <a name="return-value"></a>戻り値  
 成功した場合、S_OK またはエラー発生時にエラーの hresult 値を返します。  
  
### <a name="remarks"></a>コメント  
 ハンドルが削除されたとき[IWorkerThreadClient::CloseHandle](../../atl/reference/iworkerthreadclient-interface.md#closehandle)に渡された関連付けられたオブジェクトで呼び出される[AddHandle](#addhandle)です。 この呼び出しが失敗した場合、 `CWorkerThread` 、Windows を呼び出す[CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211)ハンドルの関数。  
  
##  <a name="shutdown"></a>  CWorkerThread::Shutdown  
 ワーカー スレッドをシャット ダウンするには、このメソッドを呼び出します。  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `dwWait`  
 ワーカー スレッドをシャット ダウンするまで待機するミリ秒単位の時間。 ATL_WORKER_THREAD_WAIT の既定値は 10 秒です。 Atlutil.h する前に、必要に応じて、このシンボルに独自の値を定義できます。 
  
### <a name="return-value"></a>戻り値  
 成功した場合、または失敗した場合の場合など、エラーの hresult 値は S_OK を返します、タイムアウト値を`dwWait`を超過します。  
  
### <a name="remarks"></a>コメント  
 オブジェクトを再利用する[CWorkerThread::Initialize](#initialize)このメソッドを呼び出した後。  
  
 呼び出して**シャット ダウン**別にポインターを使用して初期化されるオブジェクトで`CWorkerThread`オブジェクトの影響は生じず、常に S_OK を返します。  
  
## <a name="see-also"></a>関連項目  
 [DefaultThreadTraits](atl-typedefs.md#defaultthreadtraits)   
 [クラス](../../atl/reference/atl-classes.md)   
 [マルチ スレッド: ワーカー スレッドの作成](../../parallel/multithreading-creating-worker-threads.md)   
 [IWorkerThreadClient インターフェイス](../../atl/reference/iworkerthreadclient-interface.md)
