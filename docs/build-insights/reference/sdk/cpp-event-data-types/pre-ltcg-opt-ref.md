---
title: クラス
description: C++ ビルド インサイト SDK PreLTCGOptRef クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a48dc2db0345333da3ec66ccb3a345323b4f10c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324397"
---
# <a name="preltcgoptref-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`PreLTCGOptRef`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref)イベントに一致させるために使用します。

## <a name="syntax"></a>構文

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

クラスには、[その Activity](activity.md)基本クラスから継承された`PreLTCGOptRef`メンバーと共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[プレエルトCGオプトレフ](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a>プレエルトCGオプトレフ

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
[PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref)イベント。

::: moniker-end
