---
title: Pass2 クラス
description: C++ Build Insights SDK の Pass2 クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 17f915371f70a6f4398d91251680c460aa231feb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920503"
---
# <a name="pass2-class"></a>Pass2 クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Pass2` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [PASS2](../event-table.md#pass2) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [LinkerPass](linker-pass.md) から継承されたメンバーに加えて、`Pass2` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[Pass2](#pass2)

## <a name="pass2"></a><a name="pass2"></a> Pass2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[PASS2](../event-table.md#pass2) イベント。

::: moniker-end
