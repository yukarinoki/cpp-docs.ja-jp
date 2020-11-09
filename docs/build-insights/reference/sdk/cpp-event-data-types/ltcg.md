---
title: LTCG クラス
description: C++ Build Insights SDK の LTCG クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LTCG
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3b6bab629307c9fc4fb021df2e75772d5247566d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920555"
---
# <a name="ltcg-class"></a>LTCG クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`LTCG` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [LTCG](../event-table.md#ltcg) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class LTCG : public Activity
{
public:
    LTCG(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`LTCG` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[LTCG](#ltcg)

## <a name="ltcg"></a><a name="ltcg"></a> LTCG

```cpp
LTCG(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[LTCG](../event-table.md#ltcg) イベント。

::: moniker-end
