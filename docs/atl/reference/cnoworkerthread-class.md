---
description: '詳細情報: CNoWorkerThread クラス'
title: CNoWorkerThread クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CNoWorkerThread class
ms.assetid: 29f06bae-b658-4aac-9c14-331e996d25d1
ms.openlocfilehash: 5159c04a8390f8933291f697faccedb7353fb48e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141415"
---
# <a name="cnoworkerthread-class"></a>CNoWorkerThread クラス

動的キャッシュのメンテナンスを無効にする場合は、このクラスをテンプレートパラメーターの引数として `MonitorClass` キャッシュクラスに使用します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
class CNoWorkerThread
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CNoWorkerThread:: AddHandle](#addhandle)|[CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)と同等ではない関数。|
|[CNoWorkerThread:: AddTimer](#addtimer)|[CWorkerThread:: AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)と同等ではない機能。|
|[CNoWorkerThread:: GetThreadHandle](#getthreadhandle)|[CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)と同等ではない関数。|
|[CNoWorkerThread:: GetThreadId](#getthreadid)|[CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)と同等ではない関数。|
|[CNoWorkerThread:: Initialize](#initialize)|[CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize)と同等ではない関数。|
|[CNoWorkerThread:: RemoveHandle](#removehandle)|[CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)と同等ではない関数。|
|[CNoWorkerThread:: Shutdown](#shutdown)|[CWorkerThread:: Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)と同等ではない機能。|

## <a name="remarks"></a>解説

このクラスは、 [CWorkerThread](../../atl/reference/cworkerthread-class.md)と同じパブリックインターフェイスを提供します。 このインターフェイスは、テンプレートパラメーターによってキャッシュクラスに提供されることが想定されてい `MonitorClass` ます。

このクラスのメソッドは、何も実行しないように実装されています。 HRESULT を返すメソッドは常に S_OK を返し、ハンドルまたはスレッド ID を返すメソッドは常に0を返します。

## <a name="requirements"></a>要件

**ヘッダー:** atlutil. h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a> CNoWorkerThread:: AddHandle

[CWorkerThread:: AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)と同等ではない関数。

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>戻り値

常に S_OK を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a> CNoWorkerThread:: AddTimer

[CWorkerThread:: AddTimer](../../atl/reference/cworkerthread-class.md#addtimer)と同等ではない機能。

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>戻り値

常に S_OK を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a> CNoWorkerThread:: GetThreadHandle

[CWorkerThread:: GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle)と同等ではない関数。

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>戻り値

常に NULL が返されます。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a> CNoWorkerThread:: GetThreadId

[CWorkerThread:: GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid)と同等ではない関数。

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a> CNoWorkerThread:: Initialize

[CWorkerThread:: Initialize](../../atl/reference/cworkerthread-class.md#initialize)と同等ではない関数。

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>戻り値

常に S_OK を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a> CNoWorkerThread:: RemoveHandle

[CWorkerThread:: RemoveHandle](../../atl/reference/cworkerthread-class.md#removehandle)と同等ではない関数。

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>戻り値

常に S_OK を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a> CNoWorkerThread:: Shutdown

[CWorkerThread:: Shutdown](../../atl/reference/cworkerthread-class.md#shutdown)と同等ではない機能。

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>戻り値

常に S_OK を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装では、何も行われません。
