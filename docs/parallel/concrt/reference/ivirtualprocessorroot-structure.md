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
ms.openlocfilehash: 25ede76a81a77d489d0f2316bd3ae4cb7f84d704
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344047"
---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 構造体

スレッド プロキシが実行できるハードウェア スレッドの抽象化です。

## <a name="syntax"></a>構文

```
struct IVirtualProcessorRoot : public IExecutionResource;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IVirtualProcessorRoot::Activate](#activate)|実行コンテキストのインターフェイスに関連付けられたスレッド プロキシさせます`pContext`この仮想プロセッサ ルートで実行を開始します。|
|[IVirtualProcessorRoot::Deactivate](#deactivate)|実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシはへの呼び出しで実行を再開、`Activate`メソッド。|
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|データの個別のプロセッサにシステム上のすべてのプロセッサに対して可視になるメモリ階層に保存されます。 メソッドが戻る前に、完全なメモリ フェンスがすべてのプロセッサで実行されたことを保証します。|
|[IVirtualProcessorRoot::GetId](#getid)|仮想プロセッサ ルートの一意の識別子を返します。|

## <a name="remarks"></a>Remarks

すべての仮想プロセッサ ルートでは、関連付けられている実行リソースがあります。 `IVirtualProcessorRoot`インターフェイスから継承、 [IExecutionResource](iexecutionresource-structure.md)インターフェイス。 複数の仮想プロセッサ ルートが同じ基になるハードウェア スレッドに対応しています。

Resource Manager では、リソースに対する要求への応答内のスケジューラに仮想プロセッサ ルートを付与します。 スケジューラは、仮想プロセッサ ルートを使用して、実行コンテキストでアクティブ化することによって作業を実行します。

## <a name="inheritance-hierarchy"></a>継承階層

[IExecutionResource](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="activate"></a>  Ivirtualprocessorroot::activate メソッド

実行コンテキストのインターフェイスに関連付けられたスレッド プロキシさせます`pContext`この仮想プロセッサ ルートで実行を開始します。

```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサ ルートでディスパッチされる実行コンテキストへのインターフェイス。

### <a name="remarks"></a>Remarks

Resource Manager は、実行コンテキストのインターフェイスに関連付けられていない場合、スレッド プロキシに提供されます。 `pContext`

`Activate`または非アクティブまたは非アクティブ化しようとしていますが、仮想プロセッサ ルート上で、スレッド プロキシを再開する、リソース マネージャーによって返される新しい仮想プロセッサ ルートでの作業の実行を開始するメソッドを使用できます。 参照してください[ivirtualprocessorroot::deactivate](#deactivate)非アクティブ化の詳細についてはします。 非アクティブ化された仮想プロセッサ ルートのパラメーターを再開するときに`pContext`仮想プロセッサ ルートを非アクティブ化するために使用するパラメーターと同じである必要があります。

以降の呼び出しのペアは、最初に仮想プロセッサ ルートがアクティブになると`Deactivate`と`Activate`互いに競合する可能性があります。 つまりへの呼び出しを受信する Resource Manager の許容が`Activate`を受け取る前に、`Deactivate`の本来の呼び出し。

仮想プロセッサ ルートを有効にする場合は、この仮想プロセッサ ルートが現在ビジー状態である Resource Manager へが通知します。 呼び出すことが必要です、スケジューラでは、このルート上で実行する作業を見つけられない場合、`Deactivate`メソッドは、Resource Manager 仮想プロセッサ ルートがアイドル状態であることを通知します。 Resource Manager では、このデータを使用して、分散システムを読み込みます。

`invalid_argument` 場合にスローされる引数`pContext`、値を持つ`NULL`します。

`invalid_operation` 場合にスローされる引数`pContext`この仮想プロセッサ ルートがディスパッチされた最も最近実行コンテキストを表していません。

仮想プロセッサ ルートをアクティブ化は、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。

##  <a name="deactivate"></a>  Ivirtualprocessorroot::deactivate メソッド

実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシはへの呼び出しで実行を再開、`Activate`メソッド。

```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
このルートでディスパッチされているコンテキスト。

### <a name="return-value"></a>戻り値

ブール値。 値**true**スレッド プロキシから返されることを示します、`Deactivate`メソッドへの呼び出しに応答に、`Activate`メソッド。 値`false`スレッド プロキシは、Resource Manager での notification イベントに応答でメソッドから返されることを示します。 ユーザー モード スケジュール可能 (UMS) スレッド スケジューラには、スケジューラのコンプリート リスト項目に表示されて、そのスケジューラがそれらを処理するために必要なことを示します。

### <a name="remarks"></a>Remarks

スケジューラのすべての作業が見つからない場合は、仮想プロセッサ ルートを実行を一時的に停止するのにには、このメソッドを使用します。 呼び出し、`Deactivate`内からメソッドを生成する必要があります、`Dispatch`と仮想プロセッサ ルートが最後にアクティブ化実行コンテキストのメソッド。 つまり、呼び出しスレッド プロキシ、`Deactivate`メソッドは、仮想プロセッサ ルートで現在実行されている 1 つである必要があります。 実行しているのではない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作する可能性があります。

非アクティブ化された仮想プロセッサ ルートがへの呼び出しに起こされる可能性があります、`Activate`メソッドに渡された同じ引数で、`Deactivate`メソッド。 呼び出しを確保するため、スケジューラは、`Activate`と`Deactivate`メソッドはペアになっているが、特定の順序で受信する必要はありません。 Resource Manager は、呼び出しを受け取る処理できる、`Activate`メソッドへの呼び出しを受信する前に、`Deactivate`の本来のメソッド。

仮想プロセッサ ルートが起動する場合とからの戻り値、`Deactivate`メソッドは、値**false**、スケジューラを使用して UMS の完了リストをクエリする必要があります、`IUMSCompletionList::GetUnblockNotifications`メソッド、act、その情報にし、その後、`Deactivate`メソッドを再度します。 これは、手順を繰り返しますようになるまで、`Deactivate`メソッドが値を返します`true`します。

`invalid_argument` 場合にスローされる引数`pContext`に NULL 値があります。

`invalid_operation` 仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`この仮想プロセッサ ルートがディスパッチされた最も最近実行コンテキストを表していません。

仮想プロセッサ ルートを非アクティブ化の動作では、1 つで、基になるハードウェア スレッドのサブスクリプション レベルが低くなります。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。

##  <a name="ensurealltasksvisible"></a>  Ivirtualprocessorroot::ensurealltasksvisible メソッド

データの個別のプロセッサにシステム上のすべてのプロセッサに対して可視になるメモリ階層に保存されます。 メソッドが戻る前に、完全なメモリ フェンスがすべてのプロセッサで実行されたことを保証します。

```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサ ルートでディスパッチされているコンテキスト。

### <a name="remarks"></a>Remarks

役立つこのメソッドをスケジューラに新しい作業の追加仮想プロセッサ ルートの非アクティブ化を同期するときにします。 パフォーマンス上の理由から、1 つのプロセッサで実行中のスレッドによって追加された作業項目が他のすべてのプロセッサにすぐに表示されないことを意味するメモリ バリアを実行することがなく、スケジューラに作業項目を追加することができます。 組み合わせてこのメソッドを使用して、`Deactivate`スケジューラのコレクションで作業項目が存在している間、スケジューラに仮想プロセッサすべて非アクティブ化しないことを確認するメソッドのルートします。

呼び出し、`EnsureAllTasksVisibleThe`内からメソッドを生成する必要があります、`Dispatch`と仮想プロセッサ ルートが最後にアクティブ化実行コンテキストのメソッド。 つまり、呼び出しスレッド プロキシ、`EnsureAllTasksVisible`メソッドは、仮想プロセッサ ルートで現在実行されている 1 つである必要があります。 実行しているのではない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作する可能性があります。

`invalid_argument` 場合にスローされる引数`pContext`、値を持つ`NULL`します。

`invalid_operation` 仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`この仮想プロセッサ ルートがディスパッチされた最も最近実行コンテキストを表していません。

##  <a name="getid"></a>  Ivirtualprocessorroot::getid メソッド

仮想プロセッサ ルートの一意の識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

整数の識別子。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
