---
title: SimpleEvent クラス
description: C++ Build Insights SDK の SimpleEvent クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dc09a279157482089adedc660395feaa98376dae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922995"
---
# <a name="simpleevent-class"></a>SimpleEvent クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`SimpleEvent` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 任意の簡易イベントと照合するために使用します。 `SimpleEvent` クラスで照合できるすべてのイベントを見るには、[イベント テーブル](../event-table.md)に関する記事を参照してください。

## <a name="syntax"></a>構文

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Event](event.md) から継承されたメンバーに加えて、`SimpleEvent` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a> SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
任意の簡易イベント。

::: moniker-end
