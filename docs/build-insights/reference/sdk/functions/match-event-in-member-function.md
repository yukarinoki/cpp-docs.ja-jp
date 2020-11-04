---
title: MatchEventInMemberFunction
description: C++ Build Insights SDK MatchEventInMemberFunction 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 62a7bf6bde62dee7fdf5b1d2ce9044491a123f94
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920191"
---
# <a name="matcheventinmemberfunction"></a>MatchEventInMemberFunction

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MatchEventInMemberFunction` 関数は、メンバー関数の最初のパラメーターで記述される型に対してイベントを照合するために使用されます。 一致したイベントは、後続の処理のためにそのメンバー関数に転送されます。

## <a name="syntax"></a>構文

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     TEvent,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventInMemberFunction(
    const RawEvent&          event,
    TInterface*              objectPtr,
    TReturn (TInterface::*   memberFunc)(TEvent, TExtraParams...),
    TExtraArgs&&...          extraArgs);
```

### <a name="parameters"></a>パラメーター

*TInterface*\
メンバー関数を含む型。

*TReturn*\
メンバー関数の戻り値の型。

*TEvent*\
照合するイベントの型。

*TExtraParams*\
メンバー関数によって受け入れられる追加パラメーターの型、および照合するイベントの型。

*TExtraArgs*\
`MatchEventInMemberFunction` に渡された追加の引数の型。

*event*\
*TEvent* によって記述されるイベントの型と照合するイベント。

*objectPtr*\
*memberFunc* が呼び出されるオブジェクトへのポインター。

*memberFunc*\
照合するイベント型が記述されているメンバー関数。

*extraArgs*\
イベント型のパラメーターと共に *memberFunc* に完全に転送される引数。

### <a name="return-value"></a>戻り値

正常に一致した場合は **`true`** であり、それ以外の場合は **`false`** である **`bool`** 値。

## <a name="remarks"></a>Remarks

*TEvent* パラメーターに使用するイベントの型は、" *キャプチャ クラス* " のリストから選択できます。 照合に使用できるイベントのリストとキャプチャ クラスについては、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="example"></a>例

```cpp
void MyClass::Foo1(Function f) {}

void MyClass::Foo2(Compiler cl) {}

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    auto& functionEvent = eventStack.Back(); // The Function event

    bool b1 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo1);

    bool b2 = MatchEventInMemberFunction(
        functionEvent, this, &MyClass::Foo2);

    // b1: true because the first parameter of Foo1 is Function.
    // b2: false because the first parameter of Foo2 isn't Function.
}
```

::: moniker-end
