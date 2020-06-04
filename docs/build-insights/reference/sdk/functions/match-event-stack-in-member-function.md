---
title: 関数を一致させます。
description: 関数リファレンスを構築します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventStackInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 28842a02e7edc2e00266d8c7941798f4ce714ded
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323880"
---
# <a name="matcheventstackinmemberfunction"></a>関数を一致させます。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MatchEventStackInMemberFunction`関数は、メンバー関数のパラメーター リストで記述された特定のイベント階層に対してイベント スタックを照合するために使用されます。 一致した階層は、さらに処理するためにメンバー関数に転送されます。 イベント、イベント スタック、および階層の詳細については、[イベント テーブル](../event-table.md)を参照してください。

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

*インターフェイス*\
メンバー関数を含む型。

*Tリターン*\
メンバー関数の戻り値の型。

*T1*, .., *T10*\
一致するイベント階層を記述する型。

*Tエクストラパラム*\
メンバー関数によって受け入れられる追加のパラメーターの型、およびイベント階層型。

*Tエクストラアルグ*\
に渡された追加の引数の`MatchEventStackInMemberFunction`型。

*イベントスタック*\
T1 から*T10*で記述されたイベント タイプ*T10*階層に一致するイベント スタック。

*オブジェクトPtr*\
*メンバーFunc*が呼び出されるオブジェクトへのポインター。

*メンバーファンク*\
一致するイベントの種類の階層を記述するメンバー関数。

*エクストラ引数*\
イベント型階層パラメーターと共に*memberFunc*に完全に転送される引数。

### <a name="return-value"></a>戻り値

一致が成功した場合は**true、** それ以外の場合は**false**の**ブール**値。

## <a name="remarks"></a>解説

*eventStack*の最後のイベントは、常にイベントタイプ階層内の最後のエントリと照合されます。 イベントタイプ階層内の他のすべてのタイプは、同じ順序である場合、最後のタイプを除く*eventStack*内の任意の位置と一致することができます。

T1 から*T10* *T10*パラメータに使用するイベント タイプは *、キャプチャ クラス*の一覧から選択されます。 イベントの一覧と、イベントの照合に使用できるキャプチャ クラスについては、[イベント テーブル](../event-table.md)を参照してください。

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
