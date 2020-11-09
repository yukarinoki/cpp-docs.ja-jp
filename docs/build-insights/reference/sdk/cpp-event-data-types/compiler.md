---
title: Compiler クラス
description: C++ Build Insights SDK の Compiler クラスのリファレンスです。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 52f8bb2ffc474cbf8e58552c77a4bb9fabc13c7e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923319"
---
# <a name="compiler-class"></a>Compiler クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Compiler` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [COMPILER](../event-table.md#compiler) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Invocation](invocation.md) から継承されたメンバーに加えて、`Compiler` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[Compiler](#compiler)

## <a name="compiler"></a><a name="compiler"></a> Compiler

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[COMPILER](../event-table.md#compiler) イベント。

::: moniker-end
