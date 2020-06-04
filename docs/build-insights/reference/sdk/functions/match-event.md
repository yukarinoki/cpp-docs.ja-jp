---
title: マッチイベント
description: C++ ビルド インサイト SDK マッチイベント関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0c60653641c676716bcdd60865433773da79325f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323853"
---
# <a name="matchevent"></a>マッチイベント

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MatchEvent`関数は、イベントの種類のリストに対してイベントを照合するために使用されます。 イベントがリスト内の型と一致する場合は、ハンドラーに転送され、さらに処理されます。

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

*イベント*\
一致させる最初のイベントの種類。

*Tイベント*\
一致させる残りのイベントタイプ。

*呼び出し可能*\
をサポート`operator()`する型。 この演算子に渡される引数の詳細については、*呼び出し可能パラメーター*の説明を参照してください。

*Tエクストラアルグ*\
に渡された追加の引数の`MatchEvent`型。

*イベント*\
*TEvent*および*TEvents*で記述されているイベントの種類と照合するイベント。

*呼び出し*\
`MatchEvent`呼び出しは、イベントを*TEvent*および*TEvents*で記述されたイベントの種類と正常に一致した後に*呼び出し可能*です。 *呼び出し可能*に渡される最初の引数は、一致したイベントタイプの r 値です。 *extraArgs*パラメータ パックは、*呼び出し可能*の残りのパラメータで完全に転送されます。  

*エクストラ引数*\
一致したイベントの種類と共に*呼び出し可能*に完全に転送される引数。

### <a name="return-value"></a>戻り値

一致が成功した場合は**true、** そうでない場合は**false**の**ブール**値。

## <a name="remarks"></a>解説

*TEvent*パラメータおよび*TEvents*パラメータに使用するイベントタイプは *、キャプチャ クラス*のリストから選択されます。 イベントの一覧と、イベントの照合に使用できるキャプチャ クラスについては、[イベント テーブル](../event-table.md)を参照してください。

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
