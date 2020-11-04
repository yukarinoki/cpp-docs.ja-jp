---
title: MakeStaticAnalyzerGroup
description: C++ Build Insights SDK MakeStaticAnalyzerGroup 関数リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- MakeStaticAnalyzerGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d7ddb8652400438c38882b1d27e635e8f1e8db51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920243"
---
# <a name="makestaticanalyzergroup"></a>MakeStaticAnalyzerGroup

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`MakeStaticAnalyzerGroup` 関数は、[`Analyze`](analyze.md) や [`Relog`](relog.md) などの関数に渡すことができる静的アナライザー グループを作成するために使用されます。 アナライザー グループのメンバーは、トレース内のすべてのイベントが分析されるまで、左から右に 1 つずつイベントを受け取ります。

## <a name="syntax"></a>構文

```cpp
template <typename... TAnalyzerPtrs>
auto MakeStaticAnalyzerGroup(TAnalyzerPtrs... analyzers);
```

### <a name="parameters"></a>パラメーター

*TAnalyzerPtrs*\
このパラメーターは常に推測されます。

*analyzers*\
静的アナライザー グループに含められる [`IAnalyzer`](../other-types/ianalyzer-class.md) ポインターのパラメーター パック。 これらのポインターには、生、`std::unique_ptr`、または `std::shared_ptr` を使用できます。

### <a name="return-value"></a>戻り値

静的アナライザー グループ。 戻り値を取得するには、 **`auto`** キーワードを使用します。

## <a name="remarks"></a>Remarks

動的アナライザー グループとは異なり、静的アナライザー グループのメンバーは、コンパイル時に既知である必要があります。 また、静的アナライザー グループには、ポリモーフィックな動作を持たない [`IAnalyzer`](../other-types/ianalyzer-class.md) ポインターが含まれています。 静的アナライザー グループを使用して Windows イベント トレーシング (ETW) のトレースを分析する場合、`IAnalyzer` インターフェイスへの呼び出しは、常に、アナライザー グループのメンバーによって直接指し示されているオブジェクトに解決されます。 このように柔軟性が低いことで、イベント処理時間が短縮される可能性があります。 コンパイル時にアナライザー グループのメンバーがわからない場合、または `IAnalyzer` ポインターに対してポリモーフィックな動作が必要な場合は、動的アナライザー グループの使用を検討します。 動的アナライザー グループを使用するには、代わりに [`MakeDynamicAnalyzerGroup`](make-static-analyzer-group.md) を呼び出します。

::: moniker-end
