---
title: IVirtualProcessorRoot 構造体
ms.date: 11/04/2016
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
ms.openlocfilehash: 869d51144b686dd684f62b337bb90eff8a9a5589
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193953"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 構造体

スレッド プロキシが実行できるハードウェア スレッドの抽象化です。

## <a name="syntax"></a>構文

```cpp
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IVirtualProcessorRoot:: Activate](#activate)|実行コンテキストインターフェイスに関連付けられたスレッドプロキシが、 `pContext` この仮想プロセッサルートで実行を開始します。|
|[IVirtualProcessorRoot::D eactivate](#deactivate)|この仮想プロセッサルートで現在実行されているスレッドプロキシが、実行コンテキストのディスパッチを停止します。 スレッドプロキシは、メソッドの呼び出しで実行を再開し `Activate` ます。|
|[IVirtualProcessorRoot:: EnsureAllTasksVisible](#ensurealltasksvisible)|個々のプロセッサのメモリ階層に格納されているデータが、システム上のすべてのプロセッサに対して可視になります。 これにより、メソッドが返される前に、すべてのプロセッサで完全なメモリフェンスが実行されます。|
|[IVirtualProcessorRoot:: GetId](#getid)|仮想プロセッサルートの一意の識別子を返します。|

## <a name="remarks"></a>解説

すべての仮想プロセッサルートには、実行リソースが関連付けられています。 インターフェイスは、 `IVirtualProcessorRoot` [Iexecutionresource](iexecutionresource-structure.md)インターフェイスから継承されます。 複数の仮想プロセッサルートが、同じ基になるハードウェアスレッドに対応している可能性があります。

リソースマネージャーは、リソースへの要求に応答して、仮想プロセッサルートをスケジューラに付与します。 スケジューラは、仮想プロセッサルートを使用して、実行コンテキストでアクティブ化することで、作業を実行できます。

## <a name="inheritance-hierarchy"></a>継承階層

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="ivirtualprocessorrootactivate-method"></a><a name="activate"></a>IVirtualProcessorRoot:: Activate メソッド

実行コンテキストインターフェイスに関連付けられたスレッドプロキシが、 `pContext` この仮想プロセッサルートで実行を開始します。

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサルートでディスパッチされる実行コンテキストへのインターフェイス。

### <a name="remarks"></a>解説

リソースマネージャーは、実行コンテキストインターフェイスに関連付けられていない場合、スレッドプロキシを提供します。`pContext`

`Activate`メソッドを使用して、リソースマネージャーから返された新しい仮想プロセッサルートでの作業の実行を開始したり、非アクティブ化された仮想プロセッサルートまたは非アクティブ化しようとしている仮想プロセッサルートでスレッドプロキシを再開したりすることができます。 非アクティブ化の詳細については、「 [Ivirtualprocessorroot::D eactivate](#deactivate) 」を参照してください。 非アクティブ化された仮想プロセッサルートを再開する場合、パラメーターは、 `pContext` 仮想プロセッサルートを非アクティブ化するために使用するパラメーターと同じである必要があります。

仮想プロセッサルートが初めてアクティブ化されると、その後のとの呼び出しのペア `Deactivate` `Activate` が相互に競合する可能性があります。 これは、リソースマネージャーがの呼び出しを受け取る前に、その呼び出しを受け取ることができることを意味 `Activate` `Deactivate` します。

仮想プロセッサルートをアクティブ化すると、この仮想プロセッサルートが現在ビジー状態であることがリソースマネージャーに通知されます。 スケジューラがこのルートで実行する作業を見つけられない場合は、 `Deactivate` 仮想プロセッサのルートがアイドル状態であることをリソースマネージャーに通知するメソッドを呼び出す必要があります。 リソースマネージャーは、このデータを使用してシステムの負荷を分散します。

`invalid_argument`引数の値がの場合、がスローされ `pContext` `NULL` ます。

`invalid_operation`引数が、 `pContext` この仮想プロセッサルートによって最後にディスパッチされた実行コンテキストを表していない場合は、がスローされます。

仮想プロセッサルートをアクティブ化すると、基になるハードウェアスレッドのサブスクリプションレベルが1ずつ増加します。 サブスクリプションレベルの詳細については、「 [Iexecutionresource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>IVirtualProcessorRoot::D eactivate メソッド

この仮想プロセッサルートで現在実行されているスレッドプロキシが、実行コンテキストのディスパッチを停止します。 スレッドプロキシは、メソッドの呼び出しで実行を再開し `Activate` ます。

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
このルートによって現在ディスパッチされているコンテキスト。

### <a name="return-value"></a>戻り値

ブール値。 値がの場合は、 **`true`** メソッドの呼び出しに応答して、スレッドプロキシがメソッドから返されたことを示し `Deactivate` `Activate` ます。 値がの場合は、 **`false`** リソースマネージャーの通知イベントに応答して、スレッドプロキシがメソッドから返されたことを示します。 ユーザーモードスケジュール可能 (UMS) スレッドスケジューラでは、これは項目がスケジューラの入力候補一覧に表示され、スケジューラがそれらを処理する必要があることを示します。

### <a name="remarks"></a>解説

スケジューラに作業が見つからない場合に、このメソッドを使用して、仮想プロセッサルートの実行を一時的に停止します。 メソッドの呼び出しは、 `Deactivate` `Dispatch` 仮想プロセッサのルートが最後にアクティブ化された実行コンテキストのメソッド内で発生する必要があります。 言い換えると、メソッドを呼び出すスレッドプロキシは、 `Deactivate` 仮想プロセッサルートで現在実行されているものである必要があります。 実行されていない仮想プロセッサルートでメソッドを呼び出すと、未定義の動作が発生する可能性があります。

非アクティブ化された仮想プロセッサルートは、メソッドへの呼び出しを使用してウェイクアップできます。このメソッドは、 `Activate` メソッドに渡されたものと同じ引数を使用し `Deactivate` ます。 スケジューラは、メソッドとメソッドの呼び出しがペアになっていることを確認する役割を担い `Activate` `Deactivate` ますが、特定の順序で受信する必要はありません。 リソースマネージャーは、メソッドへの呼び出しを受け取る前に、メソッドの呼び出しを受信する処理を行うことができ `Activate` `Deactivate` ます。

仮想プロセッサのルート awakens とメソッドからの戻り値 `Deactivate` が値の場合 **`false`** 、スケジューラはメソッドを使用して UMS のコンプリートリストに対してクエリ `IUMSCompletionList::GetUnblockNotifications` を実行し、その情報を操作した後、 `Deactivate` メソッドを再度呼び出します。 これは、メソッドが値を返すようになるまで繰り返さ `Deactivate` **`true`** れます。

`invalid_argument`引数の値が NULL の場合、がスローされ `pContext` ます。

`invalid_operation`は、仮想プロセッサルートがアクティブになったことがない場合、または引数 `pContext` が、この仮想プロセッサルートによって最後にディスパッチされた実行コンテキストを表していない場合にスローされます。

仮想プロセッサルートを非アクティブ化することにより、基になるハードウェアスレッドのサブスクリプションレベルが1ずつ減少します。 サブスクリプションレベルの詳細については、「 [Iexecutionresource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>IVirtualProcessorRoot:: EnsureAllTasksVisible メソッド

個々のプロセッサのメモリ階層に格納されているデータが、システム上のすべてのプロセッサに対して可視になります。 これにより、メソッドが返される前に、すべてのプロセッサで完全なメモリフェンスが実行されます。

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサルートによって現在ディスパッチされているコンテキスト。

### <a name="remarks"></a>解説

この方法は、新しい作業をスケジューラに追加することで、仮想プロセッサルートの非アクティブ化を同期する場合に便利です。 パフォーマンス上の理由から、メモリバリアを実行せずに作業項目をスケジューラに追加することを決定できます。つまり、あるプロセッサで実行されているスレッドによって追加された作業項目は、他のすべてのプロセッサですぐには表示されません。 このメソッドをメソッドと組み合わせて使用することで、スケジューラ `Deactivate` のコレクションに作業項目が存在している間、スケジューラがすべての仮想プロセッサルートを非アクティブ化しないようにすることができます。

メソッドの呼び出しは、 `EnsureAllTasksVisibleThe` `Dispatch` 仮想プロセッサのルートが最後にアクティブ化された実行コンテキストのメソッド内で発生する必要があります。 言い換えると、メソッドを呼び出すスレッドプロキシは、 `EnsureAllTasksVisible` 仮想プロセッサルートで現在実行されているものである必要があります。 実行されていない仮想プロセッサルートでメソッドを呼び出すと、未定義の動作が発生する可能性があります。

`invalid_argument`引数の値がの場合、がスローされ `pContext` `NULL` ます。

`invalid_operation`は、仮想プロセッサルートがアクティブになったことがない場合、または引数 `pContext` が、この仮想プロセッサルートによって最後にディスパッチされた実行コンテキストを表していない場合にスローされます。

## <a name="ivirtualprocessorrootgetid-method"></a><a name="getid"></a>IVirtualProcessorRoot:: GetId メソッド

仮想プロセッサルートの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

整数識別子。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
