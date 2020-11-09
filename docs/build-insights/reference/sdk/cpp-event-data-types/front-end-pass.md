---
title: FrontEndPass クラス
description: C++ Build Insights SDK の FrontEndPass クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2959b1b80163819287b1907c9d25ca75aa5bbc2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923209"
---
# <a name="frontendpass-class"></a>FrontEndPass クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`FrontEndPass` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [FRONT_END_PASS](../event-table.md#front-end-pass) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [CompilerPass](compiler-pass.md) から継承されたメンバーに加えて、`FrontEndPass` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[FrontEndPass](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a> FrontEndPass

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[FRONT_END_PASS](../event-table.md#front-end-pass) イベント。

::: moniker-end
