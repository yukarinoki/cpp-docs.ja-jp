---
title: クラス
description: C++ ビルド インサイト SDK SimpleEvent クラスリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 414ff5c1af99acc612384c1ae39f6e12ab051275
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324360"
---
# <a name="simpleevent-class"></a>クラス

::: moniker range="<=vs-2015"

C++ ビルド インサイト SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを参照するには、この記事の Visual Studio**バージョン**セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の上部に表示されます。

::: moniker-end
::: moniker range=">=vs-2017"

クラス`SimpleEvent`[は、](../functions/match-event-in-member-function.md)[関数](../functions/match-event.md)で使用されます。 [MatchEventStack](../functions/match-event-stack.md) [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) この機能を使用して、任意の単純なイベントに一致させます。 [イベント テーブル](../event-table.md)を参照して、クラスで一致できるすべてのイベントを`SimpleEvent`確認します。

## <a name="syntax"></a>構文

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

[クラスには、Event](event.md)基本クラスから継承されたメンバーと`SimpleEvent`共に、次のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[シンプルイベント](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a>シンプルイベント

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*イベント*\
任意の単純なイベント。

::: moniker-end
