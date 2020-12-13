---
description: IThreadProxy 構造の詳細情報
title: IThreadProxy 構造体
ms.date: 11/04/2016
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
ms.openlocfilehash: e63a4d2bc29a1ae846e30d1b7e93c125def971b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334391"
---
# <a name="ithreadproxy-structure"></a>IThreadProxy 構造体

実行スレッドの抽象化です。 作成するスケジューラの `SchedulerType` ポリシー キーに応じて、リソース マネージャーは、通常の Win32 スレッドまたはユーザー モード スケジュール可能 (UMS: User-Mode Schedulable) スレッドによってサポートされるスレッド プロキシを許可します。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでサポートされます。

## <a name="syntax"></a>構文

```cpp
struct IThreadProxy;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IThreadProxy:: GetId](#getid)|スレッドプロキシの一意の識別子を返します。|
|[IThreadProxy:: SwitchOut](#switchout)|基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。|
|[IThreadProxy:: SwitchTo](#switchto)|現在実行中のコンテキストから別のコンテキストへの協調的なコンテキスト切り替えを実行します。|
|[IThreadProxy:: YieldToSystem](#yieldtosystem)|呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティングシステムは、次に実行されるスレッドを選択します。|

## <a name="remarks"></a>解説

スレッドプロキシは、 `IExecutionContext` 作業をディスパッチする手段として、インターフェイスによって表される実行コンテキストと結合されます。

## <a name="inheritance-hierarchy"></a>継承階層

`IThreadProxy`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="ithreadproxygetid-method"></a><a name="getid"></a> IThreadProxy:: GetId メソッド

スレッドプロキシの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

## <a name="ithreadproxyswitchout-method"></a><a name="switchout"></a> IThreadProxy:: SwitchOut メソッド

基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>パラメーター

*switchState*<br/>
切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。

### <a name="remarks"></a>解説

なんらかの理由で、実行している仮想プロセッサ ルートからコンテキストの関連付けを解除する必要がある場合には、`SwitchOut` を使用します。 パラメーター `switchState` に渡す値によって、または仮想プロセッサ ルート上で実行されるかどうかによって、呼び出しはすぐに制御を返すか、またはコンテキストに関連付けられたスレッド プロキシをブロックします。 パラメーターを `SwitchOut` に設定して `Idle` を呼び出すと、エラーになります。 これにより、 [invalid_argument](../../../standard-library/invalid-argument-class.md) 例外が発生します。

`SwitchOut` は、リソース マネージャーから指示があった場合か、オーバーサブスクリプション状態の一時仮想プロセッサ ルートを要求した後、その処理が終了した場合に、スケジューラの仮想プロセッサ ルートの数を減らす必要があるときに便利です。 この場合、パラメーターをに設定してを呼び出す前に、仮想プロセッサルートに対して [Ivirtualprocessorroot:: Remove](iexecutionresource-structure.md#remove) メソッドを呼び出す必要があり `SwitchOut` `switchState` `Blocking` ます。 これによってスレッド プロキシはブロックされ、スケジューラの別の仮想プロセッサ ルートが処理を実行できるようになると、実行を再開します。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については、「 [Ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate)」を参照してください。

また、`SwitchOut` を使用して、仮想プロセッサを再初期化することもできます。これによって、スレッド プロキシをブロックするか、または一時的に実行している仮想プロセッサ ルートと処理をディスパッチしているスケジューラからデタッチしながら、後でアクティブ化可能なようにできます。 スレッド プロキシをブロックする場合には、パラメーター `SwitchOut` を `switchState` に設定して `Blocking` を使用します。 既に説明したように、`SwitchTo` か `IVirtualProcessorRoot::Activate` を使用して後で再開できます。 このスレッド プロキシが実行されている仮想プロセッサ ルートから、そのスレッド プロキシと、仮想プロセッサが関連付けられているスケジューラとを一時的にデタッチする必要がある場合は、パラメーターを `SwitchOut` に設定して `Nesting` を使用します。 仮想プロセッサ ルートで実行中に `SwitchOut` パラメーターを `switchState` に設定して `Nesting` を呼び出した場合、ルートは再初期化され、現在のスレッド プロキシはそれを必要とせずに実行を継続します。 スレッドプロキシは、後でを使用して [Ithreadproxy:: SwitchOut](#switchout) メソッドを呼び出すまで、スケジューラの外部にあると見なされ `Blocking` ます。 パラメーターを `SwitchOut` に設定して `Blocking` を再び呼び出すと、コンテキストをブロックされた状態に戻し、`SwitchTo` またはデタッチされたスケジューラの `IVirtualProcessorRoot::Activate` によって再開できるようにします。 これは仮想プロセッサ ルートで実行されていないため、再初期化は行われません。

再初期化された仮想プロセッサ ルートは、スケジューラがリソース マネージャーから許可された新しい仮想プロセッサ ルートと同様です。 `IVirtualProcessorRoot::Activate` を使った実行コンテキストによりアクティブ化することによって、それを実行に使用できます。

`SwitchOut` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。

Visual Studio 2010 に付属のライブラリとヘッダーでは、このメソッドはパラメーターを受け取らず、仮想プロセッサ ルートを再初期化しませんでした。 従来の動作を保持するために、既定のパラメーター値 `Blocking` が用意されています。

## <a name="ithreadproxyswitchto-method"></a><a name="switchto"></a> IThreadProxy:: SwitchTo メソッド

現在実行中のコンテキストから別のコンテキストへの協調的なコンテキスト切り替えを実行します。

```cpp
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
協調的に切り替える実行コンテキスト。

*switchState*<br/>
切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。

### <a name="remarks"></a>解説

最初の実行コンテキストの [Iexecutioncontext::D ispatch](iexecutioncontext-structure.md#dispatch) メソッドから別の実行コンテキストに切り替えるには、このメソッドを使用します。 メソッドは、 `pContext` まだ関連付けられていない場合、実行コンテキストをスレッドプロキシに関連付けます。 現在のスレッドプロキシの所有権は、引数に指定した値によって決まり `switchState` ます。

`Idle`現在実行中のスレッドプロキシをリソースマネージャーに返す場合は、値を使用します。 `SwitchTo`パラメーターをに設定してを呼び出すと、 `switchState` `Idle` `pContext` 基になる実行リソースで実行コンテキストの実行が開始されます。 このスレッドプロキシの所有権はリソースマネージャーに転送され、 `Dispatch` 転送を完了するために、が返された直後に実行コンテキストのメソッドから戻ることが想定されてい `SwitchTo` ます。 スレッドプロキシによってディスパッチされた実行コンテキストはスレッドプロキシとの関連付けが解除され、スケジューラは自由に再利用するか、またはそれに応じて破棄することができます。

このスレッドプロキシがブロックされた状態になるようにするには、値を使用し `Blocking` ます。 `SwitchTo`パラメーター `switchState` をに設定してを呼び出すと、実行コンテキストが実行を開始し、現在の `Blocking` `pContext` スレッドプロキシが再開されるまでブロックします。 スレッドプロキシが状態にある場合、スケジューラはスレッドプロキシの所有権を保持し `Blocking` ます。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については、「 [Ivirtualprocessorroot:: Activate](ivirtualprocessorroot-structure.md#activate)」を参照してください。

値を使用して、このスレッドプロキシが実行されている `Nesting` 仮想プロセッサルートからこのスレッドプロキシを一時的にデタッチし、それが処理を行うスケジューラを使用します。 `SwitchTo`パラメーター `switchState` をに設定してを呼び出す `Nesting` と、実行コンテキストが実行を `pContext` 開始し、現在のスレッドプロキシも仮想プロセッサルートを必要とせずに実行を継続します。 スレッドプロキシは、後で [Ithreadproxy:: SwitchOut](#switchout) メソッドを呼び出すまで、スケジューラの外部にあると見なされます。 メソッドは、 `IThreadProxy::SwitchOut` 仮想プロセッサルートを再スケジュールできるようになるまで、スレッドプロキシをブロックする可能性があります。

`SwitchTo` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。 `invalid_argument`パラメーターがに設定されている場合、関数はをスローし `pContext` `NULL` ます。

## <a name="ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a> IThreadProxy:: YieldToSystem メソッド

呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティングシステムは、次に実行されるスレッドを選択します。

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>解説

通常の Windows スレッドによってサポートされるスレッドプロキシによって呼び出されると、は `YieldToSystem` windows の関数と同じように動作 `SwitchToThread` します。 ただし、ユーザーモードスケジュール可能 (UMS) スレッドから呼び出された場合、関数は、 `SwitchToThread` オペレーティングシステムではなく、ユーザーモードスケジューラに対して実行する次のスレッドを選択するタスクを委任します。 システムで別の準備ができているスレッドに切り替えるために必要な効果を実現するには、を使用 `YieldToSystem` します。

`YieldToSystem` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[IExecutionContext 構造体](iexecutioncontext-structure.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
