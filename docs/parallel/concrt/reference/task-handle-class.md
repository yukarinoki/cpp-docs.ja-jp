---
description: '詳細情報: task_handle クラス'
title: task_handle クラス
ms.date: 03/27/2019
f1_keywords:
- task_handle
- PPL/concurrency::task_handle
- PPL/concurrency::task_handle::task_handle
helpviewer_keywords:
- task_handle class
ms.assetid: 74a34b15-708b-4231-a509-947874292b13
ms.openlocfilehash: 21fa2a1782fad200061deb1e85bf052613354a34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188223"
---
# <a name="task_handle-class"></a>task_handle クラス

`task_handle` クラスは個々の並列作業項目を表します。 このクラスは、1 つの処理を実行するために必要な命令およびデータをカプセル化します。

## <a name="syntax"></a>構文

```cpp
template<
    typename _Function
>
class task_handle : public ::Concurrency::details::_UnrealizedChore;
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
オブジェクトによって表される作業を実行するために呼び出される関数オブジェクトの型 `task_handle` 。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_handle](#task_handle)|新しい `task_handle` オブジェクトを構築します。 タスクの作業は、コンストラクターへのパラメーターとして指定された関数を呼び出すことによって実行されます。|
|[~ task_handle デストラクター](#dtor)|`task_handle` オブジェクトを破棄します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator ()](#task_handle__operator_call)|タスクハンドルの処理を実行するためにランタイムが呼び出す関数呼び出し演算子。|

## <a name="remarks"></a>解説

`task_handle` オブジェクトをまたはより一般的なオブジェクトと組み合わせて使用して `structured_task_group` `task_group` 、作業を並列タスクに分解することができます。 詳細については、「 [タスクの並列](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)化」を参照してください。

オブジェクトの作成者は、 `task_handle` 同時実行ランタイムで不要になるまで、作成されたオブジェクトの有効期間を維持する必要があることに注意して `task_handle` ください。 通常、これは、 `task_handle` オブジェクトが `wait` `run_and_wait` `task_group` キューに置かれているまたはのメソッドが呼び出されるまで、オブジェクトが破棄されないことを意味し `structured_task_group` ます。

`task_handle` オブジェクトは通常、C++ ラムダと組み合わせて使用されます。 ラムダの実際の型がわからないため、 [make_task](concurrency-namespace-functions.md#make_task) 関数は通常、オブジェクトの作成に使用され `task_handle` ます。

ランタイムは、オブジェクトに渡す作業関数のコピーを作成し `task_handle` ます。 したがって、オブジェクトに渡す関数オブジェクトで発生した状態の変更 `task_handle` は、その関数オブジェクトのコピーには表示されません。

## <a name="inheritance-hierarchy"></a>継承階層

`task_handle`

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="operator"></a><a name="task_handle__operator_call"></a> operator ()

タスクハンドルの処理を実行するためにランタイムが呼び出す関数呼び出し演算子。

```cpp
void operator()() const;
```

## <a name="task_handle"></a><a name="task_handle"></a> task_handle

新しい `task_handle` オブジェクトを構築します。 タスクの作業は、コンストラクターへのパラメーターとして指定された関数を呼び出すことによって実行されます。

```cpp
task_handle(const _Function& _Func);
```

### <a name="parameters"></a>パラメーター

*_Func*<br/>
オブジェクトによって表される作業を実行するために呼び出される関数 `task_handle` 。 これには、ラムダファンクタ、関数へのポインター、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートする任意のオブジェクトを指定でき `void operator()()` ます。

### <a name="remarks"></a>解説

ランタイムは、コンストラクターに渡す作業関数のコピーを作成します。 したがって、オブジェクトに渡す関数オブジェクトで発生した状態の変更 `task_handle` は、その関数オブジェクトのコピーには表示されません。

## <a name="task_handle"></a><a name="dtor"></a> ~ task_handle

`task_handle` オブジェクトを破棄します。

```cpp
~task_handle();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)
