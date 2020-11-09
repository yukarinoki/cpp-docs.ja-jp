---
title: Linker クラス
description: C++ Build Insights SDK の Linker クラスのリファレンス。
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cf5544d725c12db8962d888944d4a281387207fa
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923089"
---
# <a name="linker-class"></a>Linker クラス

::: moniker range="<=msvc-140"

C++ Build Insights SDK は、Visual Studio 2017 以降と互換性があります。 これらのバージョンのドキュメントを表示するには、この記事の Visual Studio **Version** セレクター コントロールを Visual Studio 2017 または Visual Studio 2019 に設定します。 このページの目次の一番上にあります。

::: moniker-end
::: moniker range=">=msvc-150"

`Linker` クラスは、[MatchEvent](../functions/match-event.md)、[MatchEventInMemberFunction](../functions/match-event-in-member-function.md)、[MatchEventStack](../functions/match-event-stack.md)、および [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md) 関数と共に使用されます。 [LINKER](../event-table.md#linker) イベントを照合するために使用します。

## <a name="syntax"></a>構文

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>メンバー

その基底クラス [Invocation](invocation.md) から継承されたメンバーに加えて、`Linker` クラスには以下のメンバーが含まれます。

### <a name="constructors"></a>コンストラクター

[リンカー](#linker)

## <a name="linker"></a><a name="linker"></a> Linker

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>パラメーター

*event*\
[LINKER](../event-table.md#linker) イベント。

::: moniker-end
