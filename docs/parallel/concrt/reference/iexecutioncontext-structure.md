---
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
ms.openlocfilehash: 532247ca1776452ad32476d2bcdfafcee3481058
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358802"
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
|[IExecutionコンテキスト::Dパッチ](#dispatch)|スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメインワーカールーチンである必要があります。|
|[を実行コンテキスト::取得Id](#getid)|実行コンテキストの一意の識別子を返します。|
|[を実行コンテキスト::プロキシを取得します。](#getproxy)|このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。|
|[を実行コンテキスト::スケジューラを取得します。](#getscheduler)|この実行コンテキストが属するスケジューラへのインターフェイスを返します。|
|[を実行コンテキスト::セットプロキシ](#setproxy)|スレッド プロキシをこの実行コンテキストに関連付けます。 関連付けられたスレッド プロキシは、コンテキストのメソッドの実行を開始する直前に`Dispatch`このメソッドを呼び出します。|

## <a name="remarks"></a>解説

同時実行ランタイムのリソース マネージャーとインターフェイスするカスタム スケジューラを実装する場合は、`IExecutionContext`インターフェイスを実装する必要があります。 リソース マネージャーによって作成されたスレッドは、メソッドを実行することによってスケジューラの代わりに処理`IExecutionContext::Dispatch`を実行します。

## <a name="inheritance-hierarchy"></a>継承階層

`IExecutionContext`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iexecutioncontextdispatch-method"></a><a name="dispatch"></a>メソッド:D実行コンテキスト

スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメインワーカールーチンである必要があります。

```cpp
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>パラメーター

*状態をディスパッチします。*<br/>
この実行コンテキストがディスパッチされる状態へのポインター。 ディスパッチ状態の詳細については、「 [DispatchState](dispatchstate-structure.md)」を参照してください。

## <a name="iexecutioncontextgetid-method"></a><a name="getid"></a>メソッドを取得します。

実行コンテキストの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>解説

インターフェイスを Resource `GetExecutionContextId` Manager によって提供されるメソッドのパラメーターとして使用する前`IExecutionContext`に、このメソッドを使用して、インターフェイスを実装するオブジェクトの一意の識別子を取得する必要があります。 関数が呼び出されたときに、同じ識別子`GetId`を返す必要があります。

別のソースから取得した識別子は、未定義の動作を生じる可能性があります。

## <a name="iexecutioncontextgetproxy-method"></a><a name="getproxy"></a>メソッドを取得します。

このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。

```cpp
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>戻り値

`IThreadProxy` インターフェイスです。 実行コンテキストのスレッド プロキシが 呼`SetProxy`び出しで初期化されていない場合、関数は を`NULL`返す必要があります。

### <a name="remarks"></a>解説

リソース マネージャーは、コンテキスト`SetProxy`でメソッドを入力する前に、`IThreadProxy`パラメーターとしてインターフェイスを使用して、実行コンテキストで`Dispatch`メソッドを呼び出します。 この引数を格納し、 への呼び出しで`GetProxy()`返す必要があります。

## <a name="iexecutioncontextgetscheduler-method"></a><a name="getscheduler"></a>メソッドを取得します。

この実行コンテキストが属するスケジューラへのインターフェイスを返します。

```cpp
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>戻り値

`IScheduler` インターフェイスです。

### <a name="remarks"></a>解説

実行コンテキストを有効な`IScheduler`インターフェイスで初期化してから、リソース マネージャーによって提供されるメソッドのパラメーターとして使用する必要があります。

## <a name="iexecutioncontextsetproxy-method"></a><a name="setproxy"></a>メソッドを設定します。

スレッド プロキシをこの実行コンテキストに関連付けます。 関連付けられたスレッド プロキシは、コンテキストのメソッドの実行を開始する直前に`Dispatch`このメソッドを呼び出します。

```cpp
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>パラメーター

*プロキシ*<br/>
この実行コンテキストで`Dispatch`メソッドを入力しようとしているスレッド プロキシへのインターフェイス。

### <a name="remarks"></a>解説

パラメーター`pThreadProxy`を保存し、`GetProxy`メソッドの呼び出しで返す必要があります。 リソース マネージャーは、スレッド プロキシがメソッドを実行している間、実行コンテキストに関連付けられているスレッド プロキシが`Dispatch`変更されないことを保証します。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)
