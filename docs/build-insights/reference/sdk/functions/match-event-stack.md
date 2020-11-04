---
title: MatchEventStack
description: C++ Build Insights SDK MatchEventStack 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 08627b6af601f6894aa228683ffb51232b015310
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922817"
---
# <a name="matcheventstack"></a>MatchEventStack

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MatchEventStack` 関数は、イベント スタックを特定のイベント階層と照合するために使用されます。 一致した階層は、後続の処理のためにハンドラーに転送されます。 イベント、イベント スタック、階層の詳細については、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
template <
    typename          TEvent,
    typename...       TEvents,
    typename          TCallable,
    typename...       TExtraArgs>
bool MatchEventStack(
    const EventStack& eventStack,
    TCallable&&       callable,
    TExtraArgs&&...   extraArgs);
```

### <a name="parameters"></a>パラメーター

*TEvent*\
イベント スタックで照合する最上位の親の型。

*TEvents*\
イベント スタックで照合する残りの型。

*TCallable*\
`operator()` をサポートする型。 この演算子に渡される引数の詳細については、 *callable* パラメーターの説明を参照してください。

*TExtraArgs*\
`MatchEventStack` に渡される追加の引数の型。

*eventStack*\
*TEvent* と *TEvents* によって記述されるイベントの型の階層と照合するイベント スタック。

*callable*\
*TEvent* および *TEvents* によって記述されるイベント型階層とイベント スタックが正常に照合されると、`MatchEventStack` によって *callable* が呼び出されます。 *callable* には、イベント階層内の型ごとに 1 つの右辺値引数が渡されます。 *extraArgs* パラメーター パックは、 *callable* の残りのパラメーターで完全に転送されます。

*extraArgs*\
一致したイベントの型と共に *callable* に完全に転送される引数。

### <a name="return-value"></a>戻り値

正常に一致した場合は **`true`** であり、それ以外の場合は **`false`** である **`bool`** 値。

## <a name="remarks"></a>Remarks

*eventStack* の最後のイベントは、連結された \[*TEvent* , *TEvents...* \] 型リストの最後のエントリと常に照合されます。 *TEvent* と *TEvents* の他のすべてのエントリは、同じ順序になっている限り、 *eventStack* 内の最後を除く任意の位置と照合できます。

*TEvent* および *TEvents* パラメーターに使用するイベントの型は、" *キャプチャ クラス* " のリストから選択します。 照合に使用できるイベントのリストとキャプチャ クラスについては、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="example"></a>例

```cpp
void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStack<Compiler, BackEndPass, C2DLL,
                CodeGeneration, Thread, Function>(
        eventStack, [](Compiler cl, BackEndPass bep, C2DLL c2,
            CodeGeneration cg, Thread t, Function f){ /* Do something ... */ });

    bool b2 = MatchEventStack<Compiler, Function>(
        eventStack, [](Compiler cl, Function f){ /* Do something... */ });

    bool b3 = MatchEventStack<Thread, Compiler, Function>(
        eventStack, [](Thread t, Compiler cl Function f){ /* Do something... */ });

    bool b4 = MatchEventStack<Compiler>(
        eventStack, [](Compiler cl){ /* Do something... */ });


    // b1: true because the list of types matches the eventStack exactly.
    // b2: true because Function is the last entry in both the type list
    //     and 'eventStack', and also because Compiler comes before
    //     Function in 'eventStack' and in the type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', they aren't listed in the
    //     right order in the type list.
    // b4: false because the last entry in the type list is Compiler,
    //     which doesn't match the last entry in 'eventStack' (Function).
}
```

::: moniker-end
