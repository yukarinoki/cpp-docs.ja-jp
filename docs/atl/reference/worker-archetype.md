---
title: ワーカーの原型クラス
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 2e57c575ed778184cf319bb84e61f585fcfa2111
ms.sourcegitcommit: 44eeb065c3148d0484de791080a3f963109744fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/18/2020
ms.locfileid: "79509342"
---
# <a name="worker-archetype"></a>ワーカーの原型クラス

*ワーカー*の原型物に準拠するクラスは、スレッドプールでキューに置かれた作業項目を処理するコードを提供します。

**実装**

この原型に準拠するクラスを実装するには、クラスに次の機能を提供する必要があります。

|方法|説明|
|------------|-----------------|
|[Initialize](#initialize)|要求が[Execute](#execute)に渡される前にワーカーオブジェクトを初期化するために呼び出されます。|
|[実行](#execute)|作業項目を処理するために呼び出されます。|
|[Terminate](#terminate)|すべての要求が[実行](#execute)されると、ワーカーオブジェクトを初期化解除するために呼び出されます。|

|Typedef|説明|
|-------------|-----------------|
|[RequestType](#requesttype)|ワーカークラスで処理できる作業項目の種類の typedef。|

一般的な*ワーカー*クラスは次のようになります。

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**既存の実装**

これらのクラスは、この原型に準拠しています。

|クラス|説明|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|スレッドプールから要求を受信し、要求ごとに作成および破棄されたワーカーオブジェクトに渡します。|

**用途**

これらのテンプレートパラメーターは、クラスがこの原型に準拠していることを想定しています。

|パラメーター名|次のリソースで使用|
|--------------------|-------------|
|*者*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*者*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>要件

**ヘッダー:** atlutil. h

## <a name="execute"></a>WorkerArchetype:: Execute

作業項目を処理するために呼び出されます。

```
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>パラメーター

*request*<br/>
処理される作業項目。 作業項目の種類は `RequestType`と同じです。

*pvWorkerParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 `WorkerArchetype::Initialize` と `Terminate`にも渡されます。

*pOverlapped*<br/>
作業項目がキューに格納されたキューを作成するために使用される、[オーバーラップ](/windows/win32/api/minwinbase/ns-minwinbase-overlapped)された構造体へのポインター。

## <a name="initialize"></a>WorkerArchetype:: Initialize

要求が `WorkerArchetype::Execute`に渡される前にワーカーオブジェクトを初期化するために呼び出されます。

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 `WorkerArchetype::Terminate` と `WorkerArchetype::Execute`にも渡されます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="requesttype"></a>WorkerArchetype:: RequestType

ワーカークラスで処理できる作業項目の種類の typedef。

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>コメント

この型は `WorkerArchetype::Execute` の最初のパラメーターとして使用する必要があり、ULONG_PTR との間でキャストできる必要があります。

## <a name="terminate"></a>WorkerArchetype:: Terminate

すべての要求が `WorkerArchetype::Execute`に渡された後にワーカーオブジェクトを初期化解除するために呼び出されます。

```
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 `WorkerArchetype::Initialize` と `WorkerArchetype::Execute`にも渡されます。

## <a name="see-also"></a>参照

[概念](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
