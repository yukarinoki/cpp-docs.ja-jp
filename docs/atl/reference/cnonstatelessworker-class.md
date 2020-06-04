---
title: CNonStatelessワーカークラス
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
ms.openlocfilehash: 6264bb6bc9070b5ce170b294f9db0d371e7b6b71
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747670"
---
# <a name="cnonstatelessworker-class"></a>CNonStatelessワーカークラス

スレッド プールから要求を受信し、要求ごとに作成および破棄されるワーカー オブジェクトに渡します。

> [!IMPORTANT]
> このクラスとそのメンバーは、Windows ランタイムで実行されるアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
template <class Worker>
class CNonStatelessWorker
```

#### <a name="parameters"></a>パラメーター

*ワーカー*<br/>
ワーカー の[アーキタイプ](../../atl/reference/worker-archetype.md)に準拠するワーカー スレッド クラスで[、CThreadPool](../../atl/reference/cthreadpool-class.md)にキューに置かれた要求を処理するのに適しています。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|[ステートレスワーカー::要求タイプ](#requesttype)|[ワーカーアーキッシュタイプの実装::要求タイプ](worker-archetype.md#requesttype)。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[非ステートレスワーカー::実行](#execute)|[ワーカーアーキタイプの実装::実行](worker-archetype.md#execute).|
|[C非ステートレスワーカー::初期化](#initialize)|[ワーカーアーキッシュタイプの実装::初期化](worker-archetype.md#initialize).|
|[CNonStatelessワーカー::終了](#terminate)|[ワーカーアーキタイプの実装::終了](worker-archetype.md#terminate).|

## <a name="remarks"></a>解説

このクラスは[、CThreadPool](../../atl/reference/cthreadpool-class.md)で使用する単純なワーカー スレッドです。 このクラスは、独自の要求処理機能を提供しません。 代わりに、要求ごとに*ワーカー*のインスタンスを 1 つインスタンス化し、そのインスタンスにメソッドの実装をデリゲートします。

このクラスの利点は、既存のワーカー スレッド クラスの状態モデルを変更する便利な方法を提供することです。 `CThreadPool`スレッドの有効期間に対して 1 つのワーカーを作成するので、ワーカー クラスが状態を保持している場合は、複数の要求にまたがって保持されます。 で使用する前に、その`CNonStatelessWorker`クラスをテンプレートにラップ`CThreadPool`するだけで、ワーカーの有効期間と保持している状態は 1 つの要求に制限されます。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

## <a name="cnonstatelessworkerexecute"></a><a name="execute"></a>非ステートレスワーカー::実行

[ワーカーアーキタイプの実装::実行](worker-archetype.md#execute).

```cpp
void Execute(
    Worker::RequestType request,
    void* pvWorkerParam,
    OVERLAPPED* pOverlapped);
```

### <a name="remarks"></a>解説

このメソッドは、スタック上に*ワーカー*クラスのインスタンスを作成し、そのオブジェクトに対して[Initialize](worker-archetype.md#initialize)を呼び出します。 初期化が成功した場合、このメソッドは同じオブジェクトに対して[Execute](worker-archetype.md#execute)と[Terminate](worker-archetype.md#terminate)も呼び出します。

## <a name="cnonstatelessworkerinitialize"></a><a name="initialize"></a>C非ステートレスワーカー::初期化

[ワーカーアーキッシュタイプの実装::初期化](worker-archetype.md#initialize).

```
BOOL Initialize(void* /* pvParam */) throw();
```

### <a name="return-value"></a>戻り値

常に TRUE を返します。

### <a name="remarks"></a>解説

このクラスは、 で`Initialize`初期化を行いません。

## <a name="cnonstatelessworkerrequesttype"></a><a name="requesttype"></a>ステートレスワーカー::要求タイプ

[ワーカーアーキッシュタイプの実装::要求タイプ](worker-archetype.md#requesttype)。

```
typedef Worker::RequestType RequestType;
```

### <a name="remarks"></a>解説

このクラスは *、Worker*テンプレート パラメーターに使用されるクラスと同じ種類の作業項目を処理します。 詳細については[、「CNonStateless ワーカーの概要](../../atl/reference/cnonstatelessworker-class.md)」を参照してください。

## <a name="cnonstatelessworkerterminate"></a><a name="terminate"></a>CNonStatelessワーカー::終了

[ワーカーアーキタイプの実装::終了](worker-archetype.md#terminate).

```cpp
void Terminate(void* /* pvParam */) throw();
```

### <a name="remarks"></a>解説

このクラスは、 でのクリーンアップ`Terminate`を行いません。

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/cthreadpool-class.md)<br/>
[労働者の原型](../../atl/reference/worker-archetype.md)<br/>
[クラス](../../atl/reference/atl-classes.md)
