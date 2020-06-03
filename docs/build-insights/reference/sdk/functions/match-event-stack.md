---
title: イベントスタックを一致させる
description: C++ ビルド インサイト SDK マッチイベントスタック関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a223d420e8c48667fbd1c6569f02d0486f597b5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323874"
---
# <a name="matcheventstack"></a>イベントスタックを一致させる

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MatchEventStack`関数は、イベント スタックを特定のイベント階層と照合するために使用されます。 一致した階層は、さらに処理するためにハンドラに転送されます。 イベント、イベント スタック、および階層の詳細については、[イベント テーブル](../event-table.md)を参照してください。

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

*イベント*\
イベント スタックで一致させる長子の型。

*Tイベント*\
イベント スタックで一致させる残りの型。

*呼び出し可能*\
をサポート`operator()`する型。 この演算子に渡される引数の詳細については、*呼び出し可能パラメーター*の説明を参照してください。

*Tエクストラアルグ*\
に渡される余分な引数の型`MatchEventStack`。

*イベントスタック*\
*TEvent*および*TEvents*で記述されたイベントタイプ階層に一致するイベントスタック。

*呼び出し*\
イベント スタックと*TEvent*および*TEvents*で記述されたイベントタイプ階層と`MatchEventStack`のマッチングが正常に行われた場合は *、呼び出し可能*. これは、イベント階層内の各型に対して、1 つの r 値引数を*呼び出し可能*に渡します。 *extraArgs*パラメータ パックは、*呼び出し可能*の残りのパラメータで完全に転送されます。

*エクストラ引数*\
一致したイベントの種類と共に*呼び出し可能*に完全に転送される引数。

### <a name="return-value"></a>戻り値

一致が成功した場合は**true、** それ以外の場合は**false**の**ブール**値。

## <a name="remarks"></a>解説

*イベントスタック*の最後のイベントは、連結された\[ *TEvent*の最後のエントリと常に一致*します。*\]型リスト。 他のすべての*TEvent*と*TEvents*のエントリは、最後のエントリを除く*イベントスタック*内の任意の位置に一致することができます( 同じ順序にする場合)。

*TEvent*パラメータおよび*TEvents*パラメータに使用するイベントタイプは *、キャプチャ クラス*のリストから選択されます。 イベントの一覧と、イベントの照合に使用できるキャプチャ クラスについては、[イベント テーブル](../event-table.md)を参照してください。

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
