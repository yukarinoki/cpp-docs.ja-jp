---
title: WholeProgramAnalysis クラス
description: C++ Build Insights SDK の WholeProgramAnalysis クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: aa766bb33c358627d3347e1d64ed7cc3be832116
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920347"
---
# <a name="wholeprogramanalysis-class"></a>WholeProgramAnalysis クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`WholeProgramAnalysis` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`WholeProgramAnalysis` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[WholeProgramAnalysis](#whole-program-analysis)

## <a name="wholeprogramanalysis"></a><a name="whole-program-analysis"></a> WholeProgramAnalysis

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) イベント。

::: moniker-end
