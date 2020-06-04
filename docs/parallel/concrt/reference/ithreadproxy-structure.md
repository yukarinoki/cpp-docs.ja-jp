---
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
ms.openlocfilehash: fc2fb2df06225a5c963fe39178c1b4a10f77953d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368127"
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
|[を使用します。](#getid)|スレッド プロキシの一意の識別子を返します。|
|[Iスレッドプロキシ::スイッチアウト](#switchout)|基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。|
|[を切り替える](#switchto)|現在実行中のコンテキストから別のコンテキストへの協調コンテキスト切り替えを実行します。|
|[システムへの譲り方](#yieldtosystem)|呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティング システムは、次に実行されるスレッドを選択します。|

## <a name="remarks"></a>解説

スレッド プロキシは、作業をディスパッチする手段としてインターフェイス`IExecutionContext`によって表される実行コンテキストに結合されます。

## <a name="inheritance-hierarchy"></a>継承階層

`IThreadProxy`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="ithreadproxygetid-method"></a><a name="getid"></a>メソッドを取得します。

スレッド プロキシの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

## <a name="ithreadproxyswitchout-method"></a><a name="switchout"></a>メソッドの切り替え

基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。

```cpp
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```

### <a name="parameters"></a>パラメーター

*スイッチステート*<br/>
切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。

### <a name="remarks"></a>解説

なんらかの理由で、実行している仮想プロセッサ ルートからコンテキストの関連付けを解除する必要がある場合には、`SwitchOut` を使用します。 パラメーター `switchState` に渡す値によって、または仮想プロセッサ ルート上で実行されるかどうかによって、呼び出しはすぐに制御を返すか、またはコンテキストに関連付けられたスレッド プロキシをブロックします。 パラメーターを `SwitchOut` に設定して `Idle` を呼び出すと、エラーになります。 これを行うと[、invalid_argument](../../../standard-library/invalid-argument-class.md)例外が発生します。

`SwitchOut` は、リソース マネージャーから指示があった場合か、オーバーサブスクリプション状態の一時仮想プロセッサ ルートを要求した後、その処理が終了した場合に、スケジューラの仮想プロセッサ ルートの数を減らす必要があるときに便利です。 この場合は、仮想プロセッサ ルートでメソッド[IVirtualProcessorRoot::Remove](iexecutionresource-structure.md#remove)を呼び出してから、パラメータ`SwitchOut``switchState`をに`Blocking`設定して呼び出す必要があります。 これによってスレッド プロキシはブロックされ、スケジューラの別の仮想プロセッサ ルートが処理を実行できるようになると、実行を再開します。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については[、「IVirtualProcessorRoot::アクティブ化](ivirtualprocessorroot-structure.md#activate)」を参照してください。

また、`SwitchOut` を使用して、仮想プロセッサを再初期化することもできます。これによって、スレッド プロキシをブロックするか、または一時的に実行している仮想プロセッサ ルートと処理をディスパッチしているスケジューラからデタッチしながら、後でアクティブ化可能なようにできます。 スレッド プロキシをブロックする場合には、パラメーター `SwitchOut` を `switchState` に設定して `Blocking` を使用します。 既に説明したように、`SwitchTo` か `IVirtualProcessorRoot::Activate` を使用して後で再開できます。 このスレッド プロキシが実行されている仮想プロセッサ ルートから、そのスレッド プロキシと、仮想プロセッサが関連付けられているスケジューラとを一時的にデタッチする必要がある場合は、パラメーターを `SwitchOut` に設定して `Nesting` を使用します。 仮想プロセッサ ルートで実行中に `SwitchOut` パラメーターを `switchState` に設定して `Nesting` を呼び出した場合、ルートは再初期化され、現在のスレッド プロキシはそれを必要とせずに実行を継続します。 スレッド プロキシは、後`Blocking`で[IThreadProxy::SwitchOut](#switchout)メソッドを呼び出すまでスケジューラを終了したと見なされます。 パラメーターを `SwitchOut` に設定して `Blocking` を再び呼び出すと、コンテキストをブロックされた状態に戻し、`SwitchTo` またはデタッチされたスケジューラの `IVirtualProcessorRoot::Activate` によって再開できるようにします。 これは仮想プロセッサ ルートで実行されていないため、再初期化は行われません。

再初期化された仮想プロセッサ ルートは、スケジューラがリソース マネージャーから許可された新しい仮想プロセッサ ルートと同様です。 `IVirtualProcessorRoot::Activate` を使った実行コンテキストによりアクティブ化することによって、それを実行に使用できます。

`SwitchOut` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。

Visual Studio 2010 に付属のライブラリとヘッダーでは、このメソッドはパラメーターを受け取らず、仮想プロセッサ ルートを再初期化しませんでした。 従来の動作を保持するために、既定のパラメーター値 `Blocking` が用意されています。

## <a name="ithreadproxyswitchto-method"></a><a name="switchto"></a>メソッドの切り替え

現在実行中のコンテキストから別のコンテキストへの協調コンテキスト切り替えを実行します。

```cpp
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
協調的に切り替える実行コンテキスト。

*スイッチステート*<br/>
切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。

### <a name="remarks"></a>解説

このメソッドは、1 つの実行コンテキストから別の実行コンテキストに切り替えるには[、IExecutionContext::D](iexecutioncontext-structure.md#dispatch)最初の実行コンテキストのメソッドを切り替えるために使います。 実行コンテキスト`pContext`がスレッド プロキシに関連付けられていない場合、メソッドはスレッド プロキシに関連付けます。 現在のスレッド プロキシの所有権は、`switchState`引数に指定した値によって決まります。

現在実行中の`Idle`スレッド プロキシをリソース マネージャーに返す場合は、この値を使用します。 パラメーター`SwitchTo``switchState`をに`Idle`設定して呼び出すと、基`pContext`になる実行リソースで実行コンテキストの実行が開始されます。 このスレッド プロキシの所有権はリソース マネージャーに転送され、`Dispatch``SwitchTo`転送を完了するために、すぐに実行コンテキストのメソッドから戻る必要があります。 スレッド プロキシがディスパッチしていた実行コンテキストはスレッド プロキシとの関連付けを解除され、スケジューラは、スレッド プロキシを自由に再利用したり、適切な状態で破棄したりできます。

このスレッド`Blocking`プロキシがブロック状態に入る場合は、この値を使用します。 パラメーター`SwitchTo``switchState`をに`Blocking`設定して呼び出すと、実行`pContext`コンテキストが実行を開始し、再開されるまで現在のスレッド プロキシがブロックされます。 スレッド プロキシが状態の場合、スケジューラはスレッド プロキシの所有権を`Blocking`保持します。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については[、「IVirtualProcessorRoot::アクティブ化](ivirtualprocessorroot-structure.md#activate)」を参照してください。

このスレッド`Nesting`プロキシを、実行中の仮想プロセッサ ルートから一時的にデタッチし、ディスパッチしているスケジューラから一時的にデタッチする場合に、この値を使用します。 パラメーター`SwitchTo``switchState`をに`Nesting`設定して呼び出すと、実行`pContext`コンテキストが実行を開始し、現在のスレッド プロキシも、仮想プロセッサ ルートを必要とせずに実行を継続します。 スレッド プロキシは、後で[IThreadProxy::SwitchOut](#switchout)メソッドを呼び出すまでスケジューラを終了したと見なされます。 メソッド`IThreadProxy::SwitchOut`は、仮想プロセッサ ルートが再スケジュールできるようになるまで、スレッド プロキシをブロックできます。

`SwitchTo` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。 パラメーター`invalid_argument``pContext`が に設定されている場合、関数は`NULL`スローされます。

## <a name="ithreadproxyyieldtosystem-method"></a><a name="yieldtosystem"></a>メソッドを指定します。

呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティング システムは、次に実行されるスレッドを選択します。

```cpp
virtual void YieldToSystem() = 0;
```

### <a name="remarks"></a>解説

通常の Windows スレッドによってバックアップされたスレッド プロキシによって`YieldToSystem`呼び出された場合、Windows`SwitchToThread`関数とまったく同じように動作します。 ただし、ユーザー モードスケジュール可能 (UMS) スレッドから呼び出された`SwitchToThread`場合、この関数は、オペレーティング システムではなく、ユーザー モード スケジューラに実行する次のスレッドを選択するタスクを委任します。 システム内の別の準備完了スレッドに切り替えるという望ましい効果`YieldToSystem`を達成するには、 を使用します。

`YieldToSystem` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IExecutionContext 構造体](iexecutioncontext-structure.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
