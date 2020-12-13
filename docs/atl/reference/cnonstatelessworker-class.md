---
description: 詳細については、CNonStatelessWorker クラス
title: CNonStatelessWorker クラス
ms.date: 11/04/2016
f1_keywords:
- CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker
- ATLUTIL/ATL::CNonStatelessWorker::RequestType
- ATLUTIL/ATL::CNonStatelessWorker::Execute
- ATLUTIL/ATL::CNonStatelessWorker::Initialize
- ATLUTIL/ATL::CNonStatelessWorker::Terminate
helpviewer_keywords:
- CNonStatelessWorker class
ms.assetid: d00936c6-9e7d-49fb-b87d-417b963367d1
ms.openlocfilehash: 68457c9594bfaf4d8dd53acd80d7997355c3a3f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141428"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessWorker クラス

は、スレッドプールから要求を受信し、各要求で作成および破棄されたワーカーオブジェクトにそれらを渡します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>パラメーター

*ワーカー*<br/>
[CThreadPool](../../atl/reference/cthreadpool-class.md)でキューに置かれた要求の処理に適した[ワーカーの原型](../../atl/reference/worker-archetype.md)クラスに準拠するワーカースレッドクラス。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[CNonStatelessWorker:: RequestType](#requesttype)|[Workerarchetype:: RequestType](worker-archetype.md#requesttype)の実装。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CNonStatelessWorker:: Execute](#execute)|[Workerarchetype:: Execute](worker-archetype.md#execute)の実装。|
|[CNonStatelessWorker:: Initialize](#initialize)|[Workerarchetype:: Initialize](worker-archetype.md#initialize)の実装。|
|[CNonStatelessWorker:: Terminate](#terminate)|[Workerarchetype:: Terminate](worker-archetype.md#terminate)の実装。|

## <a name="remarks"></a>解説

このクラスは、 [CThreadPool](../../atl/reference/cthreadpool-class.md)で使用するための単純なワーカースレッドです。 このクラスは、独自の要求処理機能を提供しません。 代わりに、要求ごとに *ワーカー* のインスタンスを1つインスタンス化し、そのメソッドの実装をそのインスタンスに委任します。

このクラスの利点は、既存のワーカースレッドクラスの状態モデルを変更する便利な方法が提供されることです。 `CThreadPool` は、スレッドの有効期間にわたって1つのワーカーを作成します。そのため、ワーカークラスが状態を保持している場合は、複数の要求にわたって保持されます。 で使用する前に、そのクラスをテンプレートにラップするだけで `CNonStatelessWorker` `CThreadPool` 、ワーカーの有効期間と保持される状態は1つの要求に制限されます。

## <a name="requirements"></a>要件

**ヘッダー:** atlutil. h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a> CNonStatelessWorker:: Execute

[Workerarchetype:: Execute](worker-archetype.md#execute)の実装。

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>解説

このメソッドは、スタックに *ワーカー* クラスのインスタンスを作成し、そのオブジェクトで [Initialize](worker-archetype.md#initialize) を呼び出します。 初期化が成功した場合、このメソッドは、同じオブジェクトに対して [Execute](worker-archetype.md#execute) と [Terminate](worker-archetype.md#terminate) も呼び出します。

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a> CNonStatelessWorker:: Initialize

[Workerarchetype:: Initialize](worker-archetype.md#initialize)の実装。

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

このクラスでは、での初期化は行われません `Initialize` 。

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a> CNonStatelessWorker:: RequestType

[Workerarchetype:: RequestType](worker-archetype.md#requesttype)の実装。

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>解説

このクラスは、 *ワーカー* テンプレートパラメーターに使用されるクラスと同じ種類の作業項目を処理します。 詳細については、「 [Cnonstatelessworker の概要](../../atl/reference/cnonstatelessworker-class.md) 」を参照してください。

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a> CNonStatelessWorker:: Terminate

[Workerarchetype:: Terminate](worker-archetype.md#terminate)の実装。

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>解説

このクラスは、でのクリーンアップを実行しません `Terminate` 。

## <a name="see-also"></a>関連項目

[CThreadPool クラス](../../atl/reference/cthreadpool-class.md)<br/>
[ワーカーの原型クラス](../../atl/reference/worker-archetype.md)<br/>
[クラス](../../atl/reference/atl-classes.md)
