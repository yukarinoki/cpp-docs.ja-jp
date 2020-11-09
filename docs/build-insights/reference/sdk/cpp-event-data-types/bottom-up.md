---
title: BottomUp クラス
description: C++ Build Insights SDK の BottomUp クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BottomUp
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4fb5d9165837484477044f200e5a17da0e678e32
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923387"
---
# <a name="bottomup-class"></a>BottomUp クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`BottomUp` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [BOTTOM_UP](../event-table.md#bottom-up) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class BottomUp : public Activity
{
public:
    BottomUp(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`BottomUp` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[BottomUp](#bottom-up)

## <a name="bottomup"></a><a name="bottom-up"></a> BottomUp

```cpp
BottomUp(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[BOTTOM_UP](../event-table.md#bottom-up) イベント。

::: moniker-end
