---
title: CNoWorkerThread クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread
- ATLUTIL/ATL::CNoWorkerThread::AddHandle
- ATLUTIL/ATL::CNoWorkerThread::AddTimer
- ATLUTIL/ATL::CNoWorkerThread::GetThreadHandle
- ATLUTIL/ATL::CNoWorkerThread::GetThreadId
- ATLUTIL/ATL::CNoWorkerThread::Initialize
- ATLUTIL/ATL::CNoWorkerThread::RemoveHandle
- ATLUTIL/ATL::CNoWorkerThread::Shutdown
dev_langs:
- C++
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 85e1962d10f274f4f8c35ba27cb05c41e8bf19cb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363085"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread クラス
引数としてこのクラスを使用して、`MonitorClass`動的キャッシュのメンテナンスを無効にする場合、キャッシュ クラスをテンプレート パラメーター。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CNoWorkerThread
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CNoWorkerThread::AddHandle](#addhandle)|該当するショートカットは機能しない[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。|  
|[CNoWorkerThread::AddTimer](#addtimer)|該当するショートカットは機能しない[CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)です。|  
|[CNoWorkerThread::GetThreadHandle](#getthreadhandle)|該当するショートカットは機能しない[CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)です。|  
|[CNoWorkerThread::GetThreadId](#getthreadid)|該当するショートカットは機能しない[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)です。|  
|[CNoWorkerThread::Initialize](#initialize)|該当するショートカットは機能しない[CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)です。|  
|[CNoWorkerThread::RemoveHandle](#removehandle)|該当するショートカットは機能しない[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)です。|  
|[CNoWorkerThread::Shutdown](#shutdown)|該当するショートカットは機能しない[CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)です。|  
  
## <a name="remarks"></a>コメント  
 このクラスと同じパブリック インターフェイスを提供する[使用](../../atl/reference/cworkerthread-class.md)です。 このインターフェイスをによって提供されると予想される、`MonitorClass`キャッシュ クラスをテンプレート パラメーター。  
  
 このクラスでメソッドを実装して、何もしません。 常に HRESULT を返すメソッドは、S_OK を返し、常に、ハンドルまたはスレッドの ID を返すメソッドは、0 を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlutil.h  
  
##  <a name="addhandle"></a>  CNoWorkerThread::AddHandle  
 該当するショートカットは機能しない[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)です。  
  
```
HRESULT AddHandle(HANDLE /* hObject
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="addtimer"></a>  CNoWorkerThread::AddTimer  
 該当するショートカットは機能しない[CWorkerThread::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)です。  
  
```
HRESULT AddTimer(DWORD /* dwInterval
 */,
    IWorkerThreadClient* /* pClient
 */,
    DWORD_PTR /* dwParam
 */,
    HANDLE* /* phTimer
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="getthreadhandle"></a>  CNoWorkerThread::GetThreadHandle  
 該当するショートカットは機能しない[CWorkerThread::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)です。  
  
```
HANDLE GetThreadHandle() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に NULL が返されます。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="getthreadid"></a>  CNoWorkerThread::GetThreadId  
 該当するショートカットは機能しない[CWorkerThread::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)です。  
  
```
DWORD GetThreadId() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に 0 を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="initialize"></a>  CNoWorkerThread::Initialize  
 該当するショートカットは機能しない[CWorkerThread::Initialize](../../atl/reference/cworkerthread-class.md#initialize)です。  
  
```
HRESULT Initialize() throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="removehandle"></a>  CNoWorkerThread::RemoveHandle  
 該当するショートカットは機能しない[CWorkerThread::RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)です。  
  
```
HRESULT RemoveHandle(HANDLE /* hObject
 */) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。  
  
##  <a name="shutdown"></a>  CNoWorkerThread::Shutdown  
 該当するショートカットは機能しない[CWorkerThread::Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)です。  
  
```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```  
  
### <a name="return-value"></a>戻り値  
 常に S_OK を返します。  
  
### <a name="remarks"></a>コメント  
 このクラスで提供される実装では、何も行われません。
