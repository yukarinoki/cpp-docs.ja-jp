---
description: '詳細情報: task_continuation_context クラス'
title: task_continuation_context クラス
ms.date: 11/04/2016
f1_keywords:
- task_continuation_context
- PPLTASKS/concurrency::task_continuation_context
- PPLTASKS/concurrency::task_continuation_context::get_current_winrt_context
- PPLTASKS/concurrency::task_continuation_context::use_arbitrary
- PPLTASKS/concurrency::task_continuation_context::use_current
- PPLTASKS/concurrency::task_continuation_context::use_default
- PPLTASKS/concurrency::task_continuation_context::use_synchronous_execution
helpviewer_keywords:
- task_continuation_context class
ms.assetid: 1fb5a76a-3682-45c2-a615-8b6b527741f0
ms.openlocfilehash: ff843a84dd3e0bdaeee9df99e91b1708116191d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188301"
---
# <a name="task_continuation_context-class"></a>task_continuation_context クラス

`task_continuation_context` クラスを使用すると、継続する場所を指定できます。 Windows ランタイムアプリからこのクラスを使用する場合にのみ役立ちます。 非 Windows ランタイムアプリの場合、タスクの継続の実行コンテキストはランタイムによって決定され、構成することはできません。

## <a name="syntax"></a>構文

```cpp
class task_continuation_context : public details::_ContextCallback;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[get_current_winrt_context](#get_current_winrt_context)|現在の winrt スレッドコンテキストを表すタスクの継続コンテキストオブジェクトを返します。|
|[use_arbitrary](#use_arbitrary)|タスクの継続コンテキストを作成します。このコンテキストを使用すると、ランタイムで継続用の実行コンテキストを選択できます。|
|[use_current](#use_current)|現在の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。|
|[use_default](#use_default)|タスクの既定の継続コンテキストを作成します。|
|[use_synchronous_execution](#use_synchronous_execution)|同期実行コンテキストを表すタスクの継続コンテキストオブジェクトを返します。|

## <a name="inheritance-hierarchy"></a>継承階層

`_ContextCallback`

`task_continuation_context`

## <a name="requirements"></a>要件

**ヘッダー:** ppltasks.h

**名前空間:** concurrency

## <a name="get_current_winrt_context"></a><a name="get_current_winrt_context"></a> get_current_winrt_context

現在の WinRT スレッドコンテキストを表すタスクの継続コンテキストオブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
static task_continuation_context get_current_winrt_context();
```

### <a name="return-value"></a>戻り値

現在の Windows ランタイムスレッドコンテキスト。 Windows ランタイム以外のコンテキストから呼び出された場合は、空の task_continuation_context を返します。

### <a name="remarks"></a>解説

メソッドは、 `get_current_winrt_context` 呼び出し元の Windows ランタイムスレッドコンテキストをキャプチャします。 このメソッドは、Windows ランタイム以外の呼び出し元に空のコンテキストを返します。

によって返される値を使用すると、 `get_current_winrt_context` 継続元タスクがアパートメントに対応しているかどうかに関係なく、キャプチャされたコンテキスト (STA VS MTA) のアパートメントモデルで継続を実行する必要があることをランタイムに示すことができます。 アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。

このメソッドはメソッドに似  `use_current` ていますが、c++/cx 拡張機能をサポートせずにネイティブ c++ コードで使用することもできます。 これは、ネイティブと Windows ランタイムの両方の呼び出し元に対して C++ の非依存ライブラリコードを記述する高度なユーザーが使用することを目的としています。 この機能が必要な場合を除き、メソッドを使用することをお勧めし `use_current` ます。これは、C++/cx クライアントでのみ使用できます。

## <a name="use_arbitrary"></a><a name="use_arbitrary"></a> use_arbitrary

タスクの継続コンテキストを作成します。このコンテキストを使用すると、ランタイムで継続用の実行コンテキストを選択できます。

### <a name="syntax"></a>構文

```cpp
static task_continuation_context use_arbitrary();
```

### <a name="return-value"></a>戻り値

任意の位置を表すタスクの継続コンテキスト。

### <a name="remarks"></a>解説

この継続コンテキストを使用すると、タスクの継続は、ランタイムが選択したコンテキストで実行されます。これは、継続元タスクがアパートメントに対応している場合でも同様です。

`use_arbitrary` を使用すると、STA で作成されたアパートメント対応のタスクの継続に関する既定の動作を無効にすることができます。

このメソッドは、Windows ランタイムアプリでのみ使用できます。

## <a name="use_current"></a><a name="use_current"></a> use_current

現在の実行コンテキストを表すタスクの継続コンテキスト オブジェクトを返します。

```cpp
static task_continuation_context use_current();
```

### <a name="return-value"></a>戻り値

現在の実行コンテキスト。

### <a name="remarks"></a>解説

このメソッドは、正しいアパートメントで継続が実行できるように、呼び出し元の Windows ランタイムのコンテキストをキャプチャします。

`use_current` によって返される値を使用することで、ランタイムに対して、継続はキャプチャされたコンテキスト (STA と MTA) で実行されることを示すことができます。このような実行は、継続元タスクがアパートメントに対応しているかどうかに関係なく行われます。 アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。

このメソッドは、Windows ランタイムアプリでのみ使用できます。

## <a name="use_default"></a><a name="use_default"></a> use_default

タスクの既定の継続コンテキストを作成します。

```cpp
static task_continuation_context use_default();
```

### <a name="return-value"></a>戻り値

既定の継続コンテキスト。

### <a name="remarks"></a>解説

メソッドを呼び出すときに継続コンテキストを指定しない場合は、既定のコンテキストが使用され `then` ます。 Windows 7 以前に対応した Windows アプリケーション、および Windows 8 以降に対応したデスクトップ アプリケーションでは、ランタイムによって、タスクの継続を実行する状況が判別されます。 ただし、Windows ランタイムアプリでは、アパートメント対応タスクの継続の既定の継続コンテキストは、が呼び出されるアパートメントです `then` 。

アパートメントに対応するタスクとは、Windows Runtime `IAsyncInfo` インターフェイスのラップを解除するタスク、またはそのようなタスクの子となるタスクです。 したがって、Windows ランタイム STA でアパートメント対応のタスクについて継続をスケジュールする場合、継続はその STA で実行されます。

アパートメント以外に対応するタスクの継続は、ランタイムが選択したコンテキストで実行されます。

## <a name="task_continuation_contextuse_synchronous_execution"></a><a name="use_synchronous_execution"></a> task_continuation_context:: use_synchronous_execution

同期実行コンテキストを表すタスクの継続コンテキストオブジェクトを返します。

### <a name="syntax"></a>構文

```cpp
static task_continuation_context use_synchronous_execution();
```

### <a name="return-value"></a>戻り値

同期実行コンテキスト。

### <a name="remarks"></a>解説

メソッドは、 `use_synchronous_execution` 継続タスクをコンテキスト上で同期的に実行するように強制します。これにより、継続元タスクの完了が発生します。

継続がアタッチされたときに継続元タスクが既に完了している場合、継続は、継続をアタッチするコンテキストで同期的に実行されます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
