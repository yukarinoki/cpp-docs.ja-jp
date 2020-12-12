---
description: '詳細情報: IExecutionContext 構造体'
title: IExecutionContext 構造体
ms.date: 11/04/2016
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
ms.openlocfilehash: 90802229e878546383f683bc99ffedc9cb5411af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122188"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 構造体

特定の仮想プロセッサで実行でき、協調的にコンテキストを切り替えることができる実行コンテキストへのインターフェイスです。

## <a name="syntax"></a>構文

```cpp
struct IExecutionContext;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IExecutionContext::D ispatch](#dispatch)|スレッドプロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメインワーカールーチンです。|
|[IExecutionContext:: GetId](#getid)|実行コンテキストの一意の識別子を返します。|
|[IExecutionContext:: GetProxy](#getproxy)|このコンテキストを実行しているスレッドプロキシへのインターフェイスを返します。|
|[IExecutionContext:: GetScheduler](#getscheduler)|この実行コンテキストが属するスケジューラへのインターフェイスを返します。|
|[IExecutionContext:: SetProxy](#setproxy)|スレッドプロキシをこの実行コンテキストに関連付けます。 関連付けられたスレッドプロキシは、コンテキストのメソッドの実行を開始する直前に、このメソッドを呼び出し `Dispatch` ます。|

## <a name="remarks"></a>解説

同時実行ランタイムの Resource Manager とのインターフェイスを持つカスタムスケジューラを実装する場合は、インターフェイスを実装する必要があり `IExecutionContext` ます。 リソースマネージャーによって作成されたスレッドは、メソッドを実行して、スケジューラに代わって作業を実行し `IExecutionContext::Dispatch` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`IExecutionContext`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a> IExecutionContext::D ispatch メソッド

スレッドプロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメインワーカールーチンです。

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatchState*<br/>
この実行コンテキストがディスパッチされている状態へのポインター。 ディスパッチ状態の詳細については、「 [DispatchState](dispatchstate-structure.md)」を参照してください。

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a> IExecutionContext:: GetId メソッド

実行コンテキストの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>解説

インターフェイスを実装するオブジェクトの一意の識別子を取得するには、メソッドを使用する必要があり `GetExecutionContextId` `IExecutionContext` ます。その前に、リソースマネージャーによって提供されるメソッドのパラメーターとしてインターフェイスを使用します。 関数が呼び出されたときに、同じ識別子を返すことが想定されてい `GetId` ます。

別のソースから取得した識別子は、未定義の動作を引き起こす可能性があります。

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a> IExecutionContext:: GetProxy メソッド

このコンテキストを実行しているスレッドプロキシへのインターフェイスを返します。

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>戻り値

`IThreadProxy` インターフェイス。 実行コンテキストのスレッドプロキシがの呼び出しで初期化されていない場合 `SetProxy` 、関数はを返す必要があり `NULL` ます。

### <a name="remarks"></a>解説

リソースマネージャーは、コンテキストのに `SetProxy` `IThreadProxy` メソッドを入力する前に、パラメーターとしてインターフェイスを使用して、実行コンテキストに対してメソッドを呼び出し `Dispatch` ます。 この引数を格納し、の呼び出し時にそれを返すことが想定されてい `GetProxy()` ます。

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a> IExecutionContext:: GetScheduler メソッド

この実行コンテキストが属するスケジューラへのインターフェイスを返します。

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>戻り値

`IScheduler` インターフェイス。

### <a name="remarks"></a>解説

`IScheduler`リソースマネージャーによって提供されるメソッドのパラメーターとして使用する前に、有効なインターフェイスを使用して実行コンテキストを初期化する必要があります。

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a> IExecutionContext:: SetProxy メソッド

スレッドプロキシをこの実行コンテキストに関連付けます。 関連付けられたスレッドプロキシは、コンテキストのメソッドの実行を開始する直前に、このメソッドを呼び出し `Dispatch` ます。

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>パラメーター

*pThreadProxy*<br/>
この実行コンテキストに対してメソッドを入力しようとしているスレッドプロキシへのインターフェイス `Dispatch` 。

### <a name="remarks"></a>解説

パラメーターを保存 `pThreadProxy` して、メソッドの呼び出し時に返すことが想定されてい `GetProxy` ます。 リソースマネージャーは、スレッドプロキシがメソッドを実行している間に、実行コンテキストに関連付けられているスレッドプロキシが変更されないことを保証します `Dispatch` 。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)
