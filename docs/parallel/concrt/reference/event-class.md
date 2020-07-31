---
title: event クラス
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::event
- CONCRT/concurrency::event::reset
- CONCRT/concurrency::event::set
- CONCRT/concurrency::event::wait
- CONCRT/concurrency::event::wait_for_multiple
- CONCRT/concurrency::event::timeout_infinite
helpviewer_keywords:
- event class
ms.assetid: fba35a53-6568-4bfa-9aaf-07c0928cf73d
ms.openlocfilehash: 3f2ec71083f7a7905bad5cda014baba914e31e79
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215804"
---
# <a name="event-class"></a>event クラス

コンカレンシー ランタイムを明示的に認識する手動リセット イベントです。

## <a name="syntax"></a>構文

```cpp
class event;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ イベントデストラクター](#dtor)|イベントを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[reset](#reset)|イベントを非シグナル状態にリセットします。|
|[set](#set)|イベントを通知します。|
|[待機](#wait)|イベントがシグナル状態になるのを待機します。|
|[wait_for_multiple](#wait_for_multiple)|複数のイベントがシグナル状態になるのを待機します。|

### <a name="public-constants"></a>パブリック定数

|名前|説明|
|----------|-----------------|
|[timeout_infinite](#timeout_infinite)|待機がタイムアウトしないことを示す値。|

## <a name="remarks"></a>解説

詳細については、「[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`event`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt .h

**名前空間:** concurrency

## <a name="event"></a><a name="ctor"></a> イベント

新しいイベントを構築します。

```cpp
_CRTIMP event();
```

### <a name="remarks"></a>解説

## <a name="event"></a><a name="dtor"></a>~ イベント

イベントを破棄します。

```cpp
~event();
```

### <a name="remarks"></a>解説

デストラクターが実行されるとイベントで待機するスレッドがなくなると想定されます。 まだ待機しているスレッドと共にイベントが破棄されるようにすると、未定義の動作が発生します。

## <a name="reset"></a><a name="reset"></a>解除

イベントを非シグナル状態にリセットします。

```cpp
void reset();
```

## <a name="set"></a><a name="set"></a>一連

イベントを通知します。

```cpp
void set();
```

### <a name="remarks"></a>解説

イベントを通知すると、イベントを待機している任意の数のコンテキストが実行できるようになります。

## <a name="timeout_infinite"></a><a name="timeout_infinite"></a>timeout_infinite

待機がタイムアウトしないことを示す値。

```cpp
static const unsigned int timeout_infinite = COOPERATIVE_TIMEOUT_INFINITE;
```

## <a name="wait"></a><a name="wait"></a>待機

イベントがシグナル状態になるのを待機します。

```cpp
size_t wait(unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>パラメーター

*_Timeout*<br/>
待機がタイムアウトするまでのミリ秒数を示します。値は、 `COOPERATIVE_TIMEOUT_INFINITE` タイムアウトがないことを示します。

### <a name="return-value"></a>戻り値

待機条件が満たされた場合は、値 `0` を返します。それ以外の場合は、イベントがシグナル状態になることなく待機がタイムアウトしたことを示す `COOPERATIVE_WAIT_TIMEOUT` 値を返します。

> [!IMPORTANT]
> ユニバーサル Windows プラットフォーム (UWP) アプリでは、ASTA スレッドでを呼び出さないでください `wait` 。この呼び出しは現在のスレッドをブロックし、アプリが応答しなくなる可能性があるためです。

## <a name="wait_for_multiple"></a><a name="wait_for_multiple"></a>wait_for_multiple

複数のイベントがシグナル状態になるのを待機します。

```cpp
static size_t __cdecl wait_for_multiple(
    _In_reads_(count) event** _PPEvents,
    size_t count,
    bool _FWaitAll,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```

### <a name="parameters"></a>パラメーター

*_PPEvents*<br/>
待機するイベントの配列。 配列内のイベントの数は、`count` パラメーターによって指定されます。

*count*<br/>
配列内のイベントの数は、`_PPEvents` パラメーターで指定されます。

*_FWaitAll*<br/>
値に設定されている場合、パラメーター **`true`** は、パラメーターで指定された配列内のすべてのイベント `_PPEvents` が、待機を満たすためにシグナル状態になる必要があることを指定します。 値に設定 **`false`** されている場合は、パラメーターに指定された配列内のすべてのイベントがシグナル状態になることを指定し `_PPEvents` ます。

*_Timeout*<br/>
待機がタイムアウトするまでのミリ秒数を示します。値は、 `COOPERATIVE_TIMEOUT_INFINITE` タイムアウトがないことを示します。

### <a name="return-value"></a>戻り値

待機条件が満たされた場合は、`_PPEvents` パラメーターに指定された配列内の、待機条件を満たしたインデックス。それ以外の場合は、条件が満たされることなく待機がタイムアウトしたことを示す `COOPERATIVE_WAIT_TIMEOUT` 値。

### <a name="remarks"></a>解説

パラメーター `_FWaitAll` が値に設定されていて、すべてのイベントが待機に応じる必要があることを **`true`** 示す場合、関数によって返されるインデックスは、値ではないという点以外に特別な意味を持ちません `COOPERATIVE_WAIT_TIMEOUT` 。

> [!IMPORTANT]
> ユニバーサル Windows プラットフォーム (UWP) アプリでは、ASTA スレッドでを呼び出さないでください `wait_for_multiple` 。この呼び出しは現在のスレッドをブロックし、アプリが応答しなくなる可能性があるためです。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
