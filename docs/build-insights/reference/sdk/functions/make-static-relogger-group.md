---
title: MakeStaticReloggerGroup
description: C++ Build Insights SDK MakeStaticReloggerGroup 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticReloggerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1d49f15a14675f265e1f63ef8795f442f49ad5d4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920204"
---
# <a name="makestaticreloggergroup"></a>MakeStaticReloggerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MakeStaticReloggerGroup` 関数は、[Relog](relog.md) などの関数に渡すことができる静的リロガー グループを作成するために使用されます。 リロガー グループのメンバーは、トレース内のすべてのイベントが処理されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
template <typename... TReloggerPtrs>
auto MakeStaticReloggerGroup(TReloggerPtrs... reloggers);
```

### <a name="parameters"></a>パラメーター

*TReloggerPtrs*\
このパラメーターは常に推測されます。

*reloggers*\
静的リロガー グループに含められた [`IRelogger`](../other-types/irelogger-class.md) ポインターのパラメーター パック。 これらのポインターには、生、`std::unique_ptr`、または `std::shared_ptr` を使用できます。 継承関係のため、[`IAnalyzer`](../other-types/ianalyzer-class.md) ポインターは `IRelogger` ポインターとも見なされます。

### <a name="return-value"></a>戻り値

静的リロガー グループ。 戻り値を取得するには、 **`auto`** キーワードを使用します。

## <a name="remarks"></a>Remarks

動的リロガー グループとは異なり、静的リロガー グループのメンバーは、コンパイル時に既知である必要があります。 また、静的リロガー グループには、ポリモーフィックな動作を持たない [`IRelogger`](../other-types/irelogger-class.md) ポインターが含まれています。 静的リロガー グループを使用して Windows イベント トレーシング (ETW) のトレースを分析する場合、`IRelogger` インターフェイスへの呼び出しは、常に、リロガー グループのメンバーによって直接指し示されているオブジェクトに解決されます。 このように柔軟性が低いことで、イベント処理時間が短縮される可能性があります。 コンパイル時にリロガー グループのメンバーがわからない場合、または `IRelogger` ポインターに対してポリモーフィックな動作が必要な場合は、動的リロガー グループの使用を検討します。 代わりに [`MakeDynamicReloggerGroup`](make-dynamic-relogger-group.md) を呼び出すことによって、動的リロガー グループを使用できます。

::: moniker-end
