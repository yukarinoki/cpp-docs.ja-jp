---
title: OptICF クラス
description: C++ Build Insights SDK の OptICF クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptICF
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b816b53e1054c4492320bdb71f2f0c7726907cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920529"
---
# <a name="opticf-class"></a>OptICF クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OptICF` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [OPT_ICF](../event-table.md#opt-icf) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class OptICF : public Activity
{
public:
    OptICF(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`OptICF` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[OptICF](#opt-icf)

## <a name="opticf"></a><a name="opt-icf"></a> OptICF

```cpp
OptICF(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[OPT_ICF](../event-table.md#opt-icf) イベント。

::: moniker-end
