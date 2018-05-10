---
title: IVirtualProcessorRoot 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Activate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::Deactivate
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::EnsureAllTasksVisible
- CONCRTRM/concurrency::IVirtualProcessorRoot::IVirtualProcessorRoot::GetId
dev_langs:
- C++
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9620ee391b525356bfdb50b00d7e76c03b480815
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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
|[IVirtualProcessorRoot::Activate](#activate)|実行コンテキストのインターフェイスに関連付けられたスレッド プロキシさせます`pContext`この仮想プロセッサ ルートでの実行を開始します。|  
|[IVirtualProcessorRoot::Deactivate](#deactivate)|実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシが再開されますへの呼び出しで実行されている、`Activate`メソッドです。|  
|[IVirtualProcessorRoot::EnsureAllTasksVisible](#ensurealltasksvisible)|システム上のすべてのプロセッサに対して可視になる個々 のプロセッサのメモリ階層内に格納されているデータが発生します。 メソッドが戻る前に、完全なメモリ フェンスがすべてのプロセッサで実行されたことを保証します。|  
|[IVirtualProcessorRoot::GetId](#getid)|仮想プロセッサ ルートの一意の識別子を返します。|  
  
## <a name="remarks"></a>コメント  
 すべての仮想プロセッサ ルートでは、関連付けられた実行リソースがします。 `IVirtualProcessorRoot`インターフェイスから継承、 [IExecutionResource](iexecutionresource-structure.md)インターフェイスです。 複数の仮想プロセッサ ルートが同じ基になるハードウェア スレッドに対応しています。  
  
 リソース マネージャーは、仮想プロセッサ ルートをスケジューラにリソースに対する要求に応答を許可します。 スケジューラは、仮想プロセッサ ルートを使用して、実行コンテキストによりアクティブ化する作業を行うことができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="activate"></a>  Ivirtualprocessorroot::activate メソッド  
 実行コンテキストのインターフェイスに関連付けられたスレッド プロキシさせます`pContext`この仮想プロセッサ ルートでの実行を開始します。  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 この仮想プロセッサ ルートでディスパッチされる実行コンテキストへのインターフェイス。  
  
### <a name="remarks"></a>コメント  
 1 つは、実行コンテキストのインターフェイスに関連付けられていない場合、リソース マネージャーは、スレッド プロキシを提供します。 `pContext`  
  
 `Activate`リソース マネージャーによって返される新しい仮想プロセッサ ルートでの作業の実行を開始するかが非アクティブ化または非アクティブ化しようとしている仮想プロセッサ ルートで、スレッド プロキシを再開するメソッドを使用できます。 参照してください[ivirtualprocessorroot::deactivate](#deactivate)詳細については、非アクティブ化します。 非アクティブ化された仮想プロセッサ ルートのパラメーターを再開するときに`pContext`仮想プロセッサ ルートを非アクティブ化に使用するパラメーターと同じである必要があります。  
  
 仮想プロセッサ ルートが最初に、以降の呼び出しのペアのライセンス認証された後`Deactivate`と`Activate`互いに競合する可能性があります。 つまりのリソース マネージャーへの呼び出しを受信する余裕が`Activate`を受け取る前に、`Deactivate`の本来の呼び出しです。  
  
 仮想プロセッサ ルートをアクティブ化するときに通知する、リソース マネージャーにこの仮想プロセッサ ルートが現在ビジー状態であります。 呼び出すことが予想される場合、スケジューラは、このルート上で実行する作業を見つけることができません、`Deactivate`メソッド、仮想プロセッサ ルートがアイドル状態である旨をリソース マネージャーに通知します。 リソース マネージャーでは、このデータを使用して、分散システムを読み込みます。  
  
 `invalid_argument` スローされる場合、引数`pContext`プロパティ値を持つ`NULL`します。  
  
 `invalid_operation` スローされる場合、引数`pContext`はこの仮想プロセッサ ルートでディスパッチされた最も最近実行コンテキストを表していません。  
  
 仮想プロセッサ ルートをアクティブ化は、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)です。  
  
##  <a name="deactivate"></a>  Ivirtualprocessorroot::deactivate メソッド  
 実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシが再開されますへの呼び出しで実行されている、`Activate`メソッドです。  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 このルートで現在ディスパッチされているコンテキスト。  
  
### <a name="return-value"></a>戻り値  
 ブール値。 値`true`スレッド プロキシから返されることを示す、`Deactivate`メソッドへの呼び出しに応答で、`Activate`メソッドです。 値`false`スレッド プロキシがリソース マネージャーで通知のイベントに応答内のメソッドから返されたことを示します。 ユーザー モード スケジュール可能 (UMS) スレッド スケジューラでは、スケジューラのコンプリート リスト項目に表示されて、そのスケジューラで処理する必要がこれを示します。  
  
### <a name="remarks"></a>コメント  
 スケジューラでの作業が見つからない場合に仮想プロセッサ ルートの実行を一時的に停止するのにには、このメソッドを使用します。 呼び出し、`Deactivate`メソッド内から送信される必要が、`Dispatch`仮想プロセッサ ルートが最後にアクティブ化された実行コンテキストのメソッドです。 呼び出すスレッド プロキシ言い換えると、`Deactivate`メソッドは、仮想プロセッサ ルートで実行されているものである必要があります。 実行していない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作が生じる可能性があります。  
  
 非アクティブ化された仮想プロセッサ ルートをへの呼び出しにウェイク アップ可能性があります、`Activate`に渡された同じ引数で、メソッド、`Deactivate`メソッドです。 呼び出しを確保するため、スケジューラは、`Activate`と`Deactivate`メソッドにペアになっているが、特定の順序で受信する必要はありません。 リソース マネージャーは、呼び出しを受け取る処理できる、`Activate`メソッドへの呼び出しを受信する前に、`Deactivate`の本来メソッドです。  
  
 仮想プロセッサ ルート起動する場合からの戻り値と、`Deactivate`メソッドは値`false`、スケジューラを使用して UMS の完了リストを照会する必要があります、`IUMSCompletionList::GetUnblockNotifications`メソッドが、その情報に基づいて行動し、を後で呼び出す`Deactivate`メソッドを再度です。 これは、手順を繰り返しますとしてそのような時間まで、`Deactivate`メソッドの値を返します`true`です。  
  
 `invalid_argument` スローされる場合、引数`pContext`プロパティ値を持つ`NULL`します。  
  
 `invalid_operation` 仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`はこの仮想プロセッサ ルートでディスパッチされた最も最近実行コンテキストを表していません。  
  
 仮想プロセッサ ルートを非アクティブ化の動作は、サブスクリプション レベルの基になるハードウェア スレッドの 1 つ減少します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)です。  
  
##  <a name="ensurealltasksvisible"></a>  Ivirtualprocessorroot::ensurealltasksvisible メソッド  
 システム上のすべてのプロセッサに対して可視になる個々 のプロセッサのメモリ階層内に格納されているデータが発生します。 メソッドが戻る前に、完全なメモリ フェンスがすべてのプロセッサで実行されたことを保証します。  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 この仮想プロセッサ ルートで現在ディスパッチされているコンテキスト。  
  
### <a name="remarks"></a>コメント  
 有用なこのメソッドを追加すると、スケジューラに新しい作業の非アクティブ化の仮想プロセッサ ルートを同期するときにします。 パフォーマンス向上のため、スケジューラに 1 つのプロセッサで実行中のスレッドによって追加された作業項目が他のすべてのプロセッサにすぐに表示されないことを意味するメモリ バリアを実行することがなく作業項目を追加することができます。 組み合わせてこのメソッドを使用して、`Deactivate`メソッドが、スケジューラに仮想プロセッサすべて非アクティブ化できないことを確認することができます、スケジューラのコレクションで作業項目が存在している間のルートです。  
  
 呼び出し、`EnsureAllTasksVisibleThe`メソッド内から送信される必要が、`Dispatch`仮想プロセッサ ルートが最後にアクティブ化された実行コンテキストのメソッドです。 呼び出すスレッド プロキシ言い換えると、`EnsureAllTasksVisible`メソッドは、仮想プロセッサ ルートで実行されているものである必要があります。 実行していない仮想プロセッサ ルートでメソッドを呼び出すと、未定義の動作が生じる可能性があります。  
  
 `invalid_argument` スローされる場合、引数`pContext`プロパティ値を持つ`NULL`します。  
  
 `invalid_operation` 仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`はこの仮想プロセッサ ルートでディスパッチされた最も最近実行コンテキストを表していません。  
  
##  <a name="getid"></a>  Ivirtualprocessorroot::getid メソッド  
 仮想プロセッサ ルートの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 整数の識別子。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
