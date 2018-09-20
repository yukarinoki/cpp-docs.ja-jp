---
title: IExecutionContext 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ecb07238fbe3648c857520cce5658b8d2897ee2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46384274"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 構造体

特定の仮想プロセッサで実行でき、協調的にコンテキストを切り替えることができる実行コンテキストへのインターフェイスです。

## <a name="syntax"></a>構文

```
struct IExecutionContext;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IExecutionContext::Dispatch](#dispatch)|スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 スケジューラのワーカーのメイン ルーチンがあります。|
|[IExecutionContext::GetId](#getid)|実行コンテキストの一意の識別子を返します。|
|[IExecutionContext::GetProxy](#getproxy)|このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。|
|[IExecutionContext::GetScheduler](#getscheduler)|この実行コンテキストが属するスケジューラへのインターフェイスを返します。|
|[IExecutionContext::SetProxy](#setproxy)|この実行コンテキストには、スレッド プロキシを関連付けます。 関連付けられたスレッド プロキシが、コンテキストの実行を開始する前に、このメソッドの権限を呼び出す`Dispatch`メソッド。|

## <a name="remarks"></a>Remarks

カスタム スケジューラを同時実行ランタイムの Resource Manager でのインターフェイスを実装する場合は、実装する必要があります。、`IExecutionContext`インターフェイス。 Resource Manager によって作成されたスレッドが実行することによって、スケジューラに代わって処理を実行、`IExecutionContext::Dispatch`メソッド。

## <a name="inheritance-hierarchy"></a>継承階層

`IExecutionContext`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="dispatch"></a>  Iexecutioncontext::dispatch メソッド

スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 スケジューラのワーカーのメイン ルーチンがあります。

```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```

### <a name="parameters"></a>パラメーター

*pDispatchState*<br/>
この実行コンテキストがディスパッチされる状態へのポインター。 ディスパッチの状態の詳細については、次を参照してください。 [DispatchState](dispatchstate-structure.md)します。

##  <a name="getid"></a>  Iexecutioncontext::getid メソッド

実行コンテキストの一意の識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>Remarks

メソッドを使用する必要があります`GetExecutionContextId`を実装するオブジェクトの一意の識別子を取得する、`IExecutionContext`インターフェイス、メソッドのパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでを指定します。 同じ識別子を返す予想されるときに、`GetId`関数が呼び出されます。

別のソースから取得した識別子は、未定義の動作になる可能性があります。

##  <a name="getproxy"></a>  Iexecutioncontext::getproxy メソッド

このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。

```
virtual IThreadProxy* GetProxy() = 0;
```

### <a name="return-value"></a>戻り値

`IThreadProxy` インターフェイス。 呼び出して、実行コンテキストのスレッド プロキシが初期化されていない場合`SetProxy`、関数が返す必要があります`NULL`します。

### <a name="remarks"></a>Remarks

Resource Manager を呼び出す、`SetProxy`実行コンテキストのメソッドで、`IThreadProxy`インターフェイスを入力する前に、パラメーターとして、`Dispatch`メソッドをコンテキストに。 この引数を格納およびへの呼び出しで返すことが求められます`GetProxy()`します。

##  <a name="getscheduler"></a>  Iexecutioncontext::getscheduler メソッド

この実行コンテキストが属するスケジューラへのインターフェイスを返します。

```
virtual IScheduler* GetScheduler() = 0;
```

### <a name="return-value"></a>戻り値

`IScheduler` インターフェイス。

### <a name="remarks"></a>Remarks

有効な実行コンテキストを初期化するために必要な`IScheduler`インターフェイス メソッドのパラメーターとして使用する前に、リソース マネージャーでを指定します。

##  <a name="setproxy"></a>  Iexecutioncontext::setproxy メソッド

この実行コンテキストには、スレッド プロキシを関連付けます。 関連付けられたスレッド プロキシが、コンテキストの実行を開始する前に、このメソッドの権限を呼び出す`Dispatch`メソッド。

```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```

### <a name="parameters"></a>パラメーター

*pThreadProxy*<br/>
入力されるスレッド プロキシへのインターフェイス、`Dispatch`メソッドをこの実行コンテキスト。

### <a name="remarks"></a>Remarks

パラメーターを保存することが求め`pThreadProxy`への呼び出しで返すことと、`GetProxy`メソッド。 Resource Manager では、スレッド プロキシが実行中に、実行コンテキストに関連付けられたスレッド プロキシが変更されないことが保証されます、`Dispatch`メソッド。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)
