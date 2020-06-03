---
title: クラス
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
ms.openlocfilehash: 90056e648a53218ac06083d43ca34870e1ca72fc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326708"
---
# <a name="cnoworkerthread-class"></a>クラス

動的キャッシュ保守を無効にする場合`MonitorClass`は、このクラスをテンプレート・パラメーターの引数として使用して、クラスをキャッシュします。

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
|[ハンドルを追加します。](#addhandle)|[Cワーカースレッドの非機能的な同等物::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).|
|[を使用します。](#addtimer)|[Cワーカースレッドの非機能的な同等物::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).|
|[を使用します。](#getthreadhandle)|C ワーカー スレッドの非機能的な同等[物::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).|
|[を使用します。](#getthreadid)|非機能的な同等の[C ワーカー スレッド::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).|
|[初期化](#initialize)|[CWorker スレッドの](../../atl/reference/cworkerthread-class.md#initialize)機能性に相当しません。|
|[ハンドルを削除します。](#removehandle)|[Cワーカースレッド::削除ハンドルと](../../atl/reference/cworkerthread-class.md#removehandle)同等の非機能的な。|
|[CNoワーカースレッド::シャットダウン](#shutdown)|[CWorker スレッド::シャットダウンと](../../atl/reference/cworkerthread-class.md#shutdown)同等の機能を持たない。|

## <a name="remarks"></a>解説

このクラスは[、CWorkerThread](../../atl/reference/cworkerthread-class.md)と同じパブリック インターフェイスを提供します。 このインターフェイスは、`MonitorClass`クラスをキャッシュするテンプレート パラメーターによって提供される必要があります。

このクラスのメソッドは、何も実行しない実装です。 HRESULT を返すメソッドは常にS_OKを返し、HANDLE またはスレッド ID を返すメソッドは常に 0 を返します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="cnoworkerthreadaddhandle"></a><a name="addhandle"></a>ハンドルを追加します。

[Cワーカースレッドの非機能的な同等物::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle).

```
HRESULT AddHandle(HANDLE /* hObject */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */) throw();
```

### <a name="return-value"></a>戻り値

常にS_OK返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadaddtimer"></a><a name="addtimer"></a>を使用します。

[Cワーカースレッドの非機能的な同等物::AddTimer](../../atl/reference/cworkerthread-class.md#addtimer).

```
HRESULT AddTimer(DWORD /* dwInterval */,
    IWorkerThreadClient* /* pClient */,
    DWORD_PTR /* dwParam */,
    HANDLE* /* phTimer */) throw();
```

### <a name="return-value"></a>戻り値

常にS_OK返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadgetthreadhandle"></a><a name="getthreadhandle"></a>を使用します。

C ワーカー スレッドの非機能的な同等[物::GetThreadHandle](../../atl/reference/cworkerthread-class.md#getthreadhandle).

```
HANDLE GetThreadHandle() throw();
```

### <a name="return-value"></a>戻り値

常に NULL が返されます。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadgetthreadid"></a><a name="getthreadid"></a>を使用します。

非機能的な同等の[C ワーカー スレッド::GetThreadId](../../atl/reference/cworkerthread-class.md#getthreadid).

```
DWORD GetThreadId() throw();
```

### <a name="return-value"></a>戻り値

常に 0 を返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadinitialize"></a><a name="initialize"></a>初期化

[CWorker スレッドの](../../atl/reference/cworkerthread-class.md#initialize)機能性に相当しません。

```
HRESULT Initialize() throw();
```

### <a name="return-value"></a>戻り値

常にS_OK返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadremovehandle"></a><a name="removehandle"></a>ハンドルを削除します。

[Cワーカースレッド::削除ハンドルと](../../atl/reference/cworkerthread-class.md#removehandle)同等の非機能的な。

```
HRESULT RemoveHandle(HANDLE /* hObject */) throw();
```

### <a name="return-value"></a>戻り値

常にS_OK返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。

## <a name="cnoworkerthreadshutdown"></a><a name="shutdown"></a>CNoワーカースレッド::シャットダウン

[CWorker スレッド::シャットダウンと](../../atl/reference/cworkerthread-class.md#shutdown)同等の機能を持たない。

```
HRESULT Shutdown(DWORD dwWait = ATL_WORKER_THREAD_WAIT) throw();
```

### <a name="return-value"></a>戻り値

常にS_OK返します。

### <a name="remarks"></a>解説

このクラスによって提供される実装は何もしません。
