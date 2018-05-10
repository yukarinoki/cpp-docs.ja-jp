---
title: task_continuation_context クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
dev_langs:
- C++
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37b218a6db251123513ca155fd491fee7ebabd13
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="taskcontinuationcontext-class"></a>task_continuation_context クラス
`task_continuation_context` クラスを使用すると、継続する場所を指定できます。 のみである Windows ランタイム アプリからこのクラスを使用すると便利です。 非 Windows ランタイム アプリでは、タスク継続の実行コンテキストは、ランタイムによって決定され、構成できません。  
  
## <a name="syntax"></a>構文  
  
```
class task_continuation_context : public details::_ContextCallback;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_current_winrt_context](#get_current_winrt_context)|現在の winrt スレッド コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。|  
|[use_arbitrary](#use_arbitrary)|タスクの継続コンテキストを作成します。このコンテキストを使用すると、ランタイムで継続用の実行コンテキストを選択できます。|  
|[use_current](#use_current)|現在の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。|  
|[use_default](#use_default)|タスクの既定の継続コンテキストを作成します。|  
|[use_synchronous_execution](#use_synchronous_execution)|同期の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_ContextCallback`  
  
 `task_continuation_context`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  

## <a name="get_current_winrt_context"></a> get_current_winrt_context
 現在の WinRT スレッド コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```  
static task_continuation_context get_current_winrt_context();  
```  
  
## <a name="return-value"></a>戻り値  
 現在の Windows ランタイムのスレッド コンテキスト。 非 Windows ランタイム コンテキストから呼び出された場合は、空の task_continuation_context を返します。  
  
## <a name="remarks"></a>コメント  
 `get_current_winrt_context`メソッドは、呼び出し元の Windows ランタイムのスレッド コンテキストをキャプチャします。 非 Windows ランタイムの呼び出し元に、空のコンテキストを返します。  
  
 によって返される値`get_current_winrt_context`ランタイムに、継続元タスクがアパートメントに対応するにはかどうかに関係なく、キャプチャされたコンテキスト (STA と MTA) のアパートメント モデルの継続を実行することを示すために使用できます。 アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。  
  
 このメソッドがに似ていますが、`use_current`メソッドも使用せず C + ネイティブの C++ コードに + CX 拡張機能のサポート。 使用する上級ユーザー作成のものでは +/ネイティブと Windows ランタイムの呼び出し元の両方のライブラリ コードは CX に依存しません。 この機能が必要な場合を除き、ことをお勧め、 `use_current` C + に使用されるメソッド + CX クライアント。  
  
  
##  <a name="use_arbitrary"></a> use_arbitrary 

 タスクの継続コンテキストを作成します。このコンテキストを使用すると、ランタイムで継続用の実行コンテキストを選択できます。  
  
```
static task_continuation_context use_arbitrary();
```  
  
### <a name="return-value"></a>戻り値  
 任意の位置を表すタスクの継続コンテキスト。  
  
### <a name="remarks"></a>コメント  
 この継続コンテキストを使用すると、タスクの継続は、ランタイムが選択したコンテキストで実行されます。これは、継続元タスクがアパートメントに対応している場合でも同様です。  
  
 `use_arbitrary` を使用すると、STA で作成されたアパートメント対応のタスクの継続に関する既定の動作を無効にすることができます。  
  
 このメソッドは、Windows ランタイム アプリで利用できますのみです。  
  
##  <a name="use_current"></a> use_current 

 現在の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。  
  
```
static task_continuation_context use_current();
```  
  
### <a name="return-value"></a>戻り値  
 現在の実行コンテキスト。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、正しいアパートメントで継続が実行できるように、呼び出し元の Windows ランタイムのコンテキストをキャプチャします。  
  
 `use_current` によって返される値を使用することで、ランタイムに対して、継続はキャプチャされたコンテキスト (STA と MTA) で実行されることを示すことができます。このような実行は、継続元タスクがアパートメントに対応しているかどうかに関係なく行われます。 アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。  
  
 このメソッドは、Windows ランタイム アプリで利用できますのみです。  
  
##  <a name="use_default"></a> use_default 

 タスクの既定の継続コンテキストを作成します。  
  
```
static task_continuation_context use_default();
```  
  
### <a name="return-value"></a>戻り値  
 既定の継続コンテキスト。  
  
### <a name="remarks"></a>コメント  
 既定のコンテキストは、継続コンテキスト指定せずに `then` メソッドを呼び出すときに使用されます。 Windows 7 以前に対応した Windows アプリケーション、および Windows 8 以降に対応したデスクトップ アプリケーションでは、ランタイムによって、タスクの継続を実行する状況が判別されます。 ただし、Windows ランタイム アプリでアパートメント対応のタスクの継続に関する既定の継続コンテキストは、アパートメント、`then`が呼び出されます。  
  
 アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。 したがって、Windows ランタイム STA でアパートメント対応のタスクについて継続をスケジュールする場合、継続はその STA で実行されます。  
  
 アパートメント以外に対応するタスクの継続は、ランタイムが選択したコンテキストで実行されます。  

## <a name="use_synchronous_execution"></a> task_continuation_context::use_synchronous_execution  
同期の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。  
  
## <a name="syntax"></a>構文  
  
```  
static task_continuation_context use_synchronous_execution();  
```  
  
## <a name="return-value"></a>戻り値  
 同期の実行コンテキスト。  
  
## <a name="remarks"></a>コメント  
 `use_synchronous_execution`メソッドは、その継続元タスクの完了の原因と、コンテキストで同期的に実行する継続タスクを強制します。  
  
 継続元タスクが既に完了して、継続が関連付けられている場合、継続は継続をアタッチするコンテキストで同期的に実行します。  
  
 
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
