---
title: オプトLBRクラス
description: C++ ビルド インサイト SDK OptLBR クラス リファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptLBR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4cbd87134741d6fc09521f94bfdfbc099cb426a2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324456"
---
# <a name="optlbr-class"></a>オプトLBRクラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`OptLBR`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [OPT_LBR](../event-table.md#opt-lbr)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class OptLBR : public Activity
{
public:
    OptLBR(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`OptLBR`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[オプトLBR](#opt-lbr)

## <a name="optlbr"></a><a name="opt-lbr"></a>オプトLBR

```cpp
OptLBR(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[OPT_LBR](../event-table.md#opt-lbr)イベント。

::: moniker-end
