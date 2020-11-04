---
title: MatchEventStackInMemberFunction
description: C++ Build Insights SDK MatchEventStackInMemberFunction 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4d416a10d5e2803cd978243a1e44625a2e696d42
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920178"
---
# <a name="matcheventstackinmemberfunction"></a>MatchEventStackInMemberFunction

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MatchEventStackInMemberFunction` 関数は、メンバー関数のパラメーター リストによって記述される特定のイベント階層に対してイベント スタックを照合するために使用されます。 一致した階層は、後続の処理のためにそのメンバー関数に転送されます。 イベント、イベント スタック、階層の詳細については、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, TExtraParams...),
    TExtraArgs&&...           extraArgs);

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, TExtraParams...),
    TExtraArgs&&...           extraArgs);

// Etc...

template <
    typename     TInterface,
    typename     TReturn,
    typename     T1,
    typename     T2,
    typename     T3,
    typename     T4,
    typename     T5,
    typename     T6,
    typename     T7,
    typename     T8,
    typename     T9,
    typename     T10,
    typename...  TExtraParams,
    typename...  TExtraArgs>
bool MatchEventStackInMemberFunction(
    const EventStack&         eventStack,
    TInterface*               objectPtr,
    TReturn (TInterface::*    memberFunc)(T1, T2, T3, T4, T5, T6, T7, T8, T9, T10, TExtraParams...),
    TExtraArgs&&...           extraArgs);
```

### <a name="parameters"></a>パラメーター

*TInterface*\
メンバー関数を含む型。

*TReturn*\
メンバー関数の戻り値の型。

*T1* , ..., *T10*\
照合するイベント階層が記述されている型。

*TExtraParams*\
メンバー関数によって受け入れられる追加パラメーターの型、およびイベント階層の型。

*TExtraArgs*\
`MatchEventStackInMemberFunction` に渡された追加の引数の型。

*eventStack*\
*T1* から *T10* によって記述されるイベントの型の階層と照合するイベント スタック。

*objectPtr*\
*memberFunc* が呼び出されるオブジェクトへのポインター。

*memberFunc*\
照合するイベント型の階層が記述されているメンバー関数。

*extraArgs*\
イベント型階層のパラメーターと共に *memberFunc* に完全に転送される引数。

### <a name="return-value"></a>戻り値

正常に一致した場合は **`true`** であり、それ以外の場合は **`false`** である **`bool`** 値。

## <a name="remarks"></a>Remarks

*eventStack* の最後のイベントは常に、照合対象のイベント型階層の最後のエントリと照合されます。 イベント型階層の他のすべての型は、同じ順序になっている限り、 *eventStack* 内の最後を除く任意の位置と照合できます。

*T1* から *T10* パラメーターに使用するイベントの型は、" *キャプチャ クラス* " のリストから選択します。 照合に使用できるイベントのリストとキャプチャ クラスについては、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="example"></a>例

```cpp
void MyClass::Foo1(Compiler cl, BackEndPass bep, C2DLL c2,
    CodeGeneration cg, Thread t, Function f) { }

void MyClass::Foo2(Compiler cl, Function f) { }

void MyClass::Foo3(Thread t, Compiler cl, Function f) { }

void MyClass::Foo4(Compiler cl) { }

void MyClass::OnStartActivity(const EventStack& eventStack)
{
    // Let's assume eventStack contains:
    // [Compiler, BackEndPass, C2DLL, CodeGeneration, Thread, Function]

    bool b1 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo1);

    bool b2 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo2);

    bool b3 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo3);

    bool b4 = MatchEventStackInMemberFunction(
        eventStack, this, &MyClass::Foo4);

    // b1: true because the parameter types of Foo1 match the eventStack
    //     exactly.
    // b2: true because Function is the last entry in both the member
    //     function parameter list and 'eventStack', and also because
    //     Compiler comes before Function in 'eventStack' and in the
    //     parameter type list.
    // b3: false because, even though both Thread and Compiler come
    //     before Function in 'eventStack', the member function parameter
    //     list doesn't list them in the right order.
    // b4: false because the last entry in the member function parameter
    //     list is Compiler, which doesn't match the last entry in 'eventStack'
    //     (Function).
}
```

::: moniker-end
