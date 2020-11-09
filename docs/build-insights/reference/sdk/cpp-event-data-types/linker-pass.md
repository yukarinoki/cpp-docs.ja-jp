---
title: LinkerPass クラス
description: C++ Build Insights SDK の LinkerPass クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bee4538ff04ec14effe0223a178ffdb2cca37a75
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920594"
---
# <a name="linkerpass-class"></a>LinkerPass クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`LinkerPass` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [PASS1](../event-table.md#pass1) または [PASS2](../event-table.md#pass2) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Activity](activity.md) から継承されたメンバーに加えて、`LinkerPass` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[LinkerPass](#linker-pass)

## <a name="linkerpass"></a><a name="linker-pass"></a> LinkerPass

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[PASS1](../event-table.md#pass1) または [PASS2](../event-table.md#pass2) イベント。

::: moniker-end
