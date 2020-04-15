---
title: クラス全体
description: C++ ビルド インサイト SDK 全体プログラム分析 クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c68441b7da09f9880bbb2f97544b1ad8da2f631f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324115"
---
# <a name="wholeprogramanalysis-class"></a>クラス全体

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`WholeProgramAnalysis`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`WholeProgramAnalysis`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[プログラム分析全体](#whole-program-analysis)

## <a name="wholeprogramanalysis"></a><a name="whole-program-analysis"></a>プログラム分析全体

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis)イベント。

::: moniker-end
