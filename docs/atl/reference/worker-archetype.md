---
description: '詳細情報: Worker 原型'
title: ワーカーの原型クラス
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: 8cb8c2b281bbdc074bb700b77a856f4d26c26cf6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157569"
---
# <a name="worker-archetype"></a>ワーカーの原型クラス

*ワーカー* の原型物に準拠するクラスは、スレッドプールでキューに置かれた作業項目を処理するコードを提供します。

**実装**

この原型に準拠するクラスを実装するには、クラスに次の機能を提供する必要があります。

|Method|説明|
|------------|-----------------|
|[初期化する](#initialize)|要求が [Execute](#execute)に渡される前にワーカーオブジェクトを初期化するために呼び出されます。|
|[実行](#execute)|作業項目を処理するために呼び出されます。|
|[Terminate](#terminate)|すべての要求が [実行](#execute)されると、ワーカーオブジェクトを初期化解除するために呼び出されます。|

|Typedef|説明|
|-------------|-----------------|
|[RequestType](#requesttype)|ワーカークラスで処理できる作業項目の種類の typedef。|

一般的な *ワーカー* クラスは次のようになります。

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**既存の実装**

これらのクラスは、この原型に準拠しています。

|クラス|説明|
|-----------|-----------------|
|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|スレッドプールから要求を受信し、要求ごとに作成および破棄されたワーカーオブジェクトに渡します。|

**用途**

これらのテンプレートパラメーターは、クラスがこの原型に準拠していることを想定しています。

|パラメーター名|使用者|
|--------------------|-------------|
|*ワーカー*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*ワーカー*|[CNonStatelessWorker](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>要件

**ヘッダー:** atlutil. h

## <a name="workerarchetypeexecute"></a><a name="execute"></a> WorkerArchetype:: Execute

作業項目を処理するために呼び出されます。

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>パラメーター

*request*<br/>
処理される作業項目。 作業項目の種類はと同じです `RequestType` 。

*pvWorkerParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 また、とにも渡さ `WorkerArchetype::Initialize` `Terminate` れます。

*pOverlapped*<br/>
作業項目がキューに格納されたキューを作成するために使用される、 [オーバーラップ](/windows/win32/api/minwinbase/ns-minwinbase-overlapped) された構造体へのポインター。

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a> WorkerArchetype:: Initialize

要求がに渡される前にワーカーオブジェクトを初期化するために呼び出され `WorkerArchetype::Execute` ます。

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 また、とにも渡さ `WorkerArchetype::Terminate` `WorkerArchetype::Execute` れます。

### <a name="return-value"></a>戻り値

成功した場合は TRUE、失敗した場合は FALSE を返します。

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a> WorkerArchetype:: RequestType

ワーカークラスで処理できる作業項目の種類の typedef。

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>解説

この型は、の最初のパラメーターとして使用する必要があり、 `WorkerArchetype::Execute` ULONG_PTR との間でキャストできる必要があります。

## <a name="workerarchetypeterminate"></a><a name="terminate"></a> WorkerArchetype:: Terminate

すべての要求がに渡された後にワーカーオブジェクトを初期化解除するために呼び出され `WorkerArchetype::Execute` ます。

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvParam*<br/>
ワーカークラスによって認識されるカスタムパラメーター。 また、とにも渡さ `WorkerArchetype::Initialize` `WorkerArchetype::Execute` れます。

## <a name="see-also"></a>関連項目

[概念](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
