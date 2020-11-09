---
title: OptRef クラス
description: C++ Build Insights SDK の OptRef クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 72d3867456ecc2bb643239ddb0186668e43f69ef
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920516"
---
# <a name="optref-class"></a>OptRef クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`OptRef` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [OPT_REF](../event-table.md#opt-ref) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`OptRef` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[OptRef](#opt-ref)

## <a name="optref"></a><a name="opt-ref"></a> OptRef

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[OPT_REF](../event-table.md#opt-ref) イベント。

::: moniker-end
