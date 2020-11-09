---
title: Pass1 クラス
description: C++ Build Insights SDK の Pass1 クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 99ada8a2db5ac464113d9805797d4b4555367e77
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923031"
---
# <a name="pass1-class"></a>Pass1 クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Pass1` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [PASS1](../event-table.md#pass1) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [LinkerPass](linker-pass.md) から継承されたメンバーに加えて、`Pass1` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[Pass1](#pass1)

## <a name="pass1"></a><a name="pass1"></a> Pass1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[PASS1](../event-table.md#pass1) イベント。

::: moniker-end
