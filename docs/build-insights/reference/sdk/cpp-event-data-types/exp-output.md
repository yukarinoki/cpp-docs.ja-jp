---
title: ExpOutput クラス
description: C++ Build Insights SDK の ExpOutput クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f0e467466c344be0c6c796dd7cc168e6ff49d4c9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923282"
---
# <a name="expoutput-class"></a>ExpOutput クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`ExpOutput` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [EXP_OUTPUT](../event-table.md#exp-output) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [FileOutput](file-output.md) から継承されたメンバーに加えて、`ExpOutput` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[ExpOutput](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a> ExpOutput

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[EXP_OUTPUT](../event-table.md#exp-output) イベント。

::: moniker-end
