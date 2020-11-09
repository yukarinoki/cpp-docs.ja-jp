---
title: FrontEndFileGroup クラス
description: C++ Build Insights SDK の FrontEndFileGroup クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 902b394f645030fed4eeb79bae79535e6d246a1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923230"
---
# <a name="frontendfilegroup-class"></a>FrontEndFileGroup クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndFileGroup` クラスは、[MatchEventStack](../functions/match-event-stack.md) および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FRONT_END_FILE](../event-table.md#front-end-file) イベントのグループを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>メンバー

その基底クラス [EventGroup\<FrontEndFile\>](event-group.md) から継承されたメンバーに加えて、`FrontEndFileGroup` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[FrontEndFileGroup](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a> FrontEndFileGroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>パラメーター

*group*\
[FRONT_END_FILE](../event-table.md#front-end-file) イベントのグループ。

::: moniker-end
