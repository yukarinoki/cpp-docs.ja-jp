---
title: MatchEvent
description: C++ Build Insights SDK MatchEvent 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8ec2c6bfcacf28998058dc66b5f363fbf1ea5d70
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224111"
---
# <a name="matchevent"></a>MatchEvent

::: moniker range="<=vs-2015"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=vs-2017"

`MatchEvent` 関数は、イベントをイベントの型のリストと照合するために使用されます。 イベントがリスト内の型と一致する場合は、後続の処理のためにハンドラーに転送されます。

## <a name="syntax"></a>構文

```cpp
template <
    typename        TEvent,
    typename...     TEvents,
    typename        TCallable,
    typename...     TExtraArgs>
bool MatchEvent(
    const RawEvent& event,
    TCallable&&     callable,
    TExtraArgs&&... extraArgs);
```

### <a name="parameters"></a>パラメーター

*TEvent*\
照合する最初のイベントの型。

*TEvents*\
照合する残りのイベントの型。

*TCallable*\
`operator()` をサポートする型。 この演算子に渡される引数の詳細については、*callable* パラメーターの説明を参照してください。

*TExtraArgs*\
`MatchEvent` に渡された追加の引数の型。

*event*\
*TEvent* と *TEvents* によって記述されるイベントの型と照合するイベント。

*callable*\
`MatchEvent` では、*TEvent* および *TEvents* によって記述されるイベントの型のいずれかとイベントが正常に照合された後、*callable* が呼び出されます。 *callable* に渡される最初の引数は、一致したイベントの型の右辺値です。 *extraArgs* パラメーター パックは、*callable* の残りのパラメーターで完全に転送されます。  

*extraArgs*\
一致したイベントの型と共に *callable* に完全に転送される引数。

### <a name="return-value"></a>戻り値

正常に一致した場合は **`true`** であり、それ以外の場合は **`false`** である **`bool`** 値。

## <a name="remarks"></a>Remarks

*TEvent* および *TEvents* パラメーターに使用するイベントの型は、"*キャプチャ クラス*" のリストから選択します。 照合に使用できるイベントのリストとキャプチャ クラスについては、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="example"></a>例

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEvent<Function, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});

    bool b2 = MatchEvent<CodeGeneration, Thread>(
        functionEvent, [](auto matchedEvent){ /* Do something... */});


    // b1: true because the list of types contains Function, which is
    //     the type of the event we are trying to match.
    // b2: false because the list of types doesn't contain Function.
}
```

::: moniker-end
