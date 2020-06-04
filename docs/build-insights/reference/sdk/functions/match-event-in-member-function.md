---
title: 関数を指定します。
description: 関数リファレンスを構築します。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MatchEventInMemberFunction
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 522630da16e3f4a1294316d88140f4bc25dca2c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323899"
---
# <a name="matcheventinmemberfunction"></a>関数を指定します。

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

この`MatchEventInMemberFunction`関数は、メンバー関数の最初のパラメーターで記述されている型とイベントを照合するために使用されます。 一致したイベントは、さらに処理するためにメンバー関数に転送されます。

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

*インターフェイス*\
メンバー関数を含む型。

*Tリターン*\
メンバー関数の戻り値の型。

*イベント*\
一致させるイベントの型。

*Tエクストラパラム*\
メンバー関数で受け入れられる追加のパラメーターの型と、一致するイベントの種類。

*Tエクストラアルグ*\
に渡された追加の引数の`MatchEventInMemberFunction`型。

*イベント*\
*TEvent*で記述されているイベントの種類と一致するイベント。

*オブジェクトPtr*\
*メンバーFunc*が呼び出されるオブジェクトへのポインター。

*メンバーファンク*\
一致するイベントの種類を記述するメンバー関数。

*エクストラ引数*\
イベント型パラメーターと共に*メンバーFunc*に完全に転送される引数。

### <a name="return-value"></a>戻り値

一致が成功した場合は**true、** それ以外の場合は**false**の**ブール**値。

## <a name="remarks"></a>解説

*TEvent*パラメータに使用するイベントタイプは *、キャプチャクラス*のリストから選択できます。 イベントの一覧と、イベントの照合に使用できるキャプチャ クラスについては、[イベント テーブル](../event-table.md)を参照してください。

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
