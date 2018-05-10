---
title: IThreadProxy 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IThreadProxy
- CONCRTRM/concurrency::IThreadProxy
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::GetId
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchOut
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::SwitchTo
- CONCRTRM/concurrency::IThreadProxy::IThreadProxy::YieldToSystem
dev_langs:
- C++
helpviewer_keywords:
- IThreadProxy structure
ms.assetid: feb89241-a555-4e61-ad48-40add54daeca
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbf59302a73374f08f1c226c1e7e56202654dcfb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ithreadproxy-structure"></a>IThreadProxy 構造体
実行スレッドの抽象化です。 作成するスケジューラの `SchedulerType` ポリシー キーに応じて、リソース マネージャーは、通常の Win32 スレッドまたはユーザー モード スケジュール可能 (UMS: User-Mode Schedulable) スレッドによってサポートされるスレッド プロキシを許可します。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでサポートされます。  
  
## <a name="syntax"></a>構文  
  
```
struct IThreadProxy;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IThreadProxy::GetId](#getid)|スレッド プロキシの一意識別子を返します。|  
|[IThreadProxy::SwitchOut](#switchout)|基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。|  
|[Ithreadproxy::switchto](#switchto)|現在実行中のコンテキストから別の名前への協調的なコンテキスト スイッチを実行します。|  
|[IThreadProxy::YieldToSystem](#yieldtosystem)|呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティング システムでは、[次へ] を実行するスレッドを選択します。|  
  
## <a name="remarks"></a>コメント  
 スレッド プロキシは、インターフェイスによって表される実行コンテキストに関連付けられた`IExecutionContext`処理をディスパッチする手段として。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IThreadProxy`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="getid"></a>  Ithreadproxy::getid メソッド  
 スレッド プロキシの一意識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 一意の整数識別子。  
  
##  <a name="switchout"></a>  Ithreadproxy::switchout メソッド  
 基になる仮想プロセッサ ルートからコンテキストの関連付けを解除します。  
  
```
virtual void SwitchOut(SwitchingProxyState switchState = Blocking) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `switchState`  
 切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。  
  
### <a name="remarks"></a>コメント  
 なんらかの理由で、実行している仮想プロセッサ ルートからコンテキストの関連付けを解除する必要がある場合には、`SwitchOut` を使用します。 パラメーター `switchState` に渡す値によって、または仮想プロセッサ ルート上で実行されるかどうかによって、呼び出しはすぐに制御を返すか、またはコンテキストに関連付けられたスレッド プロキシをブロックします。 パラメーターを `SwitchOut` に設定して `Idle` を呼び出すと、エラーになります。 そうことになります、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外。  
  
 `SwitchOut` は、リソース マネージャーから指示があった場合か、オーバーサブスクリプション状態の一時仮想プロセッサ ルートを要求した後、その処理が終了した場合に、スケジューラの仮想プロセッサ ルートの数を減らす必要があるときに便利です。 この場合、メソッドを呼び出す必要がある[IVirtualProcessorRoot::Remove](http://msdn.microsoft.com/en-us/ad699b4a-1972-4390-97ee-9c083ba7d9e4)への呼び出しを行う前に、仮想プロセッサ ルートで`SwitchOut`パラメーターを使用して`switchState`'éý'`Blocking`です。 これによってスレッド プロキシはブロックされ、スケジューラの別の仮想プロセッサ ルートが処理を実行できるようになると、実行を再開します。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については、次を参照してください。 [ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)です。  
  
 また、`SwitchOut` を使用して、仮想プロセッサを再初期化することもできます。これによって、スレッド プロキシをブロックするか、または一時的に実行している仮想プロセッサ ルートと処理をディスパッチしているスケジューラからデタッチしながら、後でアクティブ化可能なようにできます。 スレッド プロキシをブロックする場合には、パラメーター `SwitchOut` を `switchState` に設定して `Blocking` を使用します。 既に説明したように、`SwitchTo` か `IVirtualProcessorRoot::Activate` を使用して後で再開できます。 このスレッド プロキシが実行されている仮想プロセッサ ルートから、そのスレッド プロキシと、仮想プロセッサが関連付けられているスケジューラとを一時的にデタッチする必要がある場合は、パラメーターを `SwitchOut` に設定して `Nesting` を使用します。 仮想プロセッサ ルートで実行中に `SwitchOut` パラメーターを `switchState` に設定して `Nesting` を呼び出した場合、ルートは再初期化され、現在のスレッド プロキシはそれを必要とせずに実行を継続します。 スレッド プロキシが呼び出されるまで、スケジューラが残さと見なされます、 [ithreadproxy::switchout](#switchout)メソッドを`Blocking`後の時点でします。 パラメーターを `SwitchOut` に設定して `Blocking` を再び呼び出すと、コンテキストをブロックされた状態に戻し、`SwitchTo` またはデタッチされたスケジューラの `IVirtualProcessorRoot::Activate` によって再開できるようにします。 これは仮想プロセッサ ルートで実行されていないため、再初期化は行われません。  
  
 再初期化された仮想プロセッサ ルートは、スケジューラがリソース マネージャーから許可された新しい仮想プロセッサ ルートと同様です。 `IVirtualProcessorRoot::Activate` を使った実行コンテキストによりアクティブ化することによって、それを実行に使用できます。  
  
 `SwitchOut` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。  
  
 Visual Studio 2010 に付属のライブラリとヘッダーでは、このメソッドはパラメーターを受け取らず、仮想プロセッサ ルートを再初期化しませんでした。 従来の動作を保持するために、既定のパラメーター値 `Blocking` が用意されています。  
  
##  <a name="switchto"></a>  Ithreadproxy::switchto メソッド  
 現在実行中のコンテキストから別の名前への協調的なコンテキスト スイッチを実行します。  
  
```
virtual void SwitchTo(
    _Inout_ IExecutionContext* pContext,
    SwitchingProxyState switchState) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 協調的に切り替えるには実行コンテキスト。  
  
 `switchState`  
 切り替えを実行しているスレッド プロキシの状態を示します。 `SwitchingProxyState` 型のパラメーター。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、1 つの実行コンテキストを切り替えるから、 [iexecutioncontext::dispatch](iexecutioncontext-structure.md#dispatch)メソッドの最初の実行コンテキスト。 メソッドの実行コンテキストに関連付けます`pContext`いずれかで関連付けられていない場合は、スレッド プロキシをします。 現在のスレッド プロキシの所有権は指定した値によって決定されます、`switchState`引数。  
  
 値を使用して`Idle`リソース マネージャーに、現在実行中のスレッド プロキシを取得するときにします。 呼び出す`SwitchTo`パラメーターを使用して`switchState`に設定`Idle`実行コンテキストと、`pContext`基になる実行リソースでの実行を開始します。 このスレッド プロキシの所有権にリソース マネージャーには転送され、実行コンテキストから返される必要が`Dispatch`メソッド後まもなく`SwitchTo`転送を完了するためを返します。 スレッド プロキシからスレッド プロキシがディスパッチされる実行コンテキストの関連付けを解除して、スケジューラは自由に再利用されるか、適切に破棄します。  
  
 値を使用して`Blocking`このスレッド プロキシをブロックされた状態を入力する場合します。 呼び出す`SwitchTo`パラメーターを使用して`switchState`に設定`Blocking`実行コンテキストと、`pContext`の実行を開始および再開されるまで、現在のスレッド プロキシをブロックします。 スレッド プロキシがの場合、スケジューラが、スレッド プロキシの所有権を保持、`Blocking`状態です。 ブロック状態のスレッド プロキシを再開するには、`SwitchTo` 関数を呼び出してこのスレッド プロキシの実行コンテキストに切り替えます。 関連付けられているコンテキストを使用して仮想プロセッサ ルートをアクティブ化することにより、スレッド プロキシを再開することもできます。 これを行う方法の詳細については、次を参照してください。 [ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)です。  
  
 値を使用して`Nesting`で実行されている仮想プロセッサ ルートからこのスレッド プロキシを一時的にデタッチして、スケジューラの作業にディスパッチします。 呼び出す`SwitchTo`パラメーターを使用して`switchState`に設定`Nesting`実行コンテキストと、`pContext`を実行して、現在を開始するスレッド プロキシも実行を継続の仮想プロセッサ ルートで必要はありません。 スレッド プロキシが呼び出されるまで、スケジューラが残さと見なされます、 [ithreadproxy::switchout](#switchout)後の時点でのメソッドです。 `IThreadProxy::SwitchOut`メソッドでは、仮想プロセッサ ルートがそれを再スケジュールする利用可能になるまでに、スレッド プロキシをブロック可能性があります。  
  
 `SwitchTo` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。 関数のスロー`invalid_argument`場合、パラメーター`pContext`に設定されている`NULL`です。  
  
##  <a name="yieldtosystem"></a>  Ithreadproxy::yieldtosystem メソッド  
 呼び出し元のスレッドから、現在のプロセッサ上で実行する準備が整っている別のスレッドに実行を切り替えます。 オペレーティング システムでは、[次へ] を実行するスレッドを選択します。  
  
```
virtual void YieldToSystem() = 0;
```  
  
### <a name="remarks"></a>コメント  
 正規の Windows スレッドによってバックアップされたスレッド プロキシによって呼び出されると`YieldToSystem`動作 Windows の関数とまったく同じ`SwitchToThread`です。 ただし、ユーザー モード スケジュール可能 (UMS) スレッドから呼び出された場合、`SwitchToThread`関数がオペレーティング システムではなく、ユーザー モード スケジューラに実行する次のスレッドをピッキングのタスクを委任します。 システムのさまざまな準備の整ったスレッドへの切り替えの所定の効果を実現するために使用`YieldToSystem`です。  
  
 `YieldToSystem` は、現在実行中のスレッドを表す `IThreadProxy` インターフェイスで呼び出す必要があります。それ以外の場合、結果は保証されません。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IExecutionContext 構造体](iexecutioncontext-structure.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
