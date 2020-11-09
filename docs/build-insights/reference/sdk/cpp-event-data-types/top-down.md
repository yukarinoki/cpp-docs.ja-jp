---
title: TopDown クラス
description: C++ Build Insights SDK の TopDown クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88622461b27a6037d8d7fbb73cd324978302c941
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920425"
---
# <a name="topdown-class"></a>TopDown クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`TopDown` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [TOP_DOWN](../event-table.md#top-down) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`TopDown` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[TopDown](#top-down)

## <a name="topdown"></a><a name="top-down"></a> TopDown

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[TOP_DOWN](../event-table.md#top-down) イベント。

::: moniker-end
