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
ms.openlocfilehash: f642a29d0a80568f7a5f2a5e89f6951d4819243e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364256"
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
|[イバーチャプロセッサールート::アクティブ化](#activate)|実行コンテキスト インターフェイス`pContext`に関連付けられているスレッド プロキシを、この仮想プロセッサ ルートで実行を開始します。|
|[イコンビニラルート::Dアクティブ化](#deactivate)|この仮想プロセッサ ルートで現在実行されているスレッド プロキシが、実行コンテキストのディスパッチを停止します。 スレッド プロキシは、メソッドの呼び出しで`Activate`実行を再開します。|
|[イバーチャブルプロセッサルート::すべてのタスクを表示します](#ensurealltasksvisible)|個々のプロセッサのメモリ階層に格納されたデータを、システム上のすべてのプロセッサから参照できるようになります。 メソッドが返される前に、すべてのプロセッサで完全メモリ フェンスが実行されていることを確認します。|
|[を使用します。](#getid)|仮想プロセッサ ルートの一意の識別子を返します。|

## <a name="remarks"></a>解説

すべての仮想プロセッサ ルートには、実行リソースが関連付けられます。 インターフェイス`IVirtualProcessorRoot`は[、IExecutionResource](iexecutionresource-structure.md)インターフェイスから継承します。 複数の仮想プロセッサ ルートが、同じ基になるハードウェア スレッドに対応している場合があります。

リソース マネージャーは、リソースの要求に応じて、スケジューラに仮想プロセッサ ルートを付与します。 スケジューラは、仮想プロセッサ ルートを使用して、実行コンテキストでアクティブ化することで、処理を実行できます。

## <a name="inheritance-hierarchy"></a>継承階層

[をリソースに追加する](iexecutionresource-structure.md)

`IVirtualProcessorRoot`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="ivirtualprocessorrootactivate-method"></a><a name="activate"></a>メソッドのアクティブ化

実行コンテキスト インターフェイス`pContext`に関連付けられているスレッド プロキシを、この仮想プロセッサ ルートで実行を開始します。

```cpp
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサ ルートにディスパッチされる実行コンテキストへのインターフェイス。

### <a name="remarks"></a>解説

実行コンテキスト インターフェイスに関連付けられていない場合、リソース マネージャーはスレッド プロキシを提供します。`pContext`

この`Activate`メソッドを使用すると、Resource Manager から返された新しい仮想プロセッサ ルートでの処理を開始したり、非アクティブ化または非アクティブ化しようとしている仮想プロセッサ ルートでスレッド プロキシを再開したりできます。 非アクティブ化の詳細については[、「IVirtualProcessorRoot::Deactivate」](#deactivate)を参照してください。 非アクティブ化された仮想プロセッサー・ルートを再開する場合、パラメーター`pContext`は、仮想プロセッサー・ルートを非アクティブ化するために使用されるパラメーターと同じでなければなりません。

仮想プロセッサ ルートが初めてアクティブ化されると、その後の呼び出し`Deactivate`の`Activate`ペアが互いに競合する可能性があります。 つまり、リソース マネージャーは、呼び出しを受信`Activate`する前に呼び出`Deactivate`しを受け取ることは許容されます。

仮想プロセッサ ルートをアクティブ化すると、この仮想プロセッサ ルートが現在作業中であることをリソース マネージャーに通知します。 スケジューラがこのルートで実行する作業を見つけられない場合は、仮想プロセッサ ルートが`Deactivate`アイドル状態であることをリソース マネージャーに通知するメソッドを呼び出す必要があります。 リソース マネージャーは、このデータを使用してシステムの負荷を分散します。

`invalid_argument`引数`pContext`に値`NULL`が含まれる場合にスローされます。

`invalid_operation`この仮想プロセッサ ルート`pContext`によって最後にディスパッチされた実行コンテキストを引数が表していない場合にスローされます。

仮想プロセッサ ルートをアクティブ化すると、基になるハードウェア スレッドのサブスクリプション レベルが 1 つ増えます。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>メソッドをアクティブに:D仮想プロセッサルート

この仮想プロセッサ ルートで現在実行されているスレッド プロキシが、実行コンテキストのディスパッチを停止します。 スレッド プロキシは、メソッドの呼び出しで`Activate`実行を再開します。

```cpp
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
現在このルートによってディスパッチされているコンテキスト。

### <a name="return-value"></a>戻り値

ブール値。 値が**true**の場合、`Deactivate`メソッドの呼び出しに応答してメソッドから返`Activate`されたスレッド プロキシを示します。 値が、`false`リソース マネージャーの通知イベントに応答してメソッドから返されたことを示します。 ユーザー モードのスケジュール可能な (UMS) スレッド スケジューラでは、これは、項目がスケジューラの完了リストに表示され、それらを処理するためにスケジューラが必要であることを示します。

### <a name="remarks"></a>解説

スケジューラ内に作業が見つからない場合に、仮想プロセッサ ルートの実行を一時的に停止するには、このメソッドを使用します。 メソッドの呼び`Deactivate`出しは、仮想プロセッサ`Dispatch`ルートが最後にアクティブ化された実行コンテキストのメソッド内から発信される必要があります。 つまり、`Deactivate`メソッドを呼び出すスレッド プロキシは、仮想プロセッサ ルートで現在実行されているスレッド プロキシである必要があります。 実行していない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作が発生する可能性があります。

非アクティブ化された仮想プロセッサ ルートは、`Activate`メソッドに渡された引数と同じ引数を使用して、メソッドの`Deactivate`呼び出しで起動できます。 スケジューラは、`Activate`メソッドと`Deactivate`メソッドの呼び出しがペアであることを保証する責任がありますが、特定の順序で受信する必要はありません。 リソース マネージャーは、メソッドの呼び出`Activate`しを受け取る前に、`Deactivate`メソッドの呼び出しを受け取る処理を行うことができます。

仮想プロセッサ ルートが起き上がり`Deactivate`、メソッドからの戻り値が**false**の場合、スケジューラは`IUMSCompletionList::GetUnblockNotifications`メソッドを介して UMS 入力候補リストを照会し、その情報を`Deactivate`処理してから、メソッドを再度呼び出す必要があります。 メソッドが値`true`を返すまで、この`Deactivate`処理を繰り返す必要があります。

`invalid_argument`は、引数`pContext`に NULL 値が設定されている場合にスローされます。

`invalid_operation`は、仮想プロセッサ ルートがアクティブにされていない場合、または引数`pContext`がこの仮想プロセッサ ルートによって最後にディスパッチされた実行コンテキストを表していない場合にスローされます。

仮想プロセッサ ルートを非アクティブ化すると、基になるハードウェア スレッドのサブスクリプション レベルが 1 つ減ります。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>メソッドを確認します。

個々のプロセッサのメモリ階層に格納されたデータを、システム上のすべてのプロセッサから参照できるようになります。 メソッドが返される前に、すべてのプロセッサで完全メモリ フェンスが実行されていることを確認します。

```cpp
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
この仮想プロセッサ ルートによって現在ディスパッチされているコンテキスト。

### <a name="remarks"></a>解説

この方法は、仮想プロセッサ ルートの非アクティブ化をスケジューラに新しい作業を追加して同期する場合に役立ちます。 パフォーマンス上の理由から、メモリ バリアを実行せずにスケジューラに作業項目を追加する場合があります。 このメソッドを`Deactivate`メソッドと組み合わせて使用すると、スケジューラのコレクションに作業項目が存在している間に、スケジューラがすべての仮想プロセッサ ルートを非アクティブ化しないようにすることができます。

メソッドの呼び`EnsureAllTasksVisibleThe`出しは、仮想プロセッサ`Dispatch`ルートが最後にアクティブ化された実行コンテキストのメソッド内から発信される必要があります。 つまり、`EnsureAllTasksVisible`メソッドを呼び出すスレッド プロキシは、仮想プロセッサ ルートで現在実行されているスレッド プロキシである必要があります。 実行していない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作が発生する可能性があります。

`invalid_argument`引数`pContext`に値`NULL`が含まれる場合にスローされます。

`invalid_operation`は、仮想プロセッサ ルートがアクティブにされていない場合、または引数`pContext`がこの仮想プロセッサ ルートによって最後にディスパッチされた実行コンテキストを表していない場合にスローされます。

## <a name="ivirtualprocessorrootgetid-method"></a><a name="getid"></a>メソッドを使用します。

仮想プロセッサ ルートの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

整数の識別子。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)
