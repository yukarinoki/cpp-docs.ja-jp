---
title: 労働者の原型
ms.date: 11/04/2016
helpviewer_keywords:
- Worker archetype
ms.assetid: 834145cd-09d3-4149-bc99-620e1871cbfb
ms.openlocfilehash: c9ed9b30b94a8debe133bc213c12063750bfb15a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747345"
---
# <a name="worker-archetype"></a>労働者の原型

*ワーカー*の原型に準拠するクラスは、スレッド プールにキューに置かれた作業項目を処理するコードを提供します。

**実装**

この原型に準拠するクラスを実装するには、クラスに次の機能を提供する必要があります。

|Method|説明|
|------------|-----------------|
|[Initialize](#initialize)|要求が[Execute](#execute)に渡される前にワーカー オブジェクトを初期化するために呼び出されます。|
|[実行](#execute)|作業項目を処理するために呼び出されます。|
|[Terminate](#terminate)|すべての要求が[Execute](#execute)に渡された後にワーカー オブジェクトを初期化解除するために呼び出されます。|

|Typedef|説明|
|-------------|-----------------|
|[要求タイプ](#requesttype)|ワーカー クラスで処理できる作業項目の種類の typedef。|

一般的な*ワーカー*クラスは次のようになります。

[!code-cpp[NVC_ATL_Utilities#137](../../atl/codesnippet/cpp/worker-archetype_1.cpp)]

**既存の実装**

これらのクラスは、この原型に準拠しています。

|クラス|説明|
|-----------|-----------------|
|[国家無福祉士](../../atl/reference/cnonstatelessworker-class.md)|スレッド プールから要求を受信し、要求ごとに作成および破棄されるワーカー オブジェクトに渡します。|

**用途**

これらのテンプレート パラメータは、クラスがこの原型に準拠することを想定しています。

|パラメーター名|使用元|
|--------------------|-------------|
|*ワーカー*|[CThreadPool](../../atl/reference/cthreadpool-class.md)|
|*ワーカー*|[国家無福祉士](../../atl/reference/cnonstatelessworker-class.md)|

### <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="workerarchetypeexecute"></a><a name="execute"></a>労働者のアーキタイプ::実行

作業項目を処理するために呼び出されます。

```cpp
void Execute(
    RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

#### <a name="parameters"></a>パラメーター

*request*<br/>
処理する作業項目。 作業項目の種類は と同じです`RequestType`。

*を使用する*<br/>
ワーカー クラスによって認識されるカスタム パラメーター。 また、と`WorkerArchetype::Initialize``Terminate`に渡されます。

*オーバーラップ*<br/>
作業項目がキューに入っているキューを作成するために使用される[OVERLAPPED](/windows/win32/api/minwinbase/ns-minwinbase-overlapped)構造体へのポインター。

## <a name="workerarchetypeinitialize"></a><a name="initialize"></a>ワーカーアーキタイプ::初期化

要求が に渡される前にワーカー オブジェクトを`WorkerArchetype::Execute`初期化するために呼び出されます。

```
BOOL Initialize(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvパラム*<br/>
ワーカー クラスによって認識されるカスタム パラメーター。 また、と`WorkerArchetype::Terminate``WorkerArchetype::Execute`に渡されます。

### <a name="return-value"></a>戻り値

成功時に TRUE を返し、失敗した場合は FALSE を返します。

## <a name="workerarchetyperequesttype"></a><a name="requesttype"></a>ワーカーアーキタイプ::要求タイプ

ワーカー クラスで処理できる作業項目の種類の typedef。

```
typedef MyRequestType RequestType;
```

### <a name="remarks"></a>解説

この型は、最初のパラメーターとして使用する`WorkerArchetype::Execute`必要があり、ULONG_PTRとの間でキャストできる必要があります。

## <a name="workerarchetypeterminate"></a><a name="terminate"></a>ワーカーアーキタイプ::終了

すべての要求が に渡された後にワーカー オブジェクトを初期化`WorkerArchetype::Execute`解除するために呼び出されます。

```cpp
void Terminate(void* pvParam) throw();
```

#### <a name="parameters"></a>パラメーター

*pvパラム*<br/>
ワーカー クラスによって認識されるカスタム パラメーター。 また、と`WorkerArchetype::Initialize``WorkerArchetype::Execute`に渡されます。

## <a name="see-also"></a>関連項目

[概念](../../atl/active-template-library-atl-concepts.md)<br/>
[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)
